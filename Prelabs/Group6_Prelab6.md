### Ian Starnes and Barbara Oramah
#### Pre-Lab 5, Group 6

##### Pre-lab Question

1. A carbon column is packed with 15 cm of activated carbon and then used to remove 50 mg/L of red dye #40. The approach velocity is 1 mm/s, the porosity is 0.4, and the bulk density of the activated carbon is 0.5 g/cm3. How long will it take for the mass transfer zone to travel to the bottom of the carbon column?


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
