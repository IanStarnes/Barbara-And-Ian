# Filter Efficiency of different mesh sizes of Activated Carbon
### Research Project Report
#### Ian Starnes and Barbara Oramah
##### Group 6

### Table of Contents

- [Introduction](#Introduction)
- [Objective](#Objective)
- [Procedure](#Procedure)
- [Data Analysis](#Data-analysis)
- [Conclusion](#Conclusion)
- [Suggestions](#Suggestions)
- [Appendix](#Appendix)


## Introduction

Filtration is an important component in water sanitation. Different mediums and methods are used in filters, however we decided to focus creating a ratio of activated carbon and sand and how effective they are at removing contaminants in water. Activated carbon can be used in water treatment, primarily to remove sediment and volatile organic compounds. It is also able to remove odor and taste from the water that goes through an activated carbon filter. However, it is not effective in removing dissolved inorganic compounds. It can be used in items on the household scale to large industrial scale filtration.

Activated carbon can be found in different mesh sizes. Mesh sizes are a measurement standard for the size of particles. The larger the mesh size, the finer the particle. We were interested in testing how the different sizes of mesh can have an effect on filter efficiency. Figure 1 shows that the particles with a small diameter have a greater number of pores within the same area.

<p align="center"> <img src="https://github.com/AguaClara/stars_filter_theory/raw/master/Fall%202018/Images/sand.jpg?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 1</b>: Demonstrates that when particle sizes are larger, there are fewer pores in the filter.


## Objective

The goal of this experiment was to test several filters that have different size particles of activated carbon. This information is valuable when designing water treatment facilities.  Our research will help engineers decide what type of activated carbon is best for each type of filter. We expected that the smaller particle size carbon will be more effective and therefore it would be more likely to be used in engineering applications.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/Screen%20Shot%202019-05-11%20at%201.46.44%20PM.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 2</b>: Hypothetical Breakthrough curve showing efficiency of filter over time.

Figure 1 above displays a hypothetical breakthrough curve where the filter is effective at particle removal to begin with but then after the breakthrough time it starts to allow particles through. The goal of our experiment was to find what type of activated carbon maximizes the time when the filter is effectively removing particles.

## Procedure

The procedure for our experiment follows closely with the [adsorption lab](https://monroews.github.io/EnvEngLabTextbook/Adsorption/Adsorption.html#contactor-procedures). However, some changes were made to the test system. We included a pressure sensor right after the pump in order to see if there was any relationship between pressure in the system and the type of activated carbon. A pressure build up would be accompanied by a decrease in flow rate. We would have to take into account the difference in flow rate in comparing the results from the different mesh sizes.

Three different mesh sizes were used. The 20-40 mesh was used as a medium size particle size (the same activated carbon from the adsorption lab). The 100 mesh was used as a powder particle size of activated carbon. Finally, the 4-12 mesh was used as the large particle size.

Using the same procedure as the adsorption lab we obtained the concentration of the red dye leaving the filter using a calibrated photometer. This worked without any problems until the 100 mesh activated carbon. With the 100 mesh, the wire screen on each side of the filter allowed the activated carbon through. The activated carbon was smaller than the wire screen. Therefore, we looked into different types of additional filters to prevent the activated carbon from leaving the filter. After looking at the effectiveness of three different potential filters we decided to use coffee filters. Two layers of coffee filters were placed between two wire screens on each side of the filter. This setup was successful in preventing the activated carbon from leaving the filter without too great of an increase in pressure build up.

## Data Analysis

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/research_diff_mesh.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 3 </b>: Breakthrough curves for columns with different mesh sizes of activated carbon vs. time over hydraulic residence time.

Figure 2 shows that the higher mesh size of -100 mesh had the longest breakthrough times. The 100 mesh experiment ran for three days, whereas  the 4-12 mesh experiment ran for less than half a day. The results were very promising as it proved our hypothesis that the finer the activated carbon used, the longer breakthrough will take to occur.

The finer particles have a greater surface area available for the red dye to be adsorbed to.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/research_diff_mesh_2.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 4 </b>: Breakthrough curve slope for -100 mesh vs. time over hydraulic residence time.

Figure 3 provides a closer look at the slope of the -100 mesh as it goes through breakthrough. The slope for the -100 mesh during breakthrough is not as steep as as the 20-40 mesh and 4-12 mesh experiments. This is also referenced in table 1.

As we were running the -100 mesh experiment, an issue that we faced was activated carbon entering into the system. Our solution for preventing this was adding a two-ply coffee filter between the wire mesh of the inlet and outlet of the filter. Though this stopped the activated carbon particles entering the system, we noticed that there was a build-up of pressure which caused a decrease in flow rate.

The peristaltic tubing used in our apparatus was the 17 tubing size. In reference to [Table 2 in the  Acid Precipitation and Remediation of Acid Lakes](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#id3), the flow rate in 1 RPM/ID (mm) translates to 2.802 mL/min. This showed us that at 5 RPM the flow rate we should be approximately 14.01 mL/min. As seen from Table 1, the flow for the -100 mesh is half of what is should be. This implies that the total volume of water treated may not have been as promising as it appeared in Figure 1. This has major implications on how truly effective the -100 mesh worked as a whole.

The varying flow rates were accounted for in Figure 2 as we looked at the flow rate for the different mesh sizes and obtained the concentration as a function of hydraulic residence time we were able to normalize the x axis.

The retardation factor is defined as the ratio of the time for the mass transfer zone to travel through the bed divided by the time for water to travel through the bed. A high retardation factor shows that contaminant took a long time to pass through the filter, which shows us that breakthrough will occur slowly.

$$R_{adsorption} = \frac{t_{mtz}}{t_{water}}$$
<p align="center">
<b>Equation 1</b>: Retardation factor for adsorption

| Mesh Size | Flow Rate (mL/min) | Retardation Coefficient | Slope of Breakthrough (change of C/C0 per HRT)|
| --------- | ------------------ | ----------------------- |------- |
| -100      | 8                  | 38000                   |  0.00002267
| 20-40     | 14                 | 625                   | 0.000085
| 4-12      | 14                 | 130   | 0.00125                          
<p align="center">
<b>Table 1 </b>: Characteristics of different mesh sizes

We became interested in exploring different materials that could be used to prevent -100 mesh activated carbon entering the system. We used materials that were easily accessible in the lab such as white paper towels, brown paper towels and coffee filters. In our apparatus design, we included a pressure sensor between the pump and filter to record the pressure build-up for the different materials.

| Material | Pressure (cm of water)| Activated Carbon concentration (g/L) |
| --------- | ------------------ | ----------------------- |
| White Paper Towels      | 2200                 | -                   |
| Brown Paper Towels    | 1900                | 0.09          |
| Coffee Filter   | 1650                 | 0.58
<p align="center">
<b>Table 2</b>: Different filter materials characteristics

We deduced that the optimal filter would strike a balance between pressure and as well as prevent activated carbon entering the system. As mentioned in the procedure, we used a photometer to measure effluent concentration for red dye. We had to recalibrate the photometer to register different activated carbon concentrations. This was done after the run for white paper towels, hence why there is no data for the activated carbon concentration in table 2.  

Focusing on brown paper towels and coffee filters in table 2, it is evident that there are pros and cons for the two materials The brown paper towels caused a greater increase in pressure than the coffee filter. However, the activated carbon concentration for the brown paper towel is less than that of the coffee filter. This shows that the brown paper towels was a better barrier against activated carbon entering the system. The trade-off is important to consider because though the goal is to stop activated carbon entering the system, we do not want to great of an increase in pressure. Increase in pressure could be an indicator that total volume of water treated might not be what it appears.


## Conclusion

In conclusion, we were able to determine that the -100 mesh activated carbon was the best mesh size for removing Red Dye #40. In running experiments, it became evident that there was an increase in pressure in the -100 mesh filter because we observed a decrease in flow rate. The decrease in flow rate was linked to the coffee filters used to prevent activated carbon particles leaving the filter.

When faced with this issue, we explored how different materials can be used to prevent activated carbon entering the system. We concluded that there is a trade-off between using a filter material that maintains a reasonable pressure within the system as well as being an effective barrier against activated carbon.


## Suggestions

For further research into adsorption, there are several areas to consider. It would be interesting to see how efficient the activated carbon is at removing different types of organic compounds to see how representative red dye #40 is for other compounds. Also, we would like to see if the relationship of efficiency of the filter at different flow rates to find the best reactor.

One problem that we encountered during this lab was that the activated carbon doesn't easily mix. It often forms layers and the activated carbon is in higher concentrations at the top of the filter. During the adsorption, we would suggest to explicitly describe the best way to ensure proper mixing.

In terms of future works that can be implemented in this research project, we are very interested in exploring the Carmen-Kozeny equation to determine the pressure drop of fluid through a packed bed of solids.

$$ \frac{h_l}{H_{FiSand}}=36k\frac{(1-\epsilon_{FiSand})^2\nu V_{Fi}}{\epsilon_{FiSand}^3 gD_{sand}^2}$$
<p align="center">
<b>Equation 2</b>: Carmen-Kozeny Equation


## Appendix

```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.physchem as pc
import aguaclara.core.utility as ut
import numpy as np
import matplotlib.pyplot as plt
import collections
import os
from pathlib import Path
import pandas as pd

path20="https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Research%20Project/Mesh20_2.txt"
mesh20time = (epa.column_of_time(path20,1,-1)).to(u.s)
mesh20conc= epa.column_of_data(path20,1,1,-1,'mg/L')

path4 ="https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Research%20Project/4-12%20mesh%209%20to%201%20ratio.xls"
mesh4time = (epa.column_of_time(path4,1,-1)).to(u.s)
mesh4conc= epa.column_of_data(path4,1,1,-1,'mg/L')

path100 = "https://raw.githubusercontent.com/IanStarnes/Barbara-And-Ian/master/Research%20Project/mesh100_2.txt"
mesh100time = (epa.column_of_time(path100,1,-1)).to(u.s)
mesh100conc= epa.column_of_data(path100,1,1,-1,'mg/L')

Column_D = 1 * u.inch
Column_A = pc.area_circle(Column_D)
Column_L = 15.2 * u.cm
Column_V = Column_A * Column_L
Tubing_V = 60 * u.mL

Flow_rate_4 =14 * u.mL/u.s
Flow_rate_20 = 14 * u.mL/u.s
Flow_rate_100 = 8 * u.mL/u.s

#temporary assumed mass for all - change later
Mass_carbon_4= 14 * u.g
Mass_carbon_20= 14 * u.g
Mass_carbon_100= 14 * u.g

Tubing_HRT_4 = Tubing_V/Flow_rate_4
Tubing_HRT_20= Tubing_V/Flow_rate_20
Tubing_HRT_100 = Tubing_V/Flow_rate_100

#temporary assumed porosity for all - change later
porosity_4 = 0.4
porosity_20 = 0.4
porosity_100 = 0.4

C_0 = 50 * u.mg/u.L

#estimate the HRT for all of the columns
HRT_4 = (porosity_4 * Column_V/Flow_rate_4).to(u.s)
HRT_20 = (porosity_20 * Column_V/Flow_rate_20).to(u.s)
HRT_100 = (porosity_100 * Column_V/Flow_rate_100).to(u.s)

#zero the concentration data by subtracting the value of the first data point from all data points. Do this in each data set.

plt.plot(mesh4time/HRT_4 - Tubing_HRT_4/HRT_4, mesh4conc/C_0,'-');
plt.plot(mesh20time/HRT_20 - Tubing_HRT_20/HRT_20, mesh20conc/C_0,'-')
plt.plot(mesh100time/HRT_100 - Tubing_HRT_100/HRT_100, mesh100conc/C_0,'-')

plt.xlabel(r'$\frac{t}{\theta}$');
plt.ylabel(r'Red dye (C/Co) $\left (unitless\right )$');
plt.xlim(left=0)
plt.legend(['4-12 mesh','20-40 mesh', '-100 mesh'])
plt.savefig('images/research_diff_mesh_2')
plt.show()

```
