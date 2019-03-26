# Reactor Characteristics
#### Ian Starnes and Barbara Oramah
##### Lab 5 Report, Group 6
##### Time (hr) Spent on Lab Report: Ian Starnes - 6  | Barbara Oramah - 6


### Table of Contents

- [Introduction](#Introduction)
- [Objective](#Objective)
- [Procedure](#Procedure)
- [Data Analysis](#Data-analysis)
- [Conclusion](#Conclusion)
- [Suggestions](#Suggestions)
- [Appendix](#Appendix)

#### Introduction

Reactors can be found in chemical, biological and physical processes all around the environment. Reactors can be defined by as real or imaginary boundaries and closed and open, such as a lake or a section of a river, respectively.

There are different types of reactor models. The most common idealised models are the batch reactor model, completely mixed flow reactor (CMFR) model, flow with dispersion (FDR) model and plug flow reactor (PFR) model. Important parameters for the reactors are the mixing level and residence time, which affect the degree of process reaction that occurs.

#### Objective
The objective for this experiment was to create different set-up to curate experimental data to see the different characteristics of a reactor. The measured data is compared with a CMFR model as well as an advection dispersion model to see how the models align. The analysis of this data will help in designing a chlorine contact tank which should optimize the contact time between the chlorine and any pathogens in the water.

#### Procedure
The detailed procedure for the lab can be found [here](https://monroews.github.io/EnvEngLabTextbook/Reactor_Characteristics/Reactor_Characteristics.html#procedures)

Following the cited lab procedure, we ran 6 different reactor experiments over a span of 2 lab sessions.

From test 1 to test 5, all the experiments used a consistent reactor volume of 0.00254 m3. Additionally the flow rate was kept the same at 380 mL/min (100 RPM).


###### Test 1: CMFR 
Test 1, the reactor is modeled as a CMFR with a stirrer in the center on a high speed. The concentration for the tracer is 100 g/L and the volume added was 765 microliters.

###### Test 2: Two baffles with 2 holes of 7.74 mm diameter (taped)

Test 2 is a reactor where we used 2 baffles that was taped around the edges with Gorilla Glue Tape. The baffles were placed on the opposing side of the reactor at equidistances. The tape was used to ensure that the dye only travelled through the holes in the baffles. The concentration for the tracer is 100 g/L and the volume added was 400 microliters.


###### Test 3: 4 baffles with 2 holes of 7.74 mm diameter (taped)

Test 3 has the same set up as test 2 however this experiment used 4 baffles as opposed to 2. The red dye that was added however had a concentration of 10g/L and we added the tracer volume of 800 microliters.

###### Test 4: 4 baffles no hole

Test 4 used 4 baffles that had no holes and were 14 cm in width. The reactor has a width of 15.3 cm, therefore was 1.3 cm of space. The baffles were placed on alternating sides of the reactor and were taped with the Gorilla Glue Tape. The tracer concentration used was 10 g/L and a volume of 800 microliters was added.


###### Test 5: 7 random baffles but evenly spaced (no tape)

Test 5 consisted of seven baffles that varied in different number of holes and diameters. They were evenly spaced within the reactor and were not taped down. The tracer concentration used was 10 g/L and a volume of 800 microliters was added.


#### Data Analysis

A total of 7 different test were run. This allows for an abundance of data to compare. The data will be presented individually and at the end of the data analysis is where differences and similarities of different models will be more carefully analyised.


1. Use multivariable nonlinear regression to obtain the best fit between the experimental data and the two models by minimizing the sum of the squared errors. Use epa.Solver_AD_Pe and epa.Solver_CMFR_N. These functions will minimize the error by varying the values of average residence time, (mass of tracer/reactor volume), and either the number of CMFR in series or the Peclet number.

2. Generate a plot showing the experimental data as points and the model results as thin lines for each of your experiments. Explain which model fits best and discuss those results based on your expectations.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/CMFR.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 1 </b>: CMFR - Test 1
</p>

The CMFR model almost perfectly agrees with the measured dye effluent concentration as expected.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/2%20baffles.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 2 </b>: Two Baffles - Test 2
</p>


For the experiment with two baffles with alternating orientation, with 2 holes of 7.74 mm diameter under the water line, the data is modeled most accurately by the CMFR model. This is seen in the beginning of the experiment, where the CMFR model more closely aligns with the measured data during the initial spike in dye in the effluent.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/four_baffles.png?raw=true" heights=110 width=427> </p>

<p align="center"> <b>Figure 3 </b>: Four Baffles - Test 3 </p>

For the experiment with four baffles with alternating orientation, again with 2 holes of 7.74 mm diameter under the water line, the data is modeled well by both the CMFR and AD model. However, the CMFR model expected the dye to leave the reactor slightly more quickly that it did.


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/four_baffle_no_holes.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 4 </b>: Four Baffles with no holes - Test 4
</p>


For this experiment four baffles of a different type were used. These baffles forced the flow to go around the baffle on alternating sides of the reactor. The AD model more accurately represents the measured dye for this reactor.

Observations: There are some dead zones in this test. The dye is not completely mixed in the reactor

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/sevenbaffle.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 5 </b>: Seven Baffles - Test 5
</p>

In this experiment a random assortment of seven baffles was used. Again, the AD model more accurately fits the measured data.

Observations: we observed some side slip through the edges of the baffles because we did not tape the sides

3. Compare the trends in the estimated values of N and Pe across your set of experiments. How did your chosen reactor modifications effect dispersion?

CMFR - Test 1:
The model estimate of the number of reactors in series was 1.04

Two Baffles - Test 2:
The model estimate of the Peclet number was 2.46
The model estimate of the number of reactors in series was 2.26

Four Baffles - Test 3:
The model estimate of the Peclet number was 30.90
The model estimate of the number of reactors in series was 16.47

Four Baffles no holes - Test 4:
The model estimate of the Peclet number was 5.68
The model estimate of the number of reactors in series was 4.00

Seven Random Baffles - Test 5:
The model estimate of the Peclet number was 1.77
The model estimate of the number of reactors in series was 2.11

4. Report the values of t⋆ at F = 0.1 for each of your experiments. Do they meet your expectations?

The time for 10% of the pulse to arrive at the effluent of a CMFR is approximately 0.1 t⋆

CMFR - Test 1:
The value of t_star at F=0.1 was  0.085 dimensionless

Two Baffles - Test 2:
The value of t_star at F=0.1 was  0.35 dimensionless

Four Baffles - Test 3:
The value of t_star at F=0.1 was  0.64 dimensionless

Four Baffles no holes - Test 4:
The value of t_star at F=0.1 was  0.44 dimensionless

Seven Random Baffles - Test 5:
The value of t_star at F=0.1 was  0.32 dimensionless

5. Evaluate whether there is any evidence of “dead volumes” or “short circuiting” in your reactor.

6. Make a recommendation for the design of a full scale chlorine contact tank. As part of your recommendation discuss the parameter you chose to vary as part of your experimentation and what the optimal value was determined to be.




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
import math
from math import pi
from scipy import integrate
from sklearn import preprocessing

# CMFR Test 1

CMFR_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/30mgL_CMFR.tsv'

CMFR_firstrow = 1
CMFR_time_data = (epa.column_of_time(CMFR_path,CMFR_firstrow,-1)).to(u.s)

CMFR_concentration_data = epa.column_of_data(CMFR_path,CMFR_firstrow,1,-1,'mg/L')

CMFR_V = 2.54*u.L
CMFR_Q = 380 * u.mL/u.min

CMFR_theta_hydraulic = (CMFR_V/CMFR_Q).to(u.s)
CMFR_C_bar_guess = np.max(CMFR_concentration_data)

CMFR_CMFR = epa.Solver_CMFR_N(CMFR_time_data, CMFR_concentration_data, CMFR_theta_hydraulic, CMFR_C_bar_guess)

CMFR_tr=100 * u.g/u.L
CMFR_vtr=0.000765 * u.L
t_star_CMFR = CMFR_time_data/CMFR_theta_hydraulic
CMFR_E = ((CMFR_concentration_data*CMFR_V)/(CMFR_CMFR.C_bar))
CMFR_F = integrate.cumtrapz(CMFR_E,t_star_CMFR, initial=0)
CMFR_F = CMFR_F/CMFR_F[len(CMFR_F)-1]
i=0
j=0
while j==0:
  if CMFR_F[i] > 0.1 :
    j=i
  i+=1
CMFR_time_0_1=t_star_CMFR[j]

print('The model estimated mass of tracer injected was',ut.round_sf(CMFR_CMFR.C_bar*CMFR_V ,2) )
print('The model estimate of the number of reactors in series was', CMFR_CMFR.N)
print('The tracer residence time was',ut.round_sf(CMFR_CMFR.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(CMFR_CMFR.theta/CMFR_theta_hydraulic).magnitude)
print('The value of t_star at F=0.1 was ',ut.round_sf(CMFR_time_0_1,2))

CMFR_CMFR_model = CMFR_CMFR.C_bar * epa.E_CMFR_N(CMFR_time_data/CMFR_CMFR.theta,CMFR_CMFR.N)
plt.plot(CMFR_time_data.to(u.min), CMFR_concentration_data.to(u.mg/u.L),'r.')
plt.plot(CMFR_time_data.to(u.min), CMFR_CMFR_model,'b')

plt.xlabel(r'$time (min)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model'])
plt.savefig('CMFR.png', bbox_inches = 'tight')
plt.show()

# 2 Baffles Holes on Alternating Sides - Test 2

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

one_baffle_tr= 100 * u.g/u.L
one_baffle_vtr=0.000765 * u.L
t_star_one_baffle = one_baffle_time_data/one_baffle_theta_hydraulic
one_baffle_E = ((one_baffle_concentration_data*one_baffle_V)/(one_baffle_CMFR.C_bar))
one_baffle_F = integrate.cumtrapz(one_baffle_E,t_star_one_baffle, initial=0)
one_baffle_F = one_baffle_F/one_baffle_F[len(one_baffle_F)-1]
i=0
j=0
while j==0:
  if one_baffle_F[i] > 0.1 :
    j=i
  i+=1
one_baffle_time_0_1=t_star_one_baffle[j]

print('The model estimated mass of tracer injected was',ut.round_sf(one_baffle_AD.C_bar*one_baffle_V ,2) )
print('The model estimate of the Peclet number was', one_baffle_AD.Pe)
print('The model estimate of the number of reactors in series was', one_baffle_CMFR.N)
print('The tracer residence time was',ut.round_sf(one_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(one_baffle_AD.theta/one_baffle_theta_hydraulic).magnitude)
print('The value of t_star at F=0.1 was ',ut.round_sf(one_baffle_time_0_1,2))


one_baffle_AD_model = (one_baffle_AD.C_bar*epa.E_Advective_Dispersion((one_baffle_time_data/one_baffle_AD.theta).to_base_units(), one_baffle_AD.Pe)).to(u.mg/u.L)


plt.plot(one_baffle_time_data.to(u.s), one_baffle_concentration_data.to(u.mg/u.L),'r.')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_CMFR_model,'b')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_AD_model,'g')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model', 'AD Model'])
plt.savefig('2 baffles.png', bbox_inches = 'tight')
plt.show()

# 4 Baffles hole on alternating sides - Test 3

four_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/4%20BAFFLES.txt'
four_baffle_firstrow = 1
four_baffle_time_data = (epa.column_of_time(four_baffle_path,four_baffle_firstrow,-1)).to(u.s)
four_baffle_concentration_data = epa.column_of_data(four_baffle_path,four_baffle_firstrow,1,-1,'mg/L')

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

four_baffle_tr=100 * u.g/u.L
four_baffle_vtr=0.000765 * u.L
t_star_four_baffle = four_baffle_time_data/four_baffle_theta_hydraulic
four_baffle_E = ((four_baffle_concentration_data*four_baffle_V)/(four_baffle_CMFR.C_bar))
four_baffle_F = integrate.cumtrapz(four_baffle_E,t_star_four_baffle, initial=0)
four_baffle_F = four_baffle_F/four_baffle_F[len(four_baffle_F)-1]
i=0
j=0
while j==0:
  if four_baffle_F[i] > 0.1 :
    j=i
  i+=1
four_baffle_time_0_1=t_star_four_baffle[j]

print('The model estimated mass of tracer injected was',ut.round_sf(four_baffle_AD.C_bar*four_baffle_V ,2) )
print('The model estimate of the Peclet number was', four_baffle_AD.Pe)
print('The model estimate of the number of reactors in series was', four_baffle_CMFR.N)
print('The tracer residence time was',ut.round_sf(four_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(four_baffle_AD.theta/four_baffle_theta_hydraulic).magnitude)
print('The value of t_star at F=0.1 was ',ut.round_sf(four_baffle_time_0_1,2))

four_baffle_AD_model = (four_baffle_AD.C_bar*epa.E_Advective_Dispersion((four_baffle_time_data/four_baffle_AD.theta).to_base_units(), four_baffle_AD.Pe)).to(u.mg/u.L)


plt.plot(four_baffle_time_data.to(u.s), four_baffle_concentration_data.to(u.mg/u.L),'r.')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_CMFR_model,'b')
plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model,'g')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye','CMFR Model', 'AD Model'])
plt.savefig('four_baffles.png', bbox_inches = 'tight')
plt.show()

# 4 Baffles no holes gap on alternating sides - Test 4

four_baffle_noholes_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/4%20baffles%20no%20holes.txt'
four_baffle_noholes_firstrow = 1
four_baffle_noholes_time_data = (epa.column_of_time(four_baffle_noholes_path,four_baffle_noholes_firstrow,-1)).to(u.s)
four_baffle_noholes_concentration_data = epa.column_of_data(four_baffle_noholes_path,four_baffle_noholes_firstrow,1,-1,'mg/L')


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

four_baffle_noholes_tr=100 * u.g/u.L
four_baffle_noholes_vtr=0.000765 * u.L
t_star_four_baffle_noholes = four_baffle_noholes_time_data/four_baffle_noholes_theta_hydraulic
four_baffle_noholes_E = ((four_baffle_noholes_concentration_data*four_baffle_noholes_V)/(four_baffle_noholes_CMFR.C_bar))
four_baffle_noholes_F = integrate.cumtrapz(four_baffle_noholes_E,t_star_four_baffle_noholes, initial=0)
four_baffle_noholes_F = four_baffle_noholes_F/four_baffle_noholes_F[len(four_baffle_noholes_F)-1]
i=0
j=0
while j==0:
  if four_baffle_noholes_F[i] > 0.1 :
    j=i
  i+=1
four_baffle_noholes_time_0_1=t_star_four_baffle_noholes[j]

print('The model estimated mass of tracer injected was',ut.round_sf(four_baffle_noholes_AD.C_bar*four_baffle_noholes_V ,2) )
print('The model estimate of the Peclet number was', four_baffle_noholes_AD.Pe)
print('The model estimate of the number of reactors in series was', four_baffle_noholes_CMFR.N)
print('The tracer residence time was',ut.round_sf(four_baffle_noholes_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(four_baffle_noholes_AD.theta/four_baffle_noholes_theta_hydraulic).magnitude)
print('The value of t_star at F=0.1 was ',ut.round_sf(four_baffle_noholes_time_0_1,2))

four_baffle_noholes_AD_model = (four_baffle_noholes_AD.C_bar*epa.E_Advective_Dispersion((four_baffle_noholes_time_data/four_baffle_noholes_AD.theta).to_base_units(), four_baffle_noholes_AD.Pe)).to(u.mg/u.L)


plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_concentration_data.to(u.mg/u.L),'r.')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_CMFR_model,'b')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_AD_model,'g')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye No holes','CMFR Model', 'AD Model' ])
plt.savefig('four_baffle_no_holes.png', bbox_inches = 'tight')
plt.show()

# 7 Baffles of random baffles - Test 5

seven_baffle_path = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Reactor%20Characteristics%20Data/7%20baffles.txt'
seven_baffle_firstrow = 1
seven_baffle_time_data = (epa.column_of_time(seven_baffle_path,seven_baffle_firstrow,-1)).to(u.s)
seven_baffle_concentration_data = epa.column_of_data(seven_baffle_path,seven_baffle_firstrow,1,-1,'mg/L')

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

seven_baffle_tr=100 * u.g/u.L
seven_baffle_vtr=0.000765 * u.L
t_star_seven_baffle = seven_baffle_time_data/seven_baffle_theta_hydraulic
seven_baffle_E = ((seven_baffle_concentration_data*seven_baffle_V)/(seven_baffle_CMFR.C_bar))
seven_baffle_F = integrate.cumtrapz(seven_baffle_E,t_star_seven_baffle, initial=0)
seven_baffle_F = seven_baffle_F/seven_baffle_F[len(seven_baffle_F)-1]
i=0
j=0
while j==0:
  if seven_baffle_F[i] > 0.1 :
    j=i
  i+=1
seven_baffle_time_0_1=t_star_seven_baffle[j]

print('The model estimated mass of tracer injected was',ut.round_sf(seven_baffle_AD.C_bar*seven_baffle_V ,2) )
print('The model estimate of the Peclet number was', seven_baffle_AD.Pe)
print('The model estimate of the number of reactors in series was', seven_baffle_CMFR.N)
print('The tracer residence time was',ut.round_sf(seven_baffle_AD.theta ,2))
print('The ratio of tracer to hydraulic residence time was',(seven_baffle_AD.theta/seven_baffle_theta_hydraulic).magnitude)
print('The value of t_star at F=0.1 was ',ut.round_sf(seven_baffle_time_0_1,2))

seven_baffle_AD_model = (seven_baffle_AD.C_bar*epa.E_Advective_Dispersion((seven_baffle_time_data/seven_baffle_AD.theta).to_base_units(), seven_baffle_AD.Pe)).to(u.mg/u.L)

plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_concentration_data.to(u.mg/u.L),'r.')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_CMFR_model,'b')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_AD_model,'g')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Measured dye seven baffles','CMFR Model ', 'AD Model'])
plt.savefig('sevenbaffle.png', bbox_inches = 'tight')
plt.show()

# Plot comparing CMFR to Two baffles with normalized concentrations

plt.plot(CMFR_time_data.to(u.s), CMFR_CMFR_model,'')
plt.plot(one_baffle_time_data.to(u.s), one_baffle_CMFR_model*1.91,'')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Normailized Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['CMFR - CFMR model', 'Two Baffles - CMFR model'])
plt.savefig('Total.png', bbox_inches = 'tight')
plt.show()

# Plot comparing 4 baffles, 4 baffles no holes, and 7 baffles

plt.plot(four_baffle_time_data.to(u.s), four_baffle_AD_model*9,56,'')
plt.plot(four_baffle_noholes_time_data.to(u.s), four_baffle_noholes_AD_model*9.56, color='orange')
plt.plot(seven_baffle_time_data.to(u.s), seven_baffle_AD_model*9.56, color = 'red')
plt.xlabel(r'$time (seconds)$')
plt.ylabel(r'Concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(['Four Baffles - AD model', 'Four Baffles No Holes - AD model', 'Seven Random Baffles - AD model'])
plt.savefig('Total2.png', bbox_inches = 'tight')
plt.show()

```
