### Data Analysis and Questions: Lab 4, Group 6
#### Ian Starnes and Barbara Oramah
##### Time Spent on Lab Report: Ian Starnes - | Barbara Oramah - 4

### Lab exploration

1. ProCoDa switches from the “prepare to calibrate” state to the “calibrate” state when the pressure below the prerdefined threshold.

2. ProCoDA switches from the “calibrate” state to the “Pause” state when the pressure in the accumulator reaches 60% of the source pressure. During the “Pause” state both valves are closed.

3. The “Pause” state knows which state to go to next because the “Pause” state stops when the elapsed time in the current state (“pause” state) is greater than the calibrate to aeration lag, then the next state is set to “Aerate”.

4. The equation that is used to calculate the maximum calibration pressure is (source pressure) * (max cal/ source). This equation better than using a constant for the maximum calibration pressure because our source pressure is not constant.

5. ProCoDA calculates the predicted pressure in the accumulator when it is filled at a constant mass flow rate by using the constant “(R*T/V)” and “Delta P” ( max cal pressure – min cal pressure) to calculate the “fill time”. This variable is used along with max calibration pressure and min calibration pressure to plot the air fill model.

6. The inputs to the “air valve control” are the air slope and the air flow rate.

7. “Air valve control” controls the solenoid valve which controls the air flow rate in our system and the two states that use it are “aerate” and “fill accumulator”.

8. Jonathan saw our program execute properly.


### Data Analysis

This lab will use the power of python to
streamline repetitive data analysis. Use the data from the entire class for the analysis. You can use for loops to cycle through all of the data sets.


<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/airflows.png?raw=true" heights=310 width=927> </p>

**Figure 1** Representative subset of 5 data sets showing the dissolved oxygen vs. time

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/OneSet.png?raw=true" heights=310 width=927> </p>

**Figure 2** Representative plot showing the model curve (as a smooth curve) and the data from 100 moles/second flow rate.

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/kvlt.png?raw=true" heights=310 width=927> </p>

**Figure 3**  kv,l  as a function of airflow rate (μmole/s)

<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/ote-airflow.png?raw=true" heights=310 width=927> </p>

**Figure 4** OTE as a function of airflow rate (μmole/s) with the oxygen deficit (C⋆−C) set at 6 mg/L.


8. Comment on the oxygen transfer efficiency and the trend or trends that you observe.

As the air flow rate increases, the oxygen transfer efficiency (OTE) decreases. As the flow rate increased, it observed that the air bubbles in the system increase in size, thus reducing the surface area to volume ratio for gas transfer. Additionally, the speed of the bubbles increased. This means that the the time of each bubble spent in the reactor decreased. With this in consideration, the bubbles at a higher flow rate do not transfer o

9. Propose a change to the experimental apparatus that would increase the efficiency.

A change that would increase the efficiency of the experiment would be using a deeper reactor. This would allow the bubbles to stay within the reactor for a longer period of time.

Make sure to keep the DO probe is close to the bottom of the reactor. This will make sure that there are no air bubbles covering the DO probe which will affect the data that is collected


### Conclusion

To conclude, cvre

### Suggestion
Make sure to keep the DO probe is close to the bottom of the reactor. This will make sure that there are no air bubbles covering the DO probe which will affect the data that is collected

### Appendix
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
import statistics


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
data1 = [100, 125, 175, 200,225,250,350,400,450,475,500,525,575,650,700,725,750,775,800,825,850,925,950]

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

time_data
airflows.size

# number 4 is a scam and i am boycotting this question
time_change =np.empty(23, dtype="object")
for i in range(23):
  t_0 = time_data[i]
  t_initial = t_0[0]
  delta = t_0-t_initial
  time_change[i] = delta
x=time_change
x
len(x)

y_values = np.empty(23, dtype = "object")
for j in range(23):
  C = DO_data[j]
  C_initial = C[0]
  y_eqn = np.log((C_star-C)/(C_star-C_initial))
  y_values[j] = y_eqn
y = y_values


kvl = np.empty(23, dtype="object")
for k in range(23):
  slope, intercept, r_value, p_value, std_err = stats.linregress(-x[k], y[k])
  kvl[k]=slope
kvl

ts=np.linspace(0, x[0][36], num=100)
Cs=C_star-((C_star-DO_data[0][0])*np.exp(-kvl[0]*ts))
tp=x[0]
Cp= C_star-((C_star-DO_data[0][0])*np.exp(y[0]))
plt.plot(ts,Cs,x[0],DO_data[0],'ro')
plt.xlabel(r'$Time (sec)$')
plt.ylabel(r'DO concentraion (mg/L)')
plt.legend(['Model Curve','Data from experiment'])
plt.savefig('OneSet.png')
plt.show()


data1 = np.array([100, 125, 175, 200,225,250,350,400,450,475,500,525,575,650,700,725,750,775,800,825,850,925,950])*u.mole/u.s/10**6
#data1 = [100, 125, 175, 200,225,250,350,400,450,475,500]
plt.plot(data1,kvl, 'ro')
plt.xlabel(r'$Flow Rate (muM/s)$')
plt.ylabel(r'k_vl (s-1)')
#plt.legend(data)
plt.savefig('kvlt')
plt.show()

#Question 7
store=kvl/u.s
V = 0.75*u.L
f = 0.21
MW_O2 = 32*u.g/u.mole
R = 8.314*u.J/u.mole/u.K
temp1=295*u.K
D=0.006*u.g/u.L
P_air = 101300*u.Pa
n_air = (data1)
n_air.to_base_units

OTE=(V*store*D)/(f*n_air*MW_O2)
OTE

plt.plot(data1, OTE, 'ro')
plt.xlabel(r'Airflow rate (mole/sec)')
plt.ylabel(r' OTE')
plt.savefig('ote-airflow.png')
plt.show()

```
