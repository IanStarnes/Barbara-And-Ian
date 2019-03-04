### Ian Starnes and Barbara Oramah
#### Pre-Lab 4, Group 6

1. Calculate the change in hydraulic grade line between baffled sections of a reactor with a flow rate of 380 mL/min. The reactor baffles are perforated with 6 holes 1 mm in diameter. Is the flow through these orifices in series or in parallel? Do you multiply the head loss for one orifice by the number of orifices to get the total head loss? Are the orifices in parallel or in series? Use the pc.head_orifice function to calculate the head loss through an orifice. The vena contracta for the orifice can be found at aguaclara.core.constants.VC_ORIFICE_RATIO. Why would 6 holes 1 mm in diameter not be a good design for this reactor?

The flow through the orifices is in parallel. Using equations (82) and (83), the ration of head from an individual orifice to total head is

$$\frac{\Delta h_{total}}{\Delta h_{1orifice}} = \frac{1}{n_{orifices}^{2}}$$

The orifices are in parallel.

```Python

import aguaclara.research.environmental_processes_analysis as epa
import aguaclara.core.physchem as ep
from aguaclara.core.units import unit_registry as u
import matplotlib.pyplot as plt
import numpy as np
from aguaclara import *

RatioVCOrifice=0.63
Diameter=0.001 * u.m
FlowRate=0.00633 * (u.m ** 3)/u.s
n=6
head=ep.head_orifice(Diameter,RatioVCOrifice,FlowRate)
head
total_head=head/(n*n)
total_head
```

2. On a single graph plot the exit age distribution (E(t⋆)) for a reactor that operates as a 1-dimensional advection-dispersion reactor with Peclet numbers of 1, 10, and 100 (there will be three plots on the graph and thus a legend is required). The x-axis should be t⋆ from 0.0 to 3.0. Comment on the shapes of the curves as a function of the Peclet number. Note that the advective dispersion equation is undefined for t⋆=0. Use the epa.E_Advective_Dispersion(t,Pe) function.

```Python

import aguaclara.research.environmental_processes_analysis as epa
from aguaclara.core.units import unit_registry as u
import matplotlib.pyplot as plt
import numpy as np

t=np.linspace(0,3,100)
E_1=epa.E_Advective_Dispersion(t,1)
E_10=epa.E_Advective_Dispersion(t,10)
E_100=epa.E_Advective_Dispersion(t,100)

fig, ax = plt.subplots()
ax.plot(t, E_1, 'r',t,E_10,'b',t,E_100,'g')
ax.legend([ 'Pe=1','Pe=10', 'Pe=100'])
ax.set(xlabel= 't* (unitless)')
ax.set(ylabel= 'E(t*) (unitless)')
ax.grid(True)
plt.savefig('Peplot.png')
plt.show()

```
<p align="center"> <img src="https://github.com/IanStarnes/Barbara-And-Ian/blob/master/images/Peplot.png" heights=310 width=927> </p>

With higher Peclet numbers, more and more of the mass leaves the reactor at one residence time. This happens because as the Peclet number approaches infinity if becomes more like a perfect plug flow reactor. A Peclet number of 100 has some dispersion but is most like a plug flow reactor out of these three options. As the Peclet number decreases, there is more dispersion. Therefore, some of the mass exits the reactor before one residence time. This effect is seen to be more important for Peclet numbers 1 and 10. For these scenarios, more mass is leaving the reactor much sooner but it also has mass leaving the reactor at much higher residence times. The mass flow out of the reactor tappers off unlike when the Peclet number is 100.
