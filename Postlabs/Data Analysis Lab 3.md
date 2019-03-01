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

This lab is modelled to highlight how acid rain affects the acid neutralizing capacity (ANC) of lakes. Acid precipitation results from the combustion of fossil fuels which produce oxides of sulfur and nitrogen that react in the earth’s atmosphere to form sulfuric and nitric acid. [(1)](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html] ) The lab report shows the results from two seperate labs, [Lab 1](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#experimental-objectives) and [Lab 2](https://monroews.github.io/EnvEngLabTextbook/Acid_Neutralizing_Capacity/Acid_Neutralizing_Capacity.html#procedures). In Lab 1, the data collected were lake samples in 5 minutes intervals over a 20 minutes time period as an acid rain storage was pumped at a constant flow rate into a modelled lake. This was done in order see the change of pH over time and calculate ANC. In Lab 2, the samples collected in Lab 1 used to determine the ANC of each sample.

The observations of the lab were to be used as supporting evidence that that is possible.

The equations that were used for this lab report:

$$ANC_0 = [ANC_{out} - ANC_{in} (1-e^{-t/\theta})]e^{t/\theta}$$

$$ANC =2[CO_{3}^{2-}]+[HCO_{3}^{-}]+[OH^{-}]-[H^{+}]$$

$${F_1} = \frac{{{V_S} + {V_T}}}{{{V_S}}}{\text{[}}{{\text{H}}^ + }{\text{]}}$$

 $$ANC=\frac{V_e N_t }{V_s }$$


#### Objective
The goal for this lab is to gather experimental data to determine that remediation of lake can be obtained by increasing the ANC added so pH can be at an acceptable level and maintained over a desired period. The lab used sodium bicarbonate, NaHCO3, to be the source of ANC.

This was achieved by adding NaHCO3 to the lake surface and pumping acid rain at a pH of 3. The pH of the lake was then monitored over a 20 minutes time frame.

#### Procedure

The detailed procedure for Lab 1 can be found [here](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#procedures), and the Lab 2 procedure can be found [here](https://monroews.github.io/EnvEngLabTextbook/Acid_Neutralizing_Capacity/Acid_Neutralizing_Capacity.html#procedures).

In Lab 1, a pre-calculated mass of NaHCO3 was weighed out and added into a 4 L lake that had a stirrer bar inside. The stirrer bar was placed to model the lake as a completely mixed flow reactor, CMFR. A pH probe was placed in the lake to measure the change over a course of 20 minutes. In 5 minute intervals, a 100 mL sample of the lake was taken, labelled and set aside. The samples were kept to be used later in Lab 2.

In Lab 2, the 5 different samples were used to perform titrations in order to find the equivalent volume. The titrant used was 0.05 N HCl. The pH probe recorded the data necessary for ProCoDA to create Gran plot analysis.


#### Data Analysis

As mentioned previously, the NaHCO3 was used as the ANC supplement for the lake. Figure 1 clearly shows the pH levels decreasing over time after the ANC was added at t = 0. This is because the bicarbonate ions react with hydrogen ions to form carbonic acid.

$$  [HCO_3^- ] + [H^+] \rightarrow [H_2CO_3]$$

This observation exactly matched expectaions
<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/phplot01.png?raw=true" heights=310 width=927> </p>

**Figure 1:** pH versus hydraulic residence time.

All samples were titrated to find the equivalence volume. Figure 2 displays the pH as a function of the volume of titrant added into the lake representing the acid rain at t=0. At t=0, the sample is expected to be the most basic solution as NaHCO3 was just added, therefore the equivalent volume would be the largest. The equivalent volume is found from the excel file of data from ProCoDA. The equivalence point is defined as the point in the titration where titrant volume that has been added equals the “equivalent” volume (Ve). The equivalence point is a good way to determine ANC

Similarly, Figure 3 is a Gran plot at t=0. In the collected data, there is a first Gran function, F1, attributed to each data point. F1 is defined as a straight line. $${F_1} = \frac{{{V_S} + {V_T}}}{{{V_S}}}{\text{[}}{{\text{H}}^ + }{\text{]}}$$
The abscissa intercept is the equivalent volume. Both figure 1 and 2 clearly show that the equivalent volume for sample t = 0 is 0.831005 ml. This is approximately the same as the calculated equivalent volume of 0.79ml. This was determined.....

There are 3 notable regions of figure 2. As labeled the first region is where bicarbonate ions react with hydrogen ions and form carbonic acid. There is a steep slope

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/gran_t=0-line.png?raw=true" heights=310 width=927> </p>

**Figure 2:** Titration curve of the t=0 sample with 0.05 N HCl


<p align="center"> <img src="https://github.com/barbaraoramah/my-CEE4530/blob/master/images/GranQ2.png?raw=true" heights=310 width=927> </p>

**Figure 3:** Gran Plot data from the titration curve of the t=0 sample


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/ANCplotmeasured1.png?raw=true" heights=310 width=927> </p>

**Figure 4:** Measured ANC of the lake at different states

**-Present results in a clearly labeled format. Data analysis methods, equations, graphs, and tables should be presented in this section. The report text should refer to each equation, figure, and table. Include a table of relevant experimental parameters (e.g., measured flow rates, sample sizes, concentrations of reagents, etc.).
-Compare theoretical expectations with your results and discuss reasons for any observed deviations. If the results weren't as expected, suggest reasons why the laboratory results may have differed from theory and suggest improved techniques to obtain more accurate results or modifications to the theory to better describe the experimental conditions.
-Make sure that responses to specific questions and data analysis requested in the lab manual are included in this section. But don't answer the questions in a list format. Instead, include your answers as part of the narrative that is designed to meet your objectives.**

We learned that by doubling the ANC added, the pH took a longer time to drop. This is because there was a higher buffer capacity, causing the lake to acidify at a slower rate. (from lab 2 data analysis)

### Conclusion

After looking at the titration curve for the t=0 sample, we were able to see two regions of slow change in pH. The first region corresponds to the buffering effect of HCO3 which becomes H2CO3 as it adds a proton and the second corresponds to a region where hydrogen ions contribute directly to the change in pH. The equivalent volume is seen in the region of this graph where there is a steep change in pH. We calculated an equivalent volume that was very close to the ProCoDa value and this is seen in the linear part of the Gran function. The measured ANC over the duration of the experiment is similar to the conservative ANC model but deviates towards the volatile ANC model. This experiment showed us how carbonate species can act as a buffer to prevent the decrease in pH associated with acid rain in lakes.

**The conclusions section should not include any new observation. It is the place to summarize the results in a few sentences. Make sure you connect your conclusions to your objectives for doing the research.**

### Suggestions

One change that could be made to the lab is when doing the titrations. We were able to same time when doing the titrations in the beginning by putting in larger amounts of titrant in order to get an idea of what the equivalent volume was. Then on the second try we were able to put in smaller increment of titrant once we were approaching the that equivalent volume. By doing this we were able to get an idea of how much titrant would be needed in each titration.

**I value your thoughts on where changes are needed as well as what is working well. Please provide very clear ideas that I can add to the lab manual or change in how we run the lab. Include ideas for: improving the data acquisition software
modifying the experimental apparatus (Explain what you would like to change and why)
making the experiment easier to understand (provide proposed change to the lab manual)
modifying the experiment to include some new experimental aspect related to the main topic
alternate ways to analyze the data (As we build better tools we can do cooler analysis!)**


### References
(1) - https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html]

### Appendix
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
ANC_cl=epa.ANC_closed(lake_pH,ANC_0)
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
