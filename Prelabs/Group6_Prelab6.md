### Ian Starnes and Barbara Oramah
#### Pre-Lab 5, Group 6

##### Pre-lab Question

1. A carbon column is packed with 15 cm of activated carbon and then used to remove 50 mg/L of red dye #40. The approach velocity is 1 mm/s, the porosity is 0.4, and the bulk density of the activated carbon is 0.5 g/cm3. How long will it take for the mass transfer zone to travel to the bottom of the carbon column?

The mass transfer zone will take **33.3 hours** to travel to the bottom of the column.

### Appendix
```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.utility as ut
import numpy as np

length_column = 15*u.cm
v_a = 1 * u.mm/u.s
porosity = 0.4
C_0 = 50*u.mg/u.L
bulk_density =  500000 * u.mg/u.L
q_0 = 0.08
t_water = (length_column*porosity/v_a).to(u.s)
R_adsorption = (q_0*bulk_density/(porosity*C_0))
t_mtz = t_water*R_adsorption
t_mtz/3600 * u.hr/u.s
```

```python
from aguaclara.core.units import unit_registry as u
import aguaclara.core.physchem as pc
import aguaclara.core.utility as ut
v_a = 1 * u.mm/u.s
porosity = 0.4 #porosity of 
L_column = 15.2 * u.cm #length of filter
D_column = 1*u.inch #diameter of filter
A_column = pc.area_circle(D_column) #area of filter
V_column = A_column * L_column #volume of filter
C_0 = 50 * u.mg/u.L # concentration of red dye to remove
q_0 = 0.08 #bulk density
t_water = (L_column*porosity/v_a).to(u.s)
t_mtz_target = 1800*u.s
# set the breakthrough time to 30 minutes = 1800 s
R_adsorption = t_mtz_target/t_water
M_ac = ((R_adsorption-1)*C_0*porosity*V_column/q_0).to(u.g)
print('The mass of activated carbon given the dilution with sand should be',ut.round_sf(M_ac,2))
Density_AC = 2100 *u.kg/(u.m**3)
#We measured the bulk density in the lab
Density_bulk_AC = 386 * u.kg/u.m**3
V_carbon = (M_ac/Density_bulk_AC).to(u.mL)
print('The volume of activated carbon is approximately',ut.round_sf(V_carbon,2))
density_sand = 2650 * u.kg/u.m**3
M_sand = ((V_column-V_carbon)*density_sand*(1-porosity)).to(u.g)
print('The mass of sand is',ut.round_sf(M_sand,2))

V_reddye = (v_a*A_column*t_mtz_target).to(u.L)
print('The volume of red dye required for one experiment is',ut.round_sf(V_reddye,2))
Q_reddye = (v_a*A_column).to(u.mL/u.min)
print('The flow rate is',ut.round_sf(Q_reddye,2))
mLperrev_Tubing_17 = 2.8 * u.mL/u.revolution
Pump_rpm = (Q_reddye/mLperrev_Tubing_17).to(u.revolution/u.min)
print('The pump rpm is',ut.round_sf(Pump_rpm,3))

```
