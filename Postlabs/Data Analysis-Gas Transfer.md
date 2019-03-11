### Data Analysis and Questions: Lab 4, Group 6
#### Ian Starnes and Barbara Oramah
##### Time Spent on Lab Report: Ian Starnes - | Barbara Oramah - 4

Data Analysis
This lab will use the power of python to streamline repetitive data analysis. Use the data from the entire class for the analysis. You can use for loops to cycle through all of the data sets.

1. Eliminate the data from each data set when the dissolved oxygen concentration was less than 2 mg/L. This will ensure that all of the sulfite has reacted. Also remove the data when the dissolved oxygen concentration was greater than 6 mg/L to reduce the effect of measurement errors when the oxygen deficit is small.
2. Plot a representative subset of the data showing dissolved oxygen vs. time. Perhaps show 5 plots on one graph.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/airflows.png?raw=true" heights=310 width=927> </p>

**Figure 1** Representative subset of 5 data sets showing the dissolved oxygen vs. time

3. Calculate C⋆ based on the average water temperature, barometric pressure, and the equation from environmental processes analysis called O2_sat. C⋆=PO2e(1727T−2.105) where T is in Kelvin, PO2 is the partial pressure of oxygen in atmospheres, and C⋆ is in mg/L.

```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats
import collections
import os
from pathlib import Path
import math
import time


def aeration_data(DO_column, dirpath):
    #return the list of files in the directory
    filenames = os.listdir(dirpath)
    #extract the flowrates from the filenames and apply units
    airflows = ((np.array([i.split('.', 1)[0] for i in filenames])).astype(np.float32))
    #sort airflows and filenames so that they are in ascending order of flow rates
    idx = np.argsort(airflows)
    airflows = (np.array(airflows)[idx])*u.umole/u.s
    filenames = np.array(filenames)[idx]

    filepaths = [os.path.join(dirpath, i) for i in filenames]
    #DO_data is a list of numpy arrays. Thus each of the numpy data arrays can have different lengths to accommodate short and long experiments
    # cycle through all of the files and extract the column of data with oxygen concentrations and the times
    DO_data=[epa.column_of_data(i,0,DO_column,-1,'mg/L') for i in filepaths]
    time_data=[(epa.column_of_time(i,0,-1)).to(u.s) for i in filepaths]
    aeration_collection = collections.namedtuple('aeration_results','filepaths airflows DO_data time_data')
    aeration_results = aeration_collection(filepaths, airflows, DO_data, time_data)
    return aeration_results

# The column of data containing the dissolved oxygen concentrations
DO_column = 2
dirpath = "/Users/barbaraoramah/github/Barbara-And-Ian/Aeration_Data"
#dirpath = "/Users/Ian/github/Barbara-And-Ian/Aeration_Data"
filepaths, airflows, DO_data, time_data = aeration_data(DO_column,dirpath)

#delete data that is less than 2 or greater than 6 mg/L
DO_min = 2 * u.mg/u.L
DO_max = 6 * u.mg/u.L
for i in range(airflows.size):
  idx_start = (np.abs(DO_data[i]-DO_min)).argmin()
  idx_end = (np.abs(DO_data[i]-DO_max)).argmin()
  time_data[i] = time_data[i][idx_start:idx_end] - time_data[i][idx_start]
  DO_data[i] = DO_data[i][idx_start:idx_end]

# this is hardcoded but i believe a for loop can work

data = [175, 350, 575, 725, 850]

plt.plot(time_data[3],DO_data[3],time_data[7],DO_data[7],time_data[14],DO_data[14],time_data[17],DO_data[17],time_data[22],DO_data[22])

plt.xlabel(r'$time (s)$')
plt.ylabel(r'Oxygen concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(data)
plt.savefig('airflows')
plt.show()

#Calculate C* , what was the pressure we found that day?

P_air = 101.3*u.kPa

temp = 22*u.degC

C_star = epa.O2_sat(P_air,temp)
C_star

#time_data

#t_0 = time_data[0]
#t_initial = t_0[0]

#C_0 = DO_data[0]
#C_initial = C_0[0]

#t_0 = time_data[0]
#t_initial = t_0[0]
#C_0 = DO_data[0]
#C_initial = C_0[0]

# need to create an empty array so data can loop into it, the x is delta t and y is the concentration change
#intercept = intercept * y.units
#slope = slope * y.units/x.units

#list_airflow =[]
#int_avg = np.empty(airflows.size)
#slope_avg = np.empty(airflows.size)
#slope_avg[i]=np.mean(y)
#slope_avg

time_data
airflows.size

# number 4 is a scam and i am boycotting this question
time_change =np.empty(11, dtype="object")
for i in range(11):
  t_0 = time_data[i]
  t_initial = t_0[0]
  delta = t_0[i]-t_initial
  time_change[i] = delta
x=time_change
x
len(x)


y_values = np.empty(11, dtype = "object")
for i in range(11):
  C_0 = DO_data[i]
  C_initial = C_0[0]
  y_eqn = -(1/x[i])*np.log((C_star-C_0)/(C_star-C_initial))
  y_values[i] = y_eqn

C_0
y = y_values
y
y_eqn

kvl = np.empty(11,dtype="object")
for i in range(11):
  x_temp = x[i]
  y_temp = y[i]
  slope, intercept, r_value, p_value, std_err = stats.linregress(x_temp, y_temp)
  kvl[i] = slope

x_temp
plt.xlabel(r'$time (s)$')
plt.ylabel(r'k_vl (s-1)')
#plt.legend(data)
plt.savefig('kvlt')
plt.show()
#t_0 = time_data[i]
#t_initial = t_0[i]

#C_0 = DO_data[i]
#C_initial = C_0[i]

#x = time_data[i]-t_initial
#y = -(1/x)*np.log((C_star-C_0)/(C_star-C_initial))

#Question Four

conc_o2 = C_star-(C_star-DO_data[1][0])*math.exp(-)


```

4. Estimate k̂ v,l using linear regression and equation (103) for each data set.
5. Create a graph with a representative plot showing the model curve (as a smooth curve) and the data from one experiment. You will need to derive the equation for the concentration of oxygen as a function of time based on equation (103).
6. Plot k̂ v,l as a function of airflow rate (μmole/s).
7. Plot OTE as a function of airflow rate (?mole/s) with the oxygen deficit (C⋆−C) set at 6 mg/L.
8. Comment on the oxygen transfer efficiency and the trend or trends that you observe.
9. Propose a change to the experimental apparatus that would increase the efficiency.
10. Verify that your report and graphs meet the requirements.
