### Lab 3 Report, Group 6
#### Ian Starnes and Barbara Oramah
##### Time Spent on Lab Report: Ian Starnes - 10 hours | Barbara Oramah - 10 hours


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

This lab is modelled to highlight how acid rain affects the acid neutralizing capacity (ANC) of lakes. Acid precipitation results from the combustion of fossil fuels which produce oxides of sulfur and nitrogen that react in the earth’s atmosphere to form sulfuric and nitric acid. [(1)](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html] ) The lab report shows the results from two seperate labs, [Lab 1](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#experimental-objectives) and [Lab 2](https://monroews.github.io/EnvEngLabTextbook/Acid_Neutralizing_Capacity/Acid_Neutralizing_Capacity.html#procedures). In Lab 1, the data collected were lake samples in 5 minutes intervals over a 20 minutes time period as acid rain was pumped at a constant flow rate into a modelled lake. This was done in order see the change of pH over time and calculate ANC. In Lab 2, the samples collected in Lab 1 used to determine the ANC of each sample.

The observations of the lab were to be used as supporting evidence that this is applicable to real world lakes that are at risk of acidification from acid rain.

The equations that were used for this lab report:

$$ANC_0 = [ANC_{out} - ANC_{in} (1-e^{-t/\theta})]e^{t/\theta}$$

$$ANC =2[CO_{3}^{2-}]+[HCO_{3}^{-}]+[OH^{-}]-[H^{+}]$$

$${F_1} = \frac{{{V_S} + {V_T}}}{{{V_S}}}{\text{[}}{{\text{H}}^ + }{\text{]}}$$

 $$ANC=\frac{V_e N_t }{V_s }$$


#### Objective
The goal for this lab is to gather experimental data to show that remediation of lake can be obtained by increasing the ANC added so pH can be at an acceptable level and maintained over a desired period. The lab used sodium bicarbonate, NaHCO3, to be the source of ANC.

This was achieved by adding NaHCO3 to the lake surface and pumping acid rain at a pH of 3. The pH of the lake was then monitored over a 20 minutes time frame.

#### Procedure

The detailed procedure for Lab 1 can be found [here](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#procedures), and the Lab 2 procedure can be found [here](https://monroews.github.io/EnvEngLabTextbook/Acid_Neutralizing_Capacity/Acid_Neutralizing_Capacity.html#procedures).

In Lab 1, a pre-calculated mass of NaHCO3 was weighed out and added into a 4 L lake that had a stirrer bar inside. The stirrer bar was placed to model the lake as a completely mixed flow reactor, CMFR. A pH probe was placed in the lake to measure the change over a course of 20 minutes. In 5 minute intervals, a 100 mL sample of the lake was taken, labelled and set aside. The samples were kept to be used later in Lab 2.

In Lab 2, the 5 different samples were used to perform titrations in order to find the equivalent volume. The titrant used was 0.05 N HCl. The pH probe recorded the data necessary for ProCoDA to execute a Gran plot analysis.


#### Data Analysis

As mentioned previously, the NaHCO3 was used as the ANC supplement for the lake. Figure 1 clearly shows the pH levels decreasing over time after the ANC was added at t = 0. The area on the graph with the slower change in pH is because of the buffering effect of bicarbonate ions reacting with hydrogen ions to form carbonic acid.

$$  [HCO_3^- ] + [H^+] \rightarrow [H_2CO_3]$$

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/phplot01.png?raw=true" heights=310 width=927> </p>

**Figure 1:** pH versus hydraulic residence time.

If enough NaHCO3 were added to the lake to maintain an ANC greater than 50μeq/L for 3 residence times with the stirrer turned off, some of it will dissolve in the water while some of it will sink to the bottom due to the greater density of NaHCO3 than water. The water in which some of the NaHCO3 dissolved in more dense than the rest of the water and it will also sink. Therefore, as the acid is added the pH will be different throughout the lake. The pH will be lower at the source of the acid, at the top of the lake, and higher farther away, at the bottom of the lake. A second experiment was conducted in Lab 1 where the mass of NaHCO3 was doubled. By doubling the ANC added, the pH took a longer time to drop. This is because there was a higher buffer capacity, causing the lake to acidify at a slower rate.

CaCO3 is another carbonate that was tested to see the effect it would have for lake remediation. There were some problems that were encountered when CaCO3 was used to remediate acid rain in the lake. The solubility of the CaCO3 is very low in water. Therefore, it might not work to just add in a lot of CaCO3 at the same time. Instead, if a steady amount was added during the during of the acid rain, the solubility might not be a problem. If all of the CaCO3 is added at the same time, a lot of it will not go into solution but rather it will settle at the bottom. The effect of this is that the ANC will not use the full potential of the CaCO3 added.

The samples taken in the Lab 1 at five minute intervals were titrated to find the respective equivalence volume. Figure 2 displays the pH as a function of the volume of titrant added into the lake at t=0. At t=0, the sample is expected to be the most basic solution as NaHCO3 was just added, therefore the equivalent volume would be the largest. The equivalent volume is found from the excel file of data from ProCoDA. The equivalence point is defined as the point in the titration where titrant volume that has been added equals the “equivalent” volume (Ve). The equivalence point is a good way to determine ANC.


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/gran_t=0-line.png?raw=true" heights=310 width=927> </p>

**Figure 2:** Titration curve of the t=0 sample with 0.05 N HCl

There are 3 notable regions of figure 2. As labeled, the first region is where bicarbonate ions react with hydrogen ions and form carbonic acid. There is a steep slope that occurs at the equivalent volume and the third region is where the hydrogen ions contribute directly to the decrease in pH.

<p align="center"> <img src="https://github.com/barbaraoramah/my-CEE4530/blob/master/images/GranQ2.png?raw=true" heights=310 width=927> </p>

**Figure 3:** Gran Plot data from the titration curve of the t=0 sample

Similarly, figure 3 is a Gran plot at t=0. In the collected data, there is a first Gran function, F1, attributed to each data point. F1 is defined as a straight line. $${F_1} = \frac{{{V_S} + {V_T}}}{{{V_S}}}{\text{[}}{{\text{H}}^ + }{\text{]}}$$
The abscissa intercept is the equivalent volume. Both figure 1 and 2 clearly show that the ProCoDa equivalent volume for sample t = 0 is 0.831005 ml. This is basically the same as the calculated equivalent volume of 0.8310051 ml.
<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/ANCplotmeasured1.png?raw=true" heights=310 width=927> </p>

**Figure 4:** Measured ANC of the lake at different states



In figure 4, there are four different ANCs being plotted. The conservative ANC is from assuming the lake is a CMFR and ANC is a conservative species.

$$ANC_0 = [ANC_{out} - ANC_{in} (1-e^{-t/\theta})]e^{t/\theta}$$

$$ANC_{out}= \frac {ANC_0}{e^{t/\theta}} + ANC_{in} (1-e^{-t/\theta}) $$

The nonvolatile ANC is from the assumption that is no carbonates exchanged with the atmosphere during the experiment. The volatile ANC is from assuming there is carbonate exchange with the atmosphere and that the carbonates are at equilibrium with the atmosphere. The ANC measured points are the data points found from doing titrations of the lake samples at five minute intervals during the experiment. The graph shows that the ANC measured partially agrees with the conservative ANC model but agrees more with the nonvolatile ANC model.

### Conclusion

After looking at the titration curve for the t=0 sample, two regions of slow change in pH were observed. The first region corresponds to the buffering effect of HCO3 ions which becomes H2CO3 as it adds a proton, and the second corresponds to a region where hydrogen ions contribute directly to the change in pH. The equivalent volume is seen in the region of this graph where there is a steep change in pH. The calculated equivalent volume is  very close to the ProCoDa value and this is seen in the linear part of the Gran function. The measured ANC over the duration of the experiment most similar to the nonvolatile ANC model. This experiment showed us how carbonate species can act as a buffer to prevent the decrease in pH associated with acid rain in lakes.

### Suggestions

One change that could be made to the lab is when doing the titrations. In order to save time when doing the titrations, a useful recommendation is adding in larger amounts of titrant in order to get an idea of what the equivalent volume is. Therefore, on the second try the increment of titrant added can be smaller as the equivalent volume is approached. By doing this a more precise estimate of the volume of titrant needed in each titration is obtained.


### References
(1) - https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html]

### Appendix
```Python
#code for pH vs hydraulic
from aguaclara.core.units import unit_registry as u
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from scipy import stats
import aguaclara.research.environmental_processes_analysis as epa
data_set = "https://raw.githubusercontent.com/barbaraoramah/my-CEE4530/master/Lab%202%20-%20Acid%20Rain%20(1).txt"
from aguaclara import *

df = pd.read_csv(data_set,delimiter='\t')
print(df)

mass_total = 4.563 * u.kg
mass_bucket = 0.592* u.kg
mass_water = mass_total-mass_bucket
print(mass_water)
volume_water = (mass_water/(1*u.kg/u.L))
print (volume_water)
flow_rate = 0.074/15*u.L/u.s
print(flow_rate)
theta = volume_water/flow_rate
print(theta)

list(df)
columns = df.columns
print(columns)

x = df.loc[:, list(df)[0]].values * u.day
y = df.iloc[:,1].values

fig, ax = plt.subplots()

ax.plot(((x - (0.607747546*u.day))/theta)*100000*u.s, y, 'r')
ax.set(xlabel= 'hydraulic residence time (unitless)')
ax.set(ylabel= 'pH')
ax.grid(True)
plt.savefig('phplot01')
plt.show()

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


fig, ax = plt.subplots()

# plot the data as red circles
ax.plot(V_titrant, pH, 'r')
ax.set(xlabel= 'Titrant Volume (mL)')
ax.set(ylabel= 'pH')
ax.grid(True)
plt.ylim(2.5,6.5)
plt.xlim(0.2,1.5)
ax.annotate('Ve -->', xy=(0.813005 , 2.51), xytext=(0.68, 2.75),)

plt.axvline(x=V_equivalent.magnitude, color='g')
plt.text(0.45, 5.75, '<-- bicarbonate to')
plt.text(0.56, 5.5, 'carbonic acid')
plt.text(0.95, 3.0, '<-- approaching')
plt.text(1, 2.75, 'input pH')
plt.savefig('gran_t=0-line')
plt.show()

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
intercept
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


time = epa.column_of_time(data_set,1,-1)
time
# note: you cannot print a list that has units, you must call it on its own. refer to 't' variable.
res_time = (time/theta).to('dimensionless')
res_time
ANC_0
ANC_out = ANC_0*(np.exp(-res_time))+ANC_in*(1-(np.exp(-res_time)))
ANC_out

lake_pH = df.iloc[:,1].values
lake_pH  = lake_pH[0:1496]
ANC_cl=epa.ANC_closed(lake_pH,ANC_out)
ANC_cl = ANC_cl[0:1496]
ANC_cl

ANC_o = epa.ANC_open(lake_pH)
ANC_o = ANC_o[0:1496]


fig, ax = plt.subplots()
ax.plot(time.to(u.min), ANC_out.to(u.meq/u.L), 'r', time.to(u.min), ANC_cl.to(u.meq/u.L), 'b', time.to(u.min), ANC_o.to(u.meq/u.L), 'g')

time_lake = np.array([0,5,10,15])*u.min
ANC_lake = np.array([(ANC_0.to(u.meq/u.L)).magnitude, (ANC_5.to(u.meq/u.L)).magnitude, (ANC_10.to(u.meq/u.L)).magnitude, (ANC_15.to(u.meq/u.L)).magnitude])

ax.plot(time_lake, ANC_lake, 'p')
ax.set(xlabel= 'time (min)')
ax.set(ylabel= 'ANC (meq/L)')
ax.legend([ 'Conservative ANC','Nonvolatile ANC', 'Volatile ANC','ANC measured'])
ax.grid(True)

plt.ylim((-1,2))
plt.xlim(-0.2,25)
plt.savefig('ANCplotmeasured')
plt.show()
```
