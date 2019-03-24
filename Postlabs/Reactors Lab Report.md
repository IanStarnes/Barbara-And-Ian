# Reactor Characteristics
#### Ian Starnes and Barbara Oramah
##### Lab 5 Report, Group 6
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

Reactors can be found in chemical, biological and physical processes all around the environment. Reactors are defined by a real or imaginary boundaries, such as a lake or a section of a river respectively.
There are different types of reactor models. The most common idealised models are the batch reactor model, completely mixed flow reactor (CMFR) model and plug flow reactor (PFR) model.  In this lab, the set-up for the experiment modelled both a CMFR and PFR.

#### Objective
The objective for this experiment was to create different set-up to curate experimental data to see the different characteristics of a reactor. The measured data is compared with a CMFR model as well as an advection dispersion model.

#### Procedure
The detailed procedure for the lab can be found [here](https://monroews.github.io/EnvEngLabTextbook/Reactor_Characteristics/Reactor_Characteristics.html#procedures)

[For your description of exactly what you did it would be best to add the details of what the actual masses and volumes were that you used.]: #
Following the lab procedure, we ran 6 different reactor experiments.

From test 1 to test 5, all the experiments use a consistent reactor volume of 0.00254 m3. Additionally the flow rate was kept the same at 380 mL/min (100 RPM).

Test 6 is where the experiment is modelled as a PFR. The length  of the tubing was 12.5 ft and the inner diameter 0.03125 ft. Thus the volume is calculated to be 0.000271 m3. We used a flow rate of ____.


###### Test 1: CMFR with no baffles
Test 1, the reactor is modelled as a CMFR with a stirrer in the center  on high speed.


Red dye concentration = 25.8 mg/L
Volume of red dye = 765 microliters


Mass of water remaining: 2537 g
Bucket alone = 560g
Bucket with water = 3097g

###### Test 2: Two baffles with 2 holes of 7.74 mm diameter (taped)

Test 2 is a reactor where we used 2 baffles that was taped around the edges with Gorilla Glue Tape. The baffles were placed on the opposing side of the reactor at equidistances. The tape was used to ensure that the dye only travelled through the holes in the baffles.

- opposing sides of the reactor
- funky data cut it at around 4:25 pm


Red dye concentration = 13 mg/L (from 100 g/L of red dye)
volume of red dye =  400 microliters


Bucket alone = 492g
Bucket with water = 3075g

3/13
Note to self: remember to turn on photometer so you can read your data

###### Test 3: 4 baffles with 2 holes of 7.74 mm diameter (taped)

Test 3 has the same set up as test 2 however this experiment used 4 baffles as opposed to 2.

Red dye concentration used = 10 g/L
Volume of red Dye = 800 microliters

Bucket alone =  557 g
Bucket with water = 3139 g

Final measured concentration = -1.02 mg/L

###### Test 4: 4 baffles no hole, 14 cm in length and the reactor is 15.3 cm )taped

Observations: There are some dead zones in this test. The dye is not completely mixed in the reactor


Red dye concentration used = 10 g/L
Volume of red Dye = 800 microliters

Bucket alone =  557 g
Bucket with water = 3099 g

Final measured concentration =  -1.08 mg/L


###### Test 5: 7 random baffles but evenly spaced (no tape)
baffles vary in different number of holes and diameters


Observations: we observed some side slip through the edges of the baffles because we did not tape the sides

Red dye conc used = 10 g/L
Volume of red Dye = 800 microliters

Bucket alone =  557 g
Bucket with water = 2985 g

Final measured concentration = -0.3 mg/L

###### Test 6: Plug Flow

Observations:

length = 12.5 ft
ID = 3/8th inch

Reactor Volume = m3
Red dye conc used = 10 g/L

Observation: test 1 we had the two pumps and then we removed the tubing that would pump in the influent.

Volume of red Dye = 1000 microliters
Diluted with 22 mL of water

flow rate?? assuming it was the same

there are three trials of plug flow

Final measured concentration = 0 mg/L (ran until there is no dye)

#### Data Analysis


1. Use multivariable nonlinear regression to obtain the best fit between the experimental data and the two models by minimizing the sum of the squared errors. Use epa.Solver_AD_Pe and epa.Solver_CMFR_N. These functions will minimize the error by varying the values of average residence time, (mass of tracer/reactor volume), and either the number of CMFR in series or the Peclet number.

2. Generate a plot showing the experimental data as points and the model results as thin lines for each of your experiments. Explain which model fits best and discuss those results based on your expectations.

3. Compare the trends in the estimated values of N and Pe across your set of experiments. How did your chosen reactor modifications effect dispersion?

4. Report the values of t⋆ at F = 0.1 for each of your experiments. Do they meet your expectations?

5. Evaluate whether there is any evidence of “dead volumes” or “short circuiting” in your reactor.

6. Make a recommendation for the design of a full scale chlorine contact tank. As part of your recommendation discuss the parameter you chose to vary as part of your experimentation and what the optimal value was determined to be.


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/CMFR.png?raw=true" heights=210 width=727> </p>

**Figure 1** CMFR

The CMFR model almost perfectly agrees with the measured dye effluent concentration as expected.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/2%20baffles.png?raw=true" heights=310 width=927> </p>

**Figure 2** Two Baffles

For the experiment with two baffles, with 2 holes of 7.74 mm diameter under the water line, the data is modeled most accurately by the CMFR model. This is seen in the beginning of the experiment, where the CMFR model more closely aligns with the measured data during the initial spike in dye in the effluent.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/four_baffles.png?raw=true" heights=310 width=927> </p>

**Figure 3** Four Baffles

For the experiment with four baffles, again with 2 holes of 7.74 mm diameter under the water line, the data is modeled most accurately by the AD model. This is seen


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/four_baffle_noholes.png?raw=true" heights=310 width=927> </p>

**Figure 4** Four Baffles with no holes

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/seven_baffle.png?raw=true" heights=310 width=927> </p>

**Figure 5** Seven Baffles

#### Conclusion
#### Suggestions
#### References

#### Appendix
```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.utility as ut
import numpy as np
import matplotlib.pyplot as plt
from math import pi


CMFR_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/30mgL_CMFR.tsv'

CMFR_firstrow = 1
CMFR_time_data = (epa.column_of_time(CMFR_path,CMFR_firstrow,-1)).to(u.s)

CMFR_concentration_data = epa.column_of_data(CMFR_path,CMFR_firstrow,1,-1,'mg/L')

CMFR_V = 2.54*u.L
CMFR_Q = 380 * u.mL/u.min


CMFR_theta_hydraulic = (CMFR_V/CMFR_Q).to(u.s)
CMFR_C_bar_guess = np.max(CMFR_concentration_data)

CMFR_CMFR = epa.Solver_CMFR_N(CMFR_time_data, CMFR_concentration_data, CMFR_theta_hydraulic, CMFR_C_bar_guess)

print('The model estimated mass of tracer injected was',ut.round_sf(CMFR_CMFR.C_bar*CMFR_V ,2) )
print('The model estimate of the number of reactors in series was', CMFR_CMFR.N)
print('The tracer residence time was',ut.round_sf(CMFR_CMFR.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(CMFR_CMFR.theta/CMFR_theta_hydraulic).magnitude)

CMFR_CMFR_model = CMFR_CMFR.C_bar * epa.E_CMFR_N(CMFR_time_data/CMFR_CMFR.theta,CMFR_CMFR.N)
plt.plot(CMFR_time_data.to(u.min), CMFR_concentration_data.to(u.mg/u.L),'r.')
plt.plot(CMFR_time_data.to(u.min), CMFR_CMFR_model,'b')

plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model'])
plt.savefig('CMFR.png', bbox_inches = 'tight')
plt.show()



one_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/2%20BAFFLES_CMFR.xls'

one_baffle_firstrow = 1
one_baffle_time_data = (epa.column_of_time(one_baffle_path,one_baffle_firstrow,-1)).to(u.s)
one_baffle_time_data
one_baffle_concentration_data = epa.column_of_data(one_baffle_path,one_baffle_firstrow,1,-1,'mg/L')
one_baffle_concentration_data

one_baffle_concentration_data = one_baffle_concentration_data - one_baffle_concentration_data[0]
one_baffle_V = 2.25*u.L
one_baffle_Q = 380 * u.mL/u.min
one_baffle_theta_hydraulic = (one_baffle_V/one_baffle_Q).to(u.s)
one_baffle_C_bar_guess = np.max(one_baffle_concentration_data)/2

one_baffle_CMFR = epa.Solver_CMFR_N(one_baffle_time_data, one_baffle_concentration_data, one_baffle_theta_hydraulic, one_baffle_C_bar_guess)
one_baffle_CMFR.C_bar
one_baffle_CMFR.N
one_baffle_CMFR.theta.to(u.s)


one_baffle_CMFR_model = (one_baffle_CMFR.C_bar*epa.E_CMFR_N(one_baffle_time_data/one_baffle_CMFR.theta, one_baffle_CMFR.N)).to(u.mg/u.L)

one_baffle_AD = epa.Solver_AD_Pe(one_baffle_time_data, one_baffle_concentration_data, one_baffle_theta_hydraulic, one_baffle_C_bar_guess)
one_baffle_AD.C_bar
one_baffle_AD.Pe
one_baffle_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(one_baffle_AD.C_bar*one_baffle_V ,2) )
print('The model estimate of the Peclet number was', one_baffle_AD.Pe)
print('The tracer residence time was',ut.round_sf(one_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(one_baffle_AD.theta/one_baffle_theta_hydraulic).magnitude)


one_baffle_AD_model = (one_baffle_AD.C_bar*epa.E_Advective_Dispersion((one_baffle_time_data/one_baffle_AD.theta).to_base_units(), one_baffle_AD.Pe)).to(u.mg/u.L)


plt.plot(one_baffle_time_data.to(u.s), one_baffle_concentration_data.to(u.mg/u.L),'r.')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_CMFR_model,'b')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_AD_model,'g')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model', 'AD Model'])
plt.savefig('2 baffles.png', bbox_inches = 'tight')
plt.show()


four_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/4%20BAFFLES.txt'
four_baffle_firstrow = 1
four_baffle_time_data = (epa.column_of_time(four_baffle_path,four_baffle_firstrow,-1)).to(u.s)
four_baffle_concentration_data = epa.column_of_data(four_baffle_path,four_baffle_firstrow,1,-1,'mg/L')
four_baffle_concentration_data


four_baffle_concentration_data = four_baffle_concentration_data - four_baffle_concentration_data[0]
four_baffle_V = 2.54*u.L
four_baffle_Q = 380 * u.mL/u.min
four_baffle_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
four_baffle_C_bar_guess = np.max(four_baffle_concentration_data)/2

four_baffle_CMFR = epa.Solver_CMFR_N(four_baffle_time_data, four_baffle_concentration_data, four_baffle_theta_hydraulic, four_baffle_C_bar_guess)
four_baffle_CMFR.C_bar
four_baffle_CMFR.N
four_baffle_CMFR.theta.to(u.s)


four_baffle_CMFR_model = (four_baffle_CMFR.C_bar*epa.E_CMFR_N(four_baffle_time_data/four_baffle_CMFR.theta, four_baffle_CMFR.N)).to(u.mg/u.L)

four_baffle_AD = epa.Solver_AD_Pe(four_baffle_time_data, four_baffle_concentration_data, four_baffle_theta_hydraulic, four_baffle_C_bar_guess)
four_baffle_AD.C_bar
four_baffle_AD.Pe
four_baffle_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(four_baffle_AD.C_bar*four_baffle_V ,2) )
print('The model estimate of the Peclet number was', four_baffle_AD.Pe)
print('The tracer residence time was',ut.round_sf(four_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(four_baffle_AD.theta/four_baffle_theta_hydraulic).magnitude)

four_baffle_AD_model = (four_baffle_AD.C_bar*epa.E_Advective_Dispersion((four_baffle_time_data/four_baffle_AD.theta).to_base_units(), four_baffle_AD.Pe)).to(u.mg/u.L)


plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'r.')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'g')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model', 'AD Model'])
plt.savefig('four_baffles.png', bbox_inches = 'tight')
plt.show()


four_baffle_noholes_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/4%20baffles%20no%20holes.txt'
four_baffle_noholes_firstrow = 1
four_baffle_noholes_time_data = (epa.column_of_time(four_baffle_noholes_path,four_baffle_noholes_firstrow,-1)).to(u.s)
four_baffle_noholes_concentration_data = epa.column_of_data(four_baffle_noholes_path,four_baffle_noholes_firstrow,1,-1,'mg/L')
four_baffle_noholes_concentration_data


four_baffle_noholes_concentration_data = four_baffle_noholes_concentration_data - four_baffle_noholes_concentration_data[0]
four_baffle_noholes_V = 2.54*u.L
four_baffle_noholes_Q = 380 * u.mL/u.min
four_baffle_noholes_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
four_baffle_noholes_C_bar_guess = np.max(four_baffle_noholes_concentration_data)/2

four_baffle_noholes_CMFR = epa.Solver_CMFR_N(four_baffle_noholes_time_data, four_baffle_noholes_concentration_data, four_baffle_noholes_theta_hydraulic, four_baffle_noholes_C_bar_guess)
four_baffle_noholes_CMFR.C_bar
four_baffle_noholes_CMFR.N
four_baffle_noholes_CMFR.theta.to(u.s)


four_baffle_noholes_CMFR_model = (four_baffle_noholes_CMFR.C_bar*epa.E_CMFR_N(four_baffle_noholes_time_data /four_baffle_noholes_CMFR.theta, four_baffle_noholes_CMFR.N)).to(u.mg/u.L)

four_baffle_noholes_AD = epa.Solver_AD_Pe(four_baffle_noholes_time_data, four_baffle_noholes_concentration_data, four_baffle_noholes_theta_hydraulic, four_baffle_noholes_C_bar_guess)
four_baffle_noholes_AD.C_bar
four_baffle_noholes_AD.Pe
four_baffle_noholes_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(four_baffle_noholes_AD.C_bar*four_baffle_noholes_V ,2) )
print('The model estimate of the Peclet number was', four_baffle_noholes_AD.Pe)
print('The tracer residence time was',ut.round_sf(four_baffle_noholes_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(four_baffle_noholes_AD.theta/four_baffle_noholes_theta_hydraulic).magnitude)


four_baffle_noholes_AD_model = (four_baffle_noholes_AD.C_bar*epa.E_Advective_Dispersion((four_baffle_noholes_time_data/four_baffle_noholes_AD.theta).to_base_units(), four_baffle_noholes_AD.Pe)).to(u.mg/u.L)


plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_concentration_data.to(u.mg/u.L),'r.')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_CMFR_model,'b')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_AD_model,'g')
#plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'c.')
#plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
#plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'y')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye No holes','CMFR Model q', 'AD Model q','Measured dye Holes','CMFR Model 2', 'AD Model 2'])
plt.savefig('four_baffle_noholes.png', bbox_inches = 'tight')
plt.show()


seven_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/7%20baffles.txt'
seven_baffle_firstrow = 1
seven_baffle_time_data = (epa.column_of_time(seven_baffle_path,seven_baffle_firstrow,-1)).to(u.s)
seven_baffle_concentration_data = epa.column_of_data(seven_baffle_path,seven_baffle_firstrow,1,-1,'mg/L')
seven_baffle_concentration_data

seven_baffle_concentration_data = seven_baffle_concentration_data - seven_baffle_concentration_data[0]
seven_baffle_V = 2.54*u.L
seven_baffle_Q = 380 * u.mL/u.min
seven_baffle_theta_hydraulic = (four_baffle_V/four_baffle_Q).to(u.s)
seven_baffle_C_bar_guess = np.max(seven_baffle_concentration_data)/2

seven_baffle_CMFR = epa.Solver_CMFR_N(seven_baffle_time_data, seven_baffle_concentration_data, seven_baffle_theta_hydraulic, seven_baffle_C_bar_guess)
seven_baffle_CMFR.C_bar
seven_baffle_CMFR.N
seven_baffle_CMFR.theta.to(u.s)

seven_baffle_CMFR_model = (seven_baffle_CMFR.C_bar*epa.E_CMFR_N(seven_baffle_time_data /seven_baffle_CMFR.theta, seven_baffle_CMFR.N)).to(u.mg/u.L)

seven_baffle_AD = epa.Solver_AD_Pe(seven_baffle_time_data, seven_baffle_concentration_data, seven_baffle_theta_hydraulic, seven_baffle_C_bar_guess)
seven_baffle_AD.C_bar
seven_baffle_AD.Pe
seven_baffle_AD.theta

print('The model estimated mass of tracer injected was',ut.round_sf(seven_baffle_AD.C_bar*seven_baffle_V ,2) )
print('The model estimate of the Peclet number was', seven_baffle_AD.Pe)
print('The tracer residence time was',ut.round_sf(seven_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(seven_baffle_AD.theta/seven_baffle_theta_hydraulic).magnitude)

seven_baffle_AD_model = (seven_baffle_AD.C_bar*epa.E_Advective_Dispersion((seven_baffle_time_data/seven_baffle_AD.theta).to_base_units(), seven_baffle_AD.Pe)).to(u.mg/u.L)

plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_concentration_data.to(u.mg/u.L),'r.')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_CMFR_model,'b')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_AD_model,'g')
#plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'c')
#plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
#plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'y')
#plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_concentration_data.to(u.mg/u.L),'k')
#plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_CMFR_model,'m')
#plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_AD_model,'b')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye seven baffles','CMFR Model q', 'AD Model q','Measured dye Holes','CMFR Model 2', 'AD Model 2','Measured dye No holes','CMFR Model q', 'AD Model q'])
plt.savefig('seven_baffle.png', bbox_inches = 'tight')
plt.show()

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
