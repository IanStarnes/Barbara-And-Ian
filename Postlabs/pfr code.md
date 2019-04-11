```python
pfr3_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/pfr%203.txt'
pfr3_firstrow = 1
pfr3_time_data = (epa.column_of_time(pfr3_path,pfr3_firstrow,-1)).to(u.s)
pfr3_time_data
pfr3_concentration_data = epa.column_of_data(pfr3_path,pfr3_firstrow,1,-1,'mg/L')
pfr3_concentration_data

pfr3_concentration_data = pfr3_concentration_data - pfr3_concentration_data[0]
length = 12.5*u.ft
ID = 0.03125*u.ft
pfr3_V = length*(pi*(ID)**2)/4
pfr3_V.to(u.L)
pfr3_Q = 380 * u.mL/u.min
pfr3_theta_hydraulic = (pfr3_V/pfr3_Q).to(u.s)
pfr3_C_bar_guess = np.max(pfr3_concentration_data)/2

pfr3_CMFR = epa.Solver_CMFR_N(pfr3_time_data, pfr3_concentration_data, pfr3_theta_hydraulic, pfr3_C_bar_guess)
pfr3_CMFR.C_bar
pfr3_CMFR.N
pfr3_CMFR.theta.to(u.s)

pfr3_CMFR_model = (pfr3_CMFR.C_bar*epa.E_CMFR_N(pfr3_time_data /pfr3_CMFR.theta, pfr3_CMFR.N)).to(u.mg/u.L)

pfr3_AD = epa.Solver_AD_Pe(pfr3_time_data, pfr3_concentration_data, pfr3_theta_hydraulic, pfr3_C_bar_guess)
pfr3_AD.C_bar
pfr3_AD.Pe
pfr3_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(pfr3_AD.C_bar*pfr3_V ,2) )
print('The model estimate of the Peclet number was', pfr3_AD.Pe)
print('The tracer residence time was',ut.round_sf(pfr3_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(pfr3_AD.theta/pfr3_theta_hydraulic).magnitude)

pfr3_AD_model = (pfr3_AD.C_bar*epa.E_Advective_Dispersion((pfr3_time_data/pfr3_AD.theta).to_base_units(), pfr3_AD.Pe)).to(u.mg/u.L)

plt.plot(pfr3_time_data.to(u.s), pfr3_concentration_data.to(u.mg/u.L),'r')
plt.plot(pfr3_time_data.to(u.s), pfr3_CMFR_model,'b')
plt.plot(pfr3_time_data.to(u.s), pfr3_AD_model,'g')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'c')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'y')
plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye No holes','CMFR Model q', 'AD Model q','Measured dye Holes','CMFR Model 2', 'AD Model 2'])
plt.savefig('pfr3.png', bbox_inches = 'tight')
plt.show()
```
