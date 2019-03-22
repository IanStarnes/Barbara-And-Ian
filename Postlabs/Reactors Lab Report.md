### Lab 5 Report, Group 6
#### Ian Starnes and Barbara Oramah
##### Time (hr) Spent on Lab Report: Ian Starnes - 4  | Barbara Oramah - 4


### Table of Contents

- [Introduction](#Introduction)
- [Objective](#Objective)
- [Procedure](#Procedure)
- [Data Analysis](#Data-analysis)
- [Conclusion](#Conclusion)
- [Suggestions](#Suggestions)
- [References](#References)
- [Appendix](#Appendix)

#### Introduction

Test 1: CMFR no baffles just a stirrer on high speed
Reactor Volume = 0.00254 m3
Red dye conc = 25.8 mg/L
volume of red dye = 765 microliters
Flow rate =  380 ml/min
(100 RPM)

Bucket alone = 560g
Bucket with water = 3097g

Test 2: Two baffles with 2 holes of 7.74 mm diameter (taped)

- opposing sides of the reactor
- funky data cut it at around 4:25 pm

Reactor Volume = 0.00254 m3
Red dye conc = 13 mg/L (from 100 g/L of red dye)
volume of red dye =  400 microliters
Flow rate = 380 mL/min

Bucket alone = 492g
Bucket with water = 3075g

3/13
Note to self: remember to turn on photometer so you can read your data
Test 3: 4 baffles with 2 holes of 7.74 mm diameter (taped)

Reactor Volume = 0.00254 m3
Red dye conc used = 10 g/L
Volume of red Dye = 800 microliters

Bucket alone =  557 g
Bucket with water = 3139 g

Final measured concentration = -1.02 mg/L

Test 4: 4 baffles no hole, 14 cm in length and the reactor is 15.3 cm )taped

Observations: There are some dead zones in this test. The dye is not completely mixed in the reactor

Reactor Volume = 0.00254 m3
Red dye conc used = 10 g/L
Volume of red Dye = 800 microliters

Bucket alone =  557 g
Bucket with water = 3099 g

Final measured concentration =  -1.08 mg/L


Test 5: 7 random baffles but evenly spaced (no tape)
baffles vary in different number of holes and diameters


Observations: we observed some side slip through the edges of the baffles because we did not tape the sides

Reactor Volume = 0.00254 m3
Red dye conc used = 10 g/L
Volume of red Dye = 800 microliters

Bucket alone =  557 g
Bucket with water = 2985 g

Final measured concentration = -0.3 mg/L

Test 6: PLUG FLOWW

Observations:

length = 12.5 ft
ID = 3/8th inch

Reactor Volume = m3
Red dye conc used = 10 g/L

Observation: test 1 we had the two pumps and then we removed the tubing that would pump in the influent.

Volume of red Dye = 1000 microliters
Diluted with 22 mL of water

there are three trials of plug flow

Final measured concentration = 0 mg/L (ran until there is no dye)


#### Data Analysis

1. Use multivariable nonlinear regression to obtain the best fit between the experimental data and the two models by minimizing the sum of the squared errors. Use epa.Solver_AD_Pe and epa.Solver_CMFR_N. These functions will minimize the error by varying the values of average residence time, (mass of tracer/reactor volume), and either the number of CMFR in series or the Peclet number.

2. Generate a plot showing the experimental data as points and the model results as thin lines for each of your experiments. Explain which model fits best and discuss those results based on your expectations.

3. Compare the trends in the estimated values of N and Pe across your set of experiments. How did your chosen reactor modifications effect dispersion?

4. Report the values of t⋆ at F = 0.1 for each of your experiments. Do they meet your expectations?

5. Evaluate whether there is any evidence of “dead volumes” or “short circuiting” in your reactor.

6. Make a recommendation for the design of a full scale chlorine contact tank. As part of your recommendation discuss the parameter you chose to vary as part of your experimentation and what the optimal value was determined to be.


### Appendix
```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.utility as ut
import numpy as np
import matplotlib.pyplot as plt

#The following file is from a CMFR
CMFR_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/30mgL_CMFR.tsv'
# find the row after the last note in the file. This assumes that the last note marks the beginning of the test.
#epa.notes(CMFR_path)

#CMFR_firstrow = epa.notes(CMFR_path).last_valid_index() + 1
#print(CMFR_firstrow)

#I eliminate the beginning of the data file because this is a CMFR and the
#first data was taken before the dye reached the sensor. Note that eliminating
#some data from the beginning of the data file will not change the analysis
#except in the estimate of the initial tracer mass.#
CMFR_firstrow = 1
CMFR_time_data = (epa.column_of_time(CMFR_path,CMFR_firstrow,-1)).to(u.s)

CMFR_concentration_data = epa.column_of_data(CMFR_path,CMFR_firstrow,1,-1,'mg/L')

#I don't actually know the values that follow. I'm guessing.
#You should use real measured values!#
CMFR_V = 2.54*u.L
CMFR_Q = 380 * u.mL/u.min

#here we set estimates that we will use as starting values for the curve fitting
CMFR_theta_hydraulic = (CMFR_V/CMFR_Q).to(u.s)
CMFR_C_bar_guess = np.max(CMFR_concentration_data)

#The Solver_CMFR_N will return the initial tracer concentration,
#residence time, and number of reactors in series.
#This experiment was for a single reactor and so we expect N to be 1!
CMFR_CMFR = epa.Solver_CMFR_N(CMFR_time_data, CMFR_concentration_data, CMFR_theta_hydraulic, CMFR_C_bar_guess)
#use dot notation to get the 3 elements of the tuple that are in CMFR.

print('The model estimated mass of tracer injected was',ut.round_sf(CMFR_CMFR.C_bar*CMFR_V ,2) )
print('The model estimate of the number of reactors in series was', CMFR_CMFR.N)
print('The tracer residence time was',ut.round_sf(CMFR_CMFR.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(CMFR_CMFR.theta/CMFR_theta_hydraulic).magnitude)

#create a model curve given the curve fit parameters.

CMFR_CMFR_model = CMFR_CMFR.C_bar * epa.E_CMFR_N(CMFR_time_data/CMFR_CMFR.theta,CMFR_CMFR.N)
plt.plot(CMFR_time_data.to(u.min), CMFR_concentration_data.to(u.mg/u.L),'r')
plt.plot(CMFR_time_data.to(u.min), CMFR_CMFR_model,'b')

plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model'])
plt.savefig('CMFR.png', bbox_inches = 'tight')
plt.show()

#Load a data file for a reactor with baffles.

one_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/2%20BAFFLES_CMFR.xls'

#one_baffle_firstrow = epa.notes(one_baffle_path).last_valid_index() + 1
one_baffle_firstrow = 1
one_baffle_time_data = (epa.column_of_time(one_baffle_path,one_baffle_firstrow,-1)).to(u.s)
one_baffle_time_data
one_baffle_concentration_data = epa.column_of_data(one_baffle_path,one_baffle_firstrow,1,-1,'mg/L')
one_baffle_concentration_data
#I noticed that the initial concentration measured by the photometer wasn't
#zero. This suggests that there may have been a small air bubble in the
#photometer or perhaps there was some other anomoly that was causing the
#photometer to read a concentration that was higher than was actually present in
#the reactor. To correct for this I subtracted the initial concentration reading
#from all of the data. This was based on the assumption that the concentration
#measurement error persisted for the entire experiment.#

one_baffle_concentration_data = one_baffle_concentration_data - one_baffle_concentration_data[0]
one_baffle_V = 2.25*u.L
one_baffle_Q = 380 * u.mL/u.min
one_baffle_theta_hydraulic = (one_baffle_V/one_baffle_Q).to(u.s)
one_baffle_C_bar_guess = np.max(one_baffle_concentration_data)/2
#use solver to get the CMFR parameters
one_baffle_CMFR = epa.Solver_CMFR_N(one_baffle_time_data, one_baffle_concentration_data, one_baffle_theta_hydraulic, one_baffle_C_bar_guess)
one_baffle_CMFR.C_bar
one_baffle_CMFR.N
one_baffle_CMFR.theta.to(u.s)

#Create the CMFR model curve based on the scipy.optimize curve_fit
#parameters. We do this with dimensions so that we can plot both models and
#the data on the same graph. If we did this in dimensionless space it wouldn't
#be possible to plot everything on the same plot because the values used to
#create dimensionless time and dimensionless concentration are different for
#the two models.
one_baffle_CMFR_model = (one_baffle_CMFR.C_bar*epa.E_CMFR_N(four_baffle_time_data/one_baffle_CMFR.theta, one_baffle_CMFR.N)).to(u.mg/u.L)

#use solver to get the advection dispersion parameters
one_baffle_AD = epa.Solver_AD_Pe(one_baffle_time_data, one_baffle_concentration_data, one_baffle_theta_hydraulic, one_baffle_C_bar_guess)
one_baffle_AD.C_bar
one_baffle_AD.Pe
one_baffle_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(one_baffle_AD.C_bar*one_baffle_V ,2) )
print('The model estimate of the Peclet number was', one_baffle_AD.Pe)
print('The tracer residence time was',ut.round_sf(one_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(one_baffle_AD.theta/one_baffle_theta_hydraulic).magnitude)

#Create the advection dispersion model curve based on the solver parameters
one_baffle_AD_model = (one_baffle_AD.C_bar*epa.E_Advective_Dispersion((one_baffle_time_data/one_baffle_AD.theta).to_base_units(), one_baffle_AD.Pe)).to(u.mg/u.L)

#Plot the data and the two model curves.
plt.plot(one_baffle_time_data.to(u.s), one_baffle_concentration_data.to(u.mg/u.L),'r')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_CMFR_model,'b')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_AD_model,'g')
plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model', 'AD Model'])
plt.savefig('2_baffles.png', bbox_inches = 'tight')
plt.show()


#Load a data file for a reactor with baffles.

four_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/4%20BAFFLES.txt'
four_baffle_firstrow = 1
four_baffle_time_data = (epa.column_of_time(four_baffle_path,four_baffle_firstrow,-1)).to(u.s)
four_baffle_concentration_data = epa.column_of_data(four_baffle_path,four_baffle_firstrow,1,-1,'mg/L')
four_baffle_concentration_data
#I noticed that the initial concentration measured by the photometer wasn't
#zero. This suggests that there may have been a small air bubble in the
#photometer or perhaps there was some other anomoly that was causing the
#photometer to read a concentration that was higher than was actually present in
#the reactor. To correct for this I subtracted the initial concentration reading
#from all of the data. This was based on the assumption that the concentration
#measurement error persisted for the entire experiment.#

four_baffle_concentration_data = four_baffle_concentration_data - four_baffle_concentration_data[0]
four_baffle_V = 2.54*u.L
four_baffle_Q = 380 * u.mL/u.min
four_baffle_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
four_baffle_C_bar_guess = np.max(four_baffle_concentration_data)/2
#use solver to get the CMFR parameters
four_baffle_CMFR = epa.Solver_CMFR_N(four_baffle_time_data, four_baffle_concentration_data, four_baffle_theta_hydraulic, four_baffle_C_bar_guess)
four_baffle_CMFR.C_bar
four_baffle_CMFR.N
four_baffle_CMFR.theta.to(u.s)

#Create the CMFR model curve based on the scipy.optimize curve_fit
#parameters. We do this with dimensions so that we can plot both models and
#the data on the same graph. If we did this in dimensionless space it wouldn't
#be possible to plot everything on the same plot because the values used to
#create dimensionless time and dimensionless concentration are different for
#the two models.
four_baffle_CMFR_model = (four_baffle_CMFR.C_bar*epa.E_CMFR_N(four_baffle_time_data/four_baffle_CMFR.theta, four_baffle_CMFR.N)).to(u.mg/u.L)
#use solver to get the advection dispersion parameters
four_baffle_AD = epa.Solver_AD_Pe(four_baffle_time_data, four_baffle_concentration_data, four_baffle_theta_hydraulic, four_baffle_C_bar_guess)
four_baffle_AD.C_bar
four_baffle_AD.Pe
four_baffle_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(four_baffle_AD.C_bar*four_baffle_V ,2) )
print('The model estimate of the Peclet number was', four_baffle_AD.Pe)
print('The tracer residence time was',ut.round_sf(four_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(four_baffle_AD.theta/four_baffle_theta_hydraulic).magnitude)

#Create the advection dispersion model curve based on the solver parameters
four_baffle_AD_model = (four_baffle_AD.C_bar*epa.E_Advective_Dispersion((four_baffle_time_data/four_baffle_AD.theta).to_base_units(), four_baffle_AD.Pe)).to(u.mg/u.L)

#Plot the data and the two model curves.
plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'r')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'g')
plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model', 'AD Model'])
plt.savefig('four_baffles.png', bbox_inches = 'tight')
plt.show()


four_baffle_noholes_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/4%20baffles%20no%20holes.txt'
four_baffle_noholes_firstrow = 1
four_baffle_noholes_time_data = (epa.column_of_time(four_baffle_noholes_path,four_baffle_noholes_firstrow,-1)).to(u.s)
four_baffle_noholes_concentration_data = epa.column_of_data(four_baffle_noholes_path,four_baffle_noholes_firstrow,1,-1,'mg/L')
four_baffle_noholes_concentration_data
#I noticed that the initial concentration measured by the photometer wasn't
#zero. This suggests that there may have been a small air bubble in the
#photometer or perhaps there was some other anomoly that was causing the
#photometer to read a concentration that was higher than was actually present in
#the reactor. To correct for this I subtracted the initial concentration reading
#from all of the data. This was based on the assumption that the concentration
#measurement error persisted for the entire experiment.#

four_baffle_noholes_concentration_data = four_baffle_noholes_concentration_data - four_baffle_noholes_concentration_data[0]
four_baffle_noholes_V = 2.54*u.L
four_baffle_noholes_Q = 380 * u.mL/u.min
four_baffle_noholes_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
four_baffle_noholes_C_bar_guess = np.max(four_baffle_noholes_concentration_data)/2
#use solver to get the CMFR parameters
four_baffle_noholes_CMFR = epa.Solver_CMFR_N(four_baffle_noholes_time_data, four_baffle_noholes_concentration_data, four_baffle_noholes_theta_hydraulic, four_baffle_noholes_C_bar_guess)
four_baffle_noholes_CMFR.C_bar
four_baffle_noholes_CMFR.N
four_baffle_noholes_CMFR.theta.to(u.s)

#Create the CMFR model curve based on the scipy.optimize curve_fit
#parameters. We do this with dimensions so that we can plot both models and
#the data on the same graph. If we did this in dimensionless space it wouldn't
#be possible to plot everything on the same plot because the values used to
#create dimensionless time and dimensionless concentration are different for
#the two models.
four_baffle_noholes_CMFR_model = (four_baffle_noholes_CMFR.C_bar*epa.E_CMFR_N(four_baffle_noholes_time_data /four_baffle_noholes_CMFR.theta, four_baffle_noholes_CMFR.N)).to(u.mg/u.L)
#use solver to get the advection dispersion parameters
four_baffle_noholes_AD = epa.Solver_AD_Pe(four_baffle_noholes_time_data, four_baffle_noholes_concentration_data, four_baffle_noholes_theta_hydraulic, four_baffle_noholes_C_bar_guess)
four_baffle_noholes_AD.C_bar
four_baffle_noholes_AD.Pe
four_baffle_noholes_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(four_baffle_noholes_AD.C_bar*four_baffle_noholes_V ,2) )
print('The model estimate of the Peclet number was', four_baffle_noholes_AD.Pe)
print('The tracer residence time was',ut.round_sf(four_baffle_noholes_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(four_baffle_noholes_AD.theta/four_baffle_noholes_theta_hydraulic).magnitude)

#Create the advection dispersion model curve based on the solver parameters
four_baffle_noholes_AD_model = (four_baffle_noholes_AD.C_bar*epa.E_Advective_Dispersion((four_baffle_noholes_time_data/four_baffle_noholes_AD.theta).to_base_units(), four_baffle_noholes_AD.Pe)).to(u.mg/u.L)

#Plot the data and the two model curves.
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_concentration_data.to(u.mg/u.L),'r')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_CMFR_model,'b')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_AD_model,'g')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'c')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'y')
plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye No holes','CMFR Model q', 'AD Model q','Measured dye Holes','CMFR Model 2', 'AD Model 2'])
plt.savefig('four_baffle_noholes.png', bbox_inches = 'tight')
plt.show()




seven_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/7%20baffles.txt'
seven_baffle_firstrow = 1
seven_baffle_time_data = (epa.column_of_time(seven_baffle_path,seven_baffle_firstrow,-1)).to(u.s)
seven_baffle_concentration_data = epa.column_of_data(seven_baffle_path,seven_baffle_firstrow,1,-1,'mg/L')
seven_baffle_concentration_data
#I noticed that the initial concentration measured by the photometer wasn't
#zero. This suggests that there may have been a small air bubble in the
#photometer or perhaps there was some other anomoly that was causing the
#photometer to read a concentration that was higher than was actually present in
#the reactor. To correct for this I subtracted the initial concentration reading
#from all of the data. This was based on the assumption that the concentration
#measurement error persisted for the entire experiment.#

seven_baffle_concentration_data = seven_baffle_concentration_data - seven_baffle_concentration_data[0]
seven_baffle_V = 2.54*u.L
seven_baffle_Q = 380 * u.mL/u.min
seven_baffle_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
seven_baffle_C_bar_guess = np.max(seven_baffle_concentration_data)/2
#use solver to get the CMFR parameters
seven_baffle_CMFR = epa.Solver_CMFR_N(seven_baffle_time_data, seven_baffle_concentration_data, seven_baffle_theta_hydraulic, seven_baffle_C_bar_guess)
seven_baffle_CMFR.C_bar
seven_baffle_CMFR.N
seven_baffle_CMFR.theta.to(u.s)

#Create the CMFR model curve based on the scipy.optimize curve_fit
#parameters. We do this with dimensions so that we can plot both models and
#the data on the same graph. If we did this in dimensionless space it wouldn't
#be possible to plot everything on the same plot because the values used to
#create dimensionless time and dimensionless concentration are different for
#the two models.
seven_baffle_CMFR_model = (seven_baffle_CMFR.C_bar*epa.E_CMFR_N(seven_baffle_time_data /seven_baffle_CMFR.theta, seven_baffle_CMFR.N)).to(u.mg/u.L)
#use solver to get the advection dispersion parameters
seven_baffle_AD = epa.Solver_AD_Pe(seven_baffle_time_data, seven_baffle_concentration_data, seven_baffle_theta_hydraulic, seven_baffle_C_bar_guess)
seven_baffle_AD.C_bar
seven_baffle_AD.Pe
seven_baffle_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(seven_baffle_AD.C_bar*seven_baffle_V ,2) )
print('The model estimate of the Peclet number was', seven_baffle_AD.Pe)
print('The tracer residence time was',ut.round_sf(seven_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(seven_baffle_AD.theta/seven_baffle_theta_hydraulic).magnitude)

#Create the advection dispersion model curve based on the solver parameters
seven_baffle_AD_model = (seven_baffle_AD.C_bar*epa.E_Advective_Dispersion((seven_baffle_time_data/seven_baffle_AD.theta).to_base_units(), seven_baffle_AD.Pe)).to(u.mg/u.L)

#Plot the data and the two model curves.
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_concentration_data.to(u.mg/u.L),'r')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_CMFR_model,'b')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_AD_model,'g')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'c')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'y')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_concentration_data.to(u.mg/u.L),'k')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_CMFR_model,'m')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_AD_model,'b')
plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye seven baffles','CMFR Model q', 'AD Model q','Measured dye Holes','CMFR Model 2', 'AD Model 2','Measured dye No holes','CMFR Model q', 'AD Model q'])
plt.savefig('seven_baffle.png', bbox_inches = 'tight')
plt.show()




pfr3_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/pfr%203.txt'
pfr3_firstrow = 1
pfr3_time_data = (epa.column_of_time(pfr3_path,pfr3_firstrow,-1)).to(u.s)
pfr3_concentration_data = epa.column_of_data(pfr3_path,pfr3_firstrow,1,-1,'mg/L')
#I noticed that the initial concentration measured by the photometer wasn't
#zero. This suggests that there may have been a small air bubble in the
#photometer or perhaps there was some other anomoly that was causing the
#photometer to read a concentration that was higher than was actually present in
#the reactor. To correct for this I subtracted the initial concentration reading
#from all of the data. This was based on the assumption that the concentration
#measurement error persisted for the entire experiment.#

pfr3_concentration_data = pfr3_concentration_data - pfr3_concentration_data[0]
length = 12.5*u.ft
ID = 3/8*u.inch
pfr3_V = length*(3.1415*(ID)**2)/4*u.L
pfr3_Q = 380 * u.mL/u.min
pfr3_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
pfr3_C_bar_guess = np.max(pfr3_concentration_data)/2
#use solver to get the CMFR parameters
pfr3_CMFR = epa.Solver_CMFR_N(pfr3_time_data, pfr3_concentration_data, pfr3_theta_hydraulic, pfr3_C_bar_guess)
pfr3_CMFR.C_bar
pfr3_CMFR.N
pfr3_CMFR.theta.to(u.s)

#Create the CMFR model curve based on the scipy.optimize curve_fit
#parameters. We do this with dimensions so that we can plot both models and
#the data on the same graph. If we did this in dimensionless space it wouldn't
#be possible to plot everything on the same plot because the values used to
#create dimensionless time and dimensionless concentration are different for
#the two models.
pfr3_CMFR_model = (pfr3_CMFR.C_bar*epa.E_CMFR_N(pfr3_time_data /pfr3_CMFR.theta, pfr3_CMFR.N)).to(u.mg/u.L)
#use solver to get the advection dispersion parameters
pfr3_AD = epa.Solver_AD_Pe(pfr3_time_data, pfr3_concentration_data, pfr3_theta_hydraulic, pfr3_C_bar_guess)
pfr3_AD.C_bar
pfr3_AD.Pe
pfr3_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(pfr3_AD.C_bar*pfr3_V ,2) )
print('The model estimate of the Peclet number was', pfr3_AD.Pe)
print('The tracer residence time was',ut.round_sf(pfr3_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(pfr3_AD.theta/pfr3_theta_hydraulic).magnitude)

#Create the advection dispersion model curve based on the solver parameters
pfr3_AD_model = (pfr3_AD.C_bar*epa.E_Advective_Dispersion((pfr3_time_data/pfr3_AD.theta).to_base_units(), pfr3_AD.Pe)).to(u.mg/u.L)

#Plot the data and the two model curves.
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
