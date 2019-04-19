### Data Analysis and Questions: Lab 6, Group 6
#### Ian Starnes and Barbara Oramah

### Data Analysis

Breakthrough is defined as the time that mass of red dye goes passes through the filter when the activated carbon (the adsorbent) can no longer adsorb the red dye (the adsorbate). As time progresses, the red dye passes through through the filter with a concentration close to the influent. The steep slope increase represents the mass transfer zone breakthrough.

Figure 1 is a graph that supports this statement where breakthrough curve of sand columns are plotted of C/C0 vs time over hydraulic residence time.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/Sand_column.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 1 </b>: Breakthrough curves showing C/C0 vs. time with sand columns
</p>

Figure 2 and Figure 3 represents the graphs of experiments that had activated carbon in the filter. Te figures clearly show that filters with high mass of activated carbon take a longer amount of time to breakthrough. Figure 3 is a close up so it can be easier to compare with Figure 1.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/Activated_carbon.png?raw=true9" heights=110 width=427> </p>

<p align="center">
<b>Figure 2 </b>: Breakthrough curves for columns with different masses of activated carbon vs. time over hydraulic residence time.
</p>


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/Activated_carbon%20close%20up.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 3 </b>: Figure 2 with tighter limit constraints.
</p>

With greater masses of activated carbon in the filter, there is positive correlation to the the increase in time for the effluent to reach 50% of the influent, as shown in figure 4. This is not necessarily clear to see with small masses of activated carbon that are less than 5 grams.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/time_half.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 4 </b>: Time showing when effluent concentration was 50% of influent concentration as a function of mass of activated carbon used.
</p>


The retardation factor is defined as the ratio of the time for the mass transfer zone to travel through the bed divided by the time for water to travel through the bed.

$$ R_{adsorption} = \frac{t_{mtz}}{t_{water}}$$


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/R_adsorption.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 5 </b>: Retardation coefficient as a function of mass of activated carbon used.
</p>

| Mass of Activated Carbon (g) | Flow Rate (mL/s) | Retardation Coefficient |
| ---------------------------- | ---------------- | ----------------------- |
| 0                            | 0.5              | 4.111                   |
| 0                            | 0.5              | 3.947                   |
| 0                            | 2.6              | 3.289                   |
| 0                            | 0.5              | 3.207                   |
| 0.5                          | 0.5              | 3.289                   |
| 0.601                        | 0.5              | 2.878                   |
| 1.66                         | 0.5              | 9.128                   |
| 2                            | 0.466            | 14.227                  |
| 4                            | 0.466            | 1.891                   |
| 13.8                         | 2.6              | 2.796                   |
| 15                           | 0.5              | 59.789                  |
| 15.63                        | 2.6              | 84.294                  |
| 29.34                        | 0.467            | 494.064                 |
<p align="center">
<b>Table 1</b>: Retardation Factors of each data set
</p>


q0 is defined as the mass of  adsorbate per mass of adsorbent.

$$ q_0 = (R{adsorption} -1 )\frac{C_0\phi V_{column}}{M_{adsorbent}} $$

Figure 6 shows the relationship between the mass of activated carbon and q0.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/q0.png?raw=true" heights=110 width=427> </p>

<p align="center">
<b>Figure 6</b>: q0 as a function of mass of activated carbon used.
</p>


### Conclusion

In conclusion, this lab was focused on determining the breakthrough characteristics of red dye #40 using activated carbon and sand as the absorbent materials. It is evident that with a large quantity of activated carbon, the breakthrough time for the dye is significantly extended.

Some teams used different flow rates which caused the breakthrough time to occur faster than expected. This does not occur when a similar mass of activated carbon is used with a slower flow rate.

### Suggestion

A common issue in this lab was air bubbles in the system. In the beginning of lab, the class should go over techniques to minimize the effect of air bubbles. This is particularly important when looking at the photometer and the tubing.

Additionally, another recommendation for future labs is to have all the experiments to be run at the same flow rate, so comparisons can be made easier.


### Appendix
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



def adsorption_data(C_column, dirpath):
    """This function extracts the data from folder containing tab delimited
    files of adsorption data. The file must be the original tab delimited file.

    Parameters
    ----------
    C_column : int
        index of the column that contains the dissolved oxygen concentration
        data.
    dirpath : string
        path to the directory containing aeration data you want to analyze
    Returns
    -------
    filepaths : string list
        all file paths in the directory sorted by flow rate
    time_data : numpy array list
        sorted list of numpy arrays containing the times with units of seconds
    Examples
    --------
    """
    #return the list of files in the directory
    metadata = pd.read_csv(dirpath + '/metadata.txt', delimiter='\t')
    filenames = metadata['file name']
    #extract the flowrates from the filenames and apply units
    #sort airflows and filenames so that they are in ascending order of flow rates


    filepaths = [dirpath + '/' + i for i in filenames]
    #C_data is a list of numpy arrays. Thus each of the numpy data arrays can have different lengths to accommodate short and long experiments
    # cycle through all of the files and extract the column of data with oxygen concentrations and the times
    C_data=[epa.column_of_data(i,epa.notes(i).last_valid_index() + 1,C_column,-1,'mg/L') for i in filepaths]
    time_data=[(epa.column_of_time(i,epa.notes(i).last_valid_index() + 1,-1)).to(u.s) for i in filepaths]

    adsorption_collection = collections.namedtuple('adsorption_results','metadata filenames C_data time_data')
    adsorption_results = adsorption_collection(metadata, filenames, C_data, time_data)
    return adsorption_results


C_column = 1
dirpath = "https://raw.githubusercontent.com/monroews/CEE4530/master/Examples/data/Adsorption"

metadata, filenames, C_data, time_data = adsorption_data(C_column,dirpath)
metadata
Column_D = 1 * u.inch
Column_A = pc.area_circle(Column_D)
Column_L = 15.2 * u.cm
Column_V = Column_A * Column_L
#I'm guessing at the volume of water in the tubing, in the photometer, and in the space above and below the column. This parameter could be adjusted!
Tubing_V = 60 * u.mL
Flow_rate = ([metadata['flow (mL/s)'][i] for i in metadata.index])* u.mL/u.s
Mass_carbon= ([metadata['carbon (g)'][i] for i in metadata.index])* u.g
Tubing_HRT = Tubing_V/Flow_rate
#to make things simple we are assuming that the porosity is the same for sand and for activated carbon. That is likely not true!
porosity = 0.4
C_0 = 50 * u.mg/u.L

#estimate the HRT for all of the columns
HRT = (porosity * Column_V/Flow_rate).to(u.s)

#zero the concentration data by subtracting the value of the first data point from all data points. Do this in each data set.
for i in range(np.size(filenames)):
  C_data[i]=C_data[i]-C_data[i][0]

#Create a graph of the columns that didn't have any activated carbon
mylegend = []
for i in range(np.size(filenames)):
  if (metadata['carbon (g)'][i] == 0):
    plt.plot(time_data[i]/HRT[i] - Tubing_HRT[i]/HRT[i], C_data[i]/C_0,'-');
    mylegend.append(str(metadata['flow (mL/s)'][i]) + ' mL/s')

plt.xlabel(r'$\frac{t}{\theta}$');
plt.xlim(right=3,left=0);
plt.ylabel(r'Red dye (C/Co) $\left (unitless\right )$');
plt.legend(mylegend);
plt.savefig('images/Sand_column')
plt.show()

# create a graph of the columns that had different masses of activated carbon. Note that this includes systems with different flow rates!
mylegend =[]
for i in range(np.size(filenames)):
  if (metadata['carbon (g)'][i] != 0):
    plt.plot(time_data[i]/HRT[i] - Tubing_HRT[i]/HRT[i], C_data[i]/C_0,'-');
    mylegend.append(str(ut.round_sf(metadata['carbon (g)'][i],3)) + ' g, ' + str(ut.round_sf(metadata['flow (mL/s)'][i],2)) + ' mL/s')

plt.xlabel(r'$\frac{t}{\theta}$');
plt.xlim(right=100,left=0);
plt.ylabel(r'Red dye (C/Co) $\left ( unitless \right )$');
plt.legend(mylegend);
plt.savefig('images/Activated_carbon')
plt.show()

mylegend =[]
for i in range(np.size(filenames)):
  if (metadata['carbon (g)'][i] != 0):
    plt.plot(time_data[i]/HRT[i] - Tubing_HRT[i]/HRT[i], C_data[i]/C_0,'-');
    mylegend.append(str(ut.round_sf(metadata['carbon (g)'][i],3)) + ' g, ' + str(ut.round_sf(metadata['flow (mL/s)'][i],2)) + ' mL/s')
plt.xlabel(r'$\frac{t}{\theta}$');
plt.xlim(right=10,left=0);
plt.ylabel(r'Red dye (C/Co) $\left ( unitless \right )$');
plt.legend(mylegend);
plt.savefig('images/Activated_carbon close up')
plt.show()

# Question Two
C_half = np.zeros(13) * (u.mg/u.L)
time_half = np.zeros(13) * (u.s)
C_half
for i in range(np.size(filenames)):
  for j in range(np.size(C_data[i])):
    #if ((C_half[i-1] == 0) and ((C_data[i-1][j-1]/C_0) > 0.5)):
    if ((C_data[i][j]/C_0) > 0.5):
      C_half[i] = (C_data[i][j])
      time_half[i]=(time_data[i][j])
      break

time_half
#time_half[12]=0 *u.s
time_half[2]=time_half[2]*5
time_half[11]=time_half[11]*5
C_half
C_data[12]

plt.plot(Mass_carbon,time_half, 'o');
#plt.yscale('log', basey=10)
plt.ylabel(r'time');
plt.xlabel(r'mass of activated carbon (g)');
plt.savefig('images/time_half')
plt.show()

# Question Three
v_a = 1 * u.mm/u.s
porosity = 0.4
L_column = 15.2 * u.cm
D_column = 1*u.inch
A_column = pc.area_circle(D_column)
V_column = (A_column * L_column).to(u.L)
V_column
C_0 = 50 * u.mg/u.L
q_0 = 0.08
t_water = (L_column*porosity/v_a).to(u.s)
t_mtz_target = time_half
# set the breakthrough times of the dataset
R_adsorption = t_mtz_target/t_water
R_adsorption[11]=R_adsorption[11]*5
R_adsorption
plt.plot(Mass_carbon,R_adsorption, 'o');
plt.ylabel(r'R_adsorption');
plt.xlabel(r'mass of activated carbon (g)');
plt.savefig('images/R_adsorption')
plt.show()

# Question Four
q0=(R_adsorption-1)*(C_0*porosity*V_column/Mass_carbon.to(u.mg))

q0
plt.plot(Mass_carbon,q0, 'o');
plt.ylabel(r'q0')
plt.xlabel(r'mass of activated carbon (g)');
plt.savefig('images/q0')
plt.show()
```
