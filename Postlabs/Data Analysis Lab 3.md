### Lab 3 Report, Group 6
#### Ian Starnes and Barbara Oramah
##### Time Spent on Lab: Ian Starnes - | Barbara Oramah - 10 hours


### Table of Contents

- [Introduction](#Introduction)
- [Observation](#Observation)
- [Procedure](#Procedure)
- [Data Analysis](#Data-analysis)
- [Conclusion](#Conclusion)
- [Suggestions](#Suggestions)
- [Appendix](#Appendix)


####Introduction

This lab is modelled to highlight how acid rain affects the acid neutralizing capacity (ANC) of lakes. Acid precipitation results from the combustion of fossil fuels which produce oxides of sulfur and nitrogen that react in the earth’s atmosphere to form sulfuric and nitric acid. [(1)](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html] ) The lab report shows the results from two seperate labs, [Lab 1](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#experimental-objectives) and [Lab 2](https://monroews.github.io/EnvEngLabTextbook/Acid_Neutralizing_Capacity/Acid_Neutralizing_Capacity.html#procedures). In Lab 1, the data collected were lake samples in 5 minutes intervals over a 20 minutes time period as an acid rain storage was pumped at a constant flow rate into a modelled lake. This was done in order see the change of pH over time and calculate ANC. In Lab 2, the samples collected in Lab 1 used to determine the ANC of each sample.

The observations of the lab were to be used as supporting evidence that that is possible.

The equations that were used for this lab report:

$$ANC_0 = [ANC_{out} - ANC_{in} (1-e^{-t/\theta})]e^{t/\theta}$$
This equation

$$ANC =2[CO_{3}^{2-}]+[HCO_{3}^{-}]+[OH^{-}]-[H^{+}]$$


**Why did you decide to do this experiment? Introduce your approach by explaining what needs to be done to meet your goal for your real world project. Explain what you hoped to learn through this research. How did you expect this experiment to guide your decisions about the real world project that you are working on?

This is the section where you can present the equations that you will be using. Format the equations using Latex to create a beautiful report."**

##### Objective
The goal for this lab is to gather experimental data to determine that remediation of lake can be obtained by increasing the ANC added so pH can be at an acceptable level and maintained over a desired period. The lab used sodium bicarbonate, NaHCO3, to be the source of ANC.

This was achieved by adding NaHCO3 to the lake surface and pumping acid rain at a pH of 3. The pH of the lake was then monitored over a 20 minutes time frame. 

#### Procedure
Provide an overview of the methods that you used in your investigation. The best procedures give an overview of the method with an explanation of why you used those methods. There is no need to restate the step-by-step procedures as outlined in the lab manual: it is sufficient to cite the lab manual and include information on any deviations from the manual procedures. When method development is part of the laboratory exercise, a detailed description of the methods should be included. Methods and procedures need to be detailed enough so that one of your classmates could duplicate your work.

#### Data Analysis

<p align="center"> <img src="https://github.com/barbaraoramah/my-CEE4530/blob/master/images/gran_t=0.png?raw=true" heights=310 width=927> </p>

**Figure 1:** Titration curve of the t=0 sample with 0.05 N HCl

The equivalent volume is found from the excel file of data from ProCoDA.
The equivalence point is defined as the point in the titration where titrant volume that has been added equals the “equivalent” volume (Ve). The equivalence point is a good way to determine ANC

 bicarbonate to carbonic acid is:

 $$ [HCO_3^-] -> [H_2CO_3]  $$



$${F_1} = \frac{{{V_S} + {V_T}}}{{{V_S}}}{\text{[}}{{\text{H}}^ + }{\text{]}}$$

The ANC can be calculated from the equivalent volume from $$ANC=\frac{V_e N_t }{V_s }$$



The calculated Ve (0.79 mL) is approximately the same as the ProCoDa Ve (0.813005  mL).

<p align="center"> <img src="https://github.com/barbaraoramah/my-CEE4530/blob/master/images/GranQ2.png?raw=true" heights=310 width=927> </p>

**Figure 2:** Gran Plot data from the titration curve of the t=0 sample



<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/ANCplotmeasured1.png?raw=true" heights=310 width=927> </p>

**Figure 3:** Measured ANC of the lake at different states


###Conclusion

We learned that by doubling the ANC added, the pH took a longer time to drop. This is because there was a higher buffer capacity, causing the lake to acidify at a slower rate. (from lab 2 data analysis)

###Suggestions

###Appendix
```Python
#Data Analysis - Question One code
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.utility as ut
from scipy import optimize
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from scipy import stats

Gran_data = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Lab%203%20Data/time_equals_0_Gran_Plot_v2.xls'
# The epa.Gran function imports data from your Gran data file as saved by ProCoDA.
# The epa.Gran function assigns all of the outputs in one statement
V_titrant, pH, V_Sample, Normality_Titrant, V_equivalent, ANC = epa.Gran(Gran_data)

# Now create a figure and plot the data and the line from the linear regression.
fig, ax = plt.subplots()


# plot the data as red circles
ax.plot(V_titrant, pH, 'r')
ax.set(xlabel= 'Titrant Volume (mL)')
ax.set(ylabel= 'pH')

ax.set(title = "Measured pH vs Titrant Volume")
ax.grid(True)
plt.ylim(2.5,6.5)
plt.xlim(0.2,1.5)

ax.annotate('Ve -->', xy=(0.813005 , 2.51), xytext=(0.68, 2.75),) #arrowprops=dict(facecolor='black', shrink=0.10),)

plt.axvline(x=V_equivalent.magnitude, color='g')
plt.text(0.45, 5.75, '<-- bicarbonate to')
plt.text(0.56, 5.5, 'carbonic acid')
plt.text(0.95, 3.0, '<-- approaching')
plt.text(1, 2.75, 'input pH')
# Here I save the file to my local harddrive. You will need to change this to work on your computer.
# We don't need the file type (png) here.
plt.savefig('gran_t=0-2')
plt.show()

```
```python
# Data Analysis - Question Two code
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.utility as ut
from scipy import optimize
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from scipy import stats

Gran_data = 'https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Lab%203%20Data/time_equals_0_Gran_Plot_v2.xls'
# The epa.Gran function imports data from your Gran data file as saved by ProCoDA.
# The epa.Gran function assigns all of the outputs in one statement
V_titrant, pH, V_Sample, Normality_Titrant, V_equivalent, ANC = epa.Gran(Gran_data)

V_equivalent

#Define the gran function.
def F1(V_sample,V_titrant,pH):
  return (V_sample + V_titrant)/V_sample * epa.invpH(pH)
#Create an array of the F1 values.
F1_data = F1(V_Sample,V_titrant,pH)
#By inspection I guess that there are 4 good data points in the linear region.
N_good_points = 3
#use scipy linear regression. Note that the we can extract the last n points from an array using the notation [-N:]
slope, intercept, r_value, p_value, std_err = stats.linregress(V_titrant[-N_good_points:],F1_data[-N_good_points:])
#reattach the correct units to the slope and intercept.
intercept = intercept*u.mole/u.L
slope = slope*(u.mole/u.L)/u.mL
V_eq = -intercept/slope
ANC_sample = V_eq*Normality_Titrant/V_Sample
print('The r value for this curve fit is', ut.round_sf(r_value,5))
print('The equivalent volume was', ut.round_sf(V_eq,2))
print('The acid neutralizing capacity was',ut.round_sf(ANC_sample.to(u.meq/u.L),2))

fig, ax = plt.subplots()
#The equivalent volume agrees well with the value calculated by ProCoDA.
#create an array of points to draw the linear regression line
x=[V_eq.magnitude,V_titrant[-1].magnitude ]
y=[0,(V_titrant[-1]*slope+intercept).magnitude]
#Now plot the data and the linear regression
ax.grid(True)

plt.plot(V_titrant, F1_data,'o')
plt.plot(x, y,'r')
plt.xlabel('Titrant Volume (mL)')
plt.ylabel('Gran function (mole/L)')
plt.legend(['data'])

plt.savefig('GranQ2-2.png')
plt.show()
```
```python
#Data Analysis - Question 3 code
from aguaclara.core.units import unit_registry as u
u.define("equivalent = mole = eq")
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from scipy import stats
data_set = "https://raw.githubusercontent.com/barbaraoramah/my-CEE4530/master/Lab%202%20-%20Acid%20Rain%20(1).txt"
import aguaclara.research.environmental_processes_analysis as epa
import math
from aguaclara import *

df = pd.read_csv(data_set,delimiter='\t')
df

data_set_0 = "https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Lab%203%20Data/time_equals_0_Gran_Plot_v2.xls"
data_set_5 = "https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Lab%203%20Data/time_equals_5_Gran_Plot_v2.xls"
data_set_10 = "https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Lab%203%20Data/time_equals_10_Gran_Plot.xls"
data_set_15 = "https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Lab%203%20Data/time_equals_15_Gran_Plot.xls"

V_titrant_0, pH_0, V_Sample_0, Normality_Titrant_0, V_equivalent_0, ANC_0 = epa.Gran(data_set_0)
V_titrant_5, pH_5, V_Sample_5, Normality_Titrant_5, V_equivalent_5, ANC_5  = epa.Gran(data_set_5)
V_titrant_10, pH_10, V_Sample_10, Normality_Titrant_10, V_equivalent_10, ANC_10  = epa.Gran(data_set_10)
V_titrant_15, pH_15, V_Sample_15, Normality_Titrant_15, V_equivalent_15, ANC_15 = epa.Gran(data_set_15)


mass_total = 4.563 * u.kg
mass_bucket = 0.592* u.kg
mass_water = mass_total-mass_bucket
print(mass_water)
volume_water = (mass_water/(1*u.kg/u.L))
print (volume_water)
ANC_in = -0.001*u.eq/u.L
pH_0 = 7.77
mass_nahco3 = 0.623 * u.g
mwt_nahco3 = 84* u.g/u.eq
conc_nahco3 = mass_nahco3/mwt_nahco3/volume_water
print(conc_nahco3)
ANC_0 = conc_nahco3
print(ANC_0)

flow_rate = 0.074/15*u.L/u.s
print(flow_rate)
theta = volume_water/flow_rate
print(theta)

 # Q2
time = epa.column_of_time(data_set,1,-1)
time
# note: you cannot print a list that has units, you must call it on its own. refer to 't' variable.
res_time = (time/theta).to('dimensionless')
res_time
ANC_0
ANC_out = ANC_0*(np.exp(-res_time))+ANC_in*(1-(np.exp(-res_time)))
ANC_out

lake_pH = df.iloc[:,1].values
ANC_cl=epa.ANC_closed(lake_pH,ANC_0)
ANC_cl = ANC_cl[0:1496]
ANC_cl

ANC_o = epa.ANC_open(lake_pH)
ANC_o = ANC_o[0:1496]
# Now create a figure and plot the data and the line from the linear regression.

fig, ax = plt.subplots()
ax.plot(time.to(u.min), ANC_out.to(u.meq/u.L), 'r', time.to(u.min), ANC_cl.to(u.meq/u.L), 'b', time.to(u.min), ANC_o.to(u.meq/u.L), 'g')

time_lake = np.array([0,5,10,15])*u.min
ANC_lake = np.array([(ANC_0.to(u.meq/u.L)).magnitude, (ANC_5.to(u.meq/u.L)).magnitude, (ANC_10.to(u.meq/u.L)).magnitude, (ANC_15.to(u.meq/u.L)).magnitude])

ax.plot(time_lake, ANC_lake, 'p')
# Add axis labels using the column labels from the dataframe
ax.set(xlabel= 'time (min)')
ax.set(ylabel= 'ANC (meq/L)')

ax.legend([ 'Conservative ANC','Nonvolatile ANC', 'Volatile ANC','ANC measured'])
ax.grid(True)
plt.ylim((-1,2))
plt.xlim(-0.2,25)

# Here I save the file to my local harddrive. You will need to change this to work on your computer.
# We don't need the file type (png) here.
plt.savefig('ANCplotmeasured')
plt.show()
```
