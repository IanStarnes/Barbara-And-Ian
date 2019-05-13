# Filter Efficiency of different mesh sizes of Activated Carbon
### Research Project Report
#### Ian Starnes and Barbara Oramah
##### Group 6



### Table of Contents

- [Introduction](#Introduction)
- [Objective](#Objective)
- [Procedure](#Procedure)
- [Results](#Results)
- [Data Analysis](#Data-analysis)
- [Recommendation](#Recommendation)
- [Conclusion](#Conclusion)
- [Suggestions](#Suggestions)
- [Appendix](#Appendix)


## Introduction

## Objectives

###### Write a paragraph on the goals of the experiment. Why did you decide to do this experiment? Introduce your approach by explaining what needs to be done to meet your goal for your real world project. Explain what you hoped to learn through this research. How did you expect this experiment to guide your decisions about the real world project that you are working on?

###### This is the section where you can present the equations that you will be using. Format the equations using Latex to create a beautiful report.

The goal of this experiment was to test several filters that have different size particles of activated carbon. This information is valuable when designing water treatment facilities. Activated carbon can be used in water treatment, primarily, to remove sediment and volatile organic compounds. It is also able to remove odor and taste from the water that goes through an activated carbon filter. However, it is not effective in dissolved inorganic compounds. It can be used in items on the household scale to large industrial scale filtration. Our research will help engineers decide what type of activated carbon is best for each type of filter. We expected that the smaller particle size carbon will be more effective and therefore it would be more likely to be used in engineering applications.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/Screen%20Shot%202019-05-11%20at%201.46.44%20PM.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 1 </b>: Hypothetical Breakthrough curve showing efficiency of filter over time.

Figure 1 above displays a hypothetical breakthrough curve where the filter is effective at particle removal to begin with but then after some time it starts to allow particles through. The goal of our experiment was to find what type of activated carbon maximizes the time when the filter is effectively removing particles.

## Procedure

###### Provide an overview of the methods that you used in your investigation. The best procedures give an overview of the method with an explanation of why you used those methods. There is no need to restate the step-by-step procedures as outlined in the lab manual: it is sufficient to cite the lab manual (use a link to the url) and include information on any deviations from the manual procedures. When method development is part of the laboratory exercise, a detailed description of the methods should be included. Methods and procedures need to be detailed enough so that one of your classmates could duplicate your work.

###### Include the actual values that you measured for volumes, masses, flow rates, etc. For example, if the lab manual suggested 267 mL/min for the flow rate and you measured 310 mL/min, then you report the 310 mL/min in procedures.

The procedure for our experiment follows closely with the [adsorption lab](https://monroews.github.io/EnvEngLabTextbook/Adsorption/Adsorption.html#contactor-procedures). However, some changes were made to the test system. We included a pressure sensor right after the pump in order to see if there was any relationship between pressure in the system and type of activated carbon. A pressure build up would be accompanied by a decrease in flow rate. We would have to take into account the different in flow rate in comparing the results from the different mesh sizes.

Three different mesh sizes were used. The 20-40 mesh was used as a medium size particle size (the same activated carbon from the adsorption lab). The 100 mesh was used as a powder particle size of activated carbon. Finally, the 4-12 mesh was used as the large particle size.

Using the same procedure as the adsorption lab we obtained the concentration of the red dye leaving the filter using a calibrated photometer. This worked without any problems until the 100 mesh activated carbon. With the 100 mesh, the wire screen on each side of the filter allowed the activated carbon through. The activated carbon was smaller than the wire screen. Therefore, we looked into different types of additional filters to prevent the activated carbon from leaving the filter. After looking at the effectiveness of three different potential filters we decided to use coffee filters. Two layers of coffee filters were placed between two wire screens on each side of the filter. This setup was successful in preventing the activated carbon from leaving the filter without too great of an increase in pressure build up.

## Results and Discussion

###### Present results in a clearly labeled format. Data analysis methods, equations, graphs, and tables should be presented in this section. The report text should refer to each equation, figure, and table. Include a table of relevant experimental parameters (e.g., measured flow rates, sample sizes, concentrations of reagents, etc.).

###### Compare theoretical expectations with your results and discuss reasons for any observed deviations. If the results weren't as expected, suggest reasons why the laboratory results may have differed from theory and suggest improved techniques to obtain more accurate results or modifications to the theory to better describe the experimental conditions.

###### Make sure that responses to specific questions and data analysis requested in the lab manual are included in this section. But don't answer the questions in a list format. Instead, include your answers as part of the narrative that is designed to meet your objectives.


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/research_diff_mesh.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 2 </b>: Breakthrough curves for columns with different mesh sizes of activated carbon vs. time over hydraulic residence time.

Figure 2 shows that the higher mesh size of -100 mesh had the longest breakthrough times. The 100 mesh experiment ran for three days, whereas  the 4-12 mesh experiment ran for less than half a day. The results were very promising as it proved our hypothesis that the finer the activated carbon used, the longer breakthrough will take to occur.

The finer particles have a greater surface area available for the red dye to be adsorbed to.

As we were running the -100 mesh experiment, an issue that we faced was activated carbon entering into the system. Our solution for preventing this was adding two ply of coffee filters between the wire mesh of the inlet and outlet of the filter. Though this stopped the activated carbon particles entering the system, we noticed that there was a build-up of pressure which caused a decrease in flow rate.

The peristaltic tubing used in our apparatus was the 17 tubing size. In reference to [Table 2 in the  Acid Precipitation and Remediation of Acid Lakes](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#id3), the flow rate in 1 RPM/ID (mm) translates to 2.802 mL/min. This showed us that at 5 RPM the flow rate we should be approximately 14.01 mL/min. As seen from Table 1, the flow for the -100 mesh is half of what is should be. This implies that the total volume of water treated may not have been as promising as it appeared in Figure 1. This has major implications on how truly effective the -100 mesh worked as a whole.

The varying flow rates were accounted for in Figure 2 as we looked at the flow rate for the different mesh sizes and obtained the concentration as a function of hydraulic residence time we were able to normalize the x axis.

$$R_{adsorption} = \frac{t_{mtz}}{t_{water}}$$


| Mesh Size | Flow Rate (mL/min) | Retardation Coefficient |
| --------- | ------------------ | ----------------------- |
| -100      | 8                  | 4.111                   |
| 20-40     | 14                 | 3.947                   |
| 4-12      | 14                 | 3.289                             
<p align="center">
<b>Table 1 </b>: Measured flow rates of different mesh sizes

We became interested in exploring different materials that could be used to prevent -100 mesh activated carbon entering the system. We used materials that were easily accessible in the lab such as white paper towels, brown paper towels and coffee filters. In our apparatus design, we included a pressure sensor between the pump and filter to record the pressure build-up for the different materials.

| Material | Pressure (cm of water)| Activated Carbon concentration (g/L) |
| --------- | ------------------ | ----------------------- |
| White Paper Towels      | 2200                 | -                   |
| Brown Paper Towels    | 1900                | 0.09          |
| Coffee Filter   | 1650                 | 0.58
<p align="center">
<b>Table 2</b>: Measured flow rates of different mesh sizes

We deduced that the optimal filter would strike a balance between pressure and as well as prevent activated carbon entering the system. As mentioned in the procedure, we made calibrated the photometer register different activated carbon concentrations. This was done after the run for white paper towels, hence why there is no data for the activated carbon concentration in Table Two.  

Focusing on brown paper towels and coffee filters in Table Two, it is evident that there are pros and cons for the two materials The brown paper towels caused a greater increase in pressure than the coffee filter. However, te







## Conclusion

###### The conclusions section should not include any new observation. It is the place to summarize the results in a few sentences. Make sure you connect your conclusions to your objectives for doing the research.

In conclusion, we were able to determine that the -100 mesh activated carbon was the best mesh size for removing Red Dye #40.



## Suggestions

###### I value your thoughts on where changes are needed as well as what is working well. Please provide very clear ideas that I can add to the lab manual or change in how we run the lab. Include ideas for:

###### improving the data acquisition software
###### modifying the experimental apparatus (Explain what you would like to change and why)
###### making the experiment easier to understand (provide proposed change to the lab manual)
###### modifying the experiment to include some new experimental aspect related to the main topic
###### alternate ways to analyze the data (As we build better tools we can do cooler analysis!)

## Appendix

###### Put all of the python code in the Appendix at the bottom of the report. Ideally make this one block of code with comments so that it can both be understood and be executed all at once.

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
100 mesh:
  pts: (47500 hrt, .12), (55000 hrt, .29)
  slope = 0.00002267 increase in red dye / HRT
20-40 mesh:
  pts: (2000 hrt, .12), (4000 hrt, .29)
  slope= 0.17/2000 = 0.000085 increase in red dye / HRT
4-12 mesh:
  pt: (200 hrt, 0.1), (400 hrt, 0.35)
  slope= .25/200 = 0.00125 increase in red dye / HRT


###### You can use the Lab Manual as an example of a well formatted document. The Atom reports should have similar formatting with the required python code.
