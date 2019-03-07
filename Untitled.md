```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from scipy import stats
import collections
import os
from pathlib import Path
import time

# This code is included because there is a bug in the version of this code that is in epa.

def aeration_data(DO_column, dirpath):
    """This function extracts the data from folder containing tab delimited
    files of aeration data. The file must be the original tab delimited file.
    All text strings below the header must be removed from these files.
    The file names must be the air flow rates with units of micromoles/s.
    An example file name would be "300.xls" where 300 is the flowr ate in
    micromoles/s. The function opens a file dialog for the user to select
    the directory containing the data.

    Parameters
    ----------
    DO_column : int
        index of the column that contains the dissolved oxygen concentration
        data.

    dirpath : string
        path to the directory containing aeration data you want to analyze

    Returns
    -------
    filepaths : string list
        all file paths in the directory sorted by flow rate

    airflows : numpy array
        sorted array of air flow rates with units of micromole/s attached

    DO_data : numpy array list
        sorted list of numpy arrays. Thus each of the numpy data arrays can
        have different lengths to accommodate short and long experiments

    time_data : numpy array list
        sorted list of numpy arrays containing the times with units of seconds

    Examples
    --------

    """
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
print(airflows.magnitude)
# The column of data containing the dissolved oxygen concentrations
DO_column = 2
dirpath = "Aeration"
filepaths, airflows, DO_data, time_data = aeration_data(DO_column,dirpath)

airflowssubsection = np.array([])
print(airflows[i])
help(np.insert)
for i in range(0,airflows.size,4):
  np.insert(airflowssubsection,airflows[i])
  print(airflows[i])
print(airflowssubsection)

# Plot the raw data
for i in range(0,airflows.size,4):
  plt.plot(time_data[i], DO_data[i],'-')
plt.xlabel(r'$time (s)$')
plt.ylabel(r'Oxygen concentration $\left ( \frac{mg}{L} \right )$')
plt.legend(airflows[i].magnitude)
plt.show()

#delete data that is less than 2 or greater than 6 mg/L
DO_min = 2 * u.mg/u.L
DO_max = 6 * u.mg/u.L
for i in range(1,airflows.size,4):
  idx_start = (np.abs(DO_data[i]-DO_min)).argmin()
  idx_end = (np.abs(DO_data[i]-DO_max)).argmin()
  time_data[i] = time_data[i][idx_start:idx_end] - time_data[i][idx_start]
  DO_data[i] = DO_data[i][idx_start:idx_end]


#Question 3
P=1.009*u.atm
T=293*u.kelvin
Cstar=epa.O2_sat(P,T)
print(Cstar)

#Question 4
#Estimate k̂ v,l using linear regression and equation (103) for each data set.

delta_t=np.empty(airflows.size,dtype="object")
for i in range(airflows.size):
  t_temp=time_data[i].magnitude
  delta_t_temp=t_temp - t_temp[0]
  delta_t[i] = delta_t_temp
  # delta_t=np.append(delta_t,[delta_t_temp])
x=delta_t
print(Cstar)
print(Cstar.magnitude)


y=np.empty(airflows.size,dtype="object")
for i in range(airflows.size):
  do_temp=DO_data[i].magnitude
  numerator = Cstar.magnitude - do_temp
  denominator = Cstar.magnitude - do_temp[0]
  y_temp = np.log(numerator/denominator)
  y[i] = y_temp

kvl = np.empty(airflows.size,dtype="object")
for i in range(airflows.size):
  x_temp = delta_t[i]
  y_temp = y[i]
  slope, intercept, r_value, p_value, std_err = stats.linregress(x_temp, y_temp)
  kvl[i] = slope

print(kvl)
print(airflows.magnitude)



#question 5
#for 175 flow rate
print(airflows[2])





print(DO_data[2].magnitude)
print(DO_data[2][0])

#DO vs t


right_side = np.exp(kvl[5]*(delta_t[5]))
right_side_2 = (Cstar.magnitude - DO_data[5][0])*right_side
C_do = Cstar.magnitude - right_side_2
print(airflows[5])
fig, ax = plt.subplots()
ax.plot(time_data[5],DO_data[5],'r',time_data[5],C_do,'g')
plt.xlabel('Time (s)')
plt.ylabel('Oxygen Concentration (mg/L)')
#plt.savefig('question1')
plt.title('Oxygen Concentration vs Time for 250 μmole/sec')
plt.legend(['DO data', 'DO model'])
plt.show()

print(C_do.magnitude)
print(kvl[0])

# question 6
fig, ax = plt.subplots()
ax.plot(airflows,kvl,'r')
plt.xlabel('airflows')
plt.ylabel('kvl')
#plt.savefig('question1')
plt.show()

#question 7
V = .750*u.L
delta_c = .006*u.gram/u.L
fO2 = 0.21
R = .082 * u.L*u.atm/(u.K*u.mol)
MWo2 = 32 *u.gram/u.mol
nair = airflows.to(u.mole/u.s)
Pair = 1.009 * u.atm




OTE = np.array((kvl*u.s*delta_c*V)/(MWo2*nair*fO2))
print(OTE)

fig, ax = plt.subplots()
ax.plot(airflows,OTE,'r')
plt.xlabel('airflows')
plt.ylabel('OTE')
#plt.savefig('question1')
plt.show()



```
$\ln \frac{C^{*} -C}{C^{*} -C_{0} } =-\hat{k}_{v,l} (t-t_{0} )$
