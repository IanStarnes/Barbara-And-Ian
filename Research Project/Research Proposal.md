# Research Proposal
#### Ian Starnes and Barbara Oramah
##### Group 6

##### Introduction

What is the problem? Why is it important?

The focus of this research will be testing the effect of filtration of activated carbon and sand with differing diameter sizes. This will

Activated carbon is charcoal that is treated with oxygen to open up million of pores in the carbon atom. This feature is what makes activated carbon a desirable material in filter as it has a large surface area that can adsorbs different chemicals.


##### Objectives
What is the hypothesis? What will you do to test the hypothesis?

Our hypothesis is that the smaller the activated carbon mesh sizes we use, the better the filter will perform. This is because the particles will have a great surface area to volume ratio that will allow more red dye to be adsorbed on to the surface. For the smaller mesh sizes, the red dye will take longer to reach the center of the activated carbon particle.


##### Experimental plan
How will you measure it?

We will vary the type of activated carbon to see how the mesh size effects the filtration efficiency. This can be measured the same was as was done in the absorption lab with the photometer. Additionally, time and resources permitting, we will vary the type of sand we use, the ratio of sand to activated carbon, and flow rates. The efficiency will again be measured with the photometer.

Key design parameters

1. Activated Carbon - different mesh sizes
2. Sand - different types
3. varying ratio of sand and activated carbon
4. flow rates ?

(in order of what we will vary time and amount of activated carbon dependent)

##### Timeline of tasks/experiments

1. Confirm our experiment with Prof. Weber Shirk

2. Order the activated carbon online

3. Set up workstation

4. Run experiment with different mesh sizes

5. Run experiment with different sands

6. Run experiment with different ratios of sand and activated Carbon

7. Data analysis - dispersed between experiments

##### Possible hurdles/challenges

We might to run experiments overnight depending of the set up.

We might need to back wash to reuse the AC.

We plan to add sand to previous experiments to vary the AC to sand ratios.

##### Resources needed to conduct experiments – What tools will you use?

Materials:

  Activated Carbon:
- untreated, granular, ≤5 mm (500g - $36.60)
- untreated, granular, 8-20 mesh (500g - $37.60)
- powder, -100 particle size (mesh), decolorizing (175g - $48.00)

  or

- DARCO®, 4-12 mesh particle size (250g - $44.30)
- DARCO®, 12-20 mesh, granular (250g - $44.30)
- DARCO®, 20-40 mesh particle size, granular (250g -$45.50)
- DARCO®, −100 mesh particle size, powder (250g - $45.80)

[link here](https://www.sigmaaldrich.com/catalog/search?term=activated+carbon&interface=All&N=0&mode=match%20partialmax&lang=en&region=US&focus=product)
- Sand (varying diameter ?)

- Red Dye #40
- Reverse Osmosis Water
- A bunch of T-valves
- Pump
- Peristaltic Tubing
- Activated Carbon Filter
- Photometer

##### Expectations/Anticipated results

For smaller mesh activated carbon the efficiency of the filter will be less than that of larger mesh activated carbon. This is due to the red dye taking longer to reach the center of the for larger particles. For the different types of sand we anticipate better filtration for the smaller sand particles. For higher AC to sand ratios we anticipate higher efficiencies. For lower flow rates we anticipate higher efficiencies.

##### References/Bibliography

Refs to primary, review, and other literature and possibly to previous years’ projects

https://www.mne.psu.edu/cimbala/me433/Lectures/Activated_Carbon_or_Charcoal_Filters.pdf

https://search.proquest.com/docview/2021147763?pq-origsite=summon

https://www.sciencedirect.com/science/article/pii/S1001074209601637

https://permanent.access.gpo.gov/gpo70466/a_citizens_guide_to_activated_carbon_treatment.pdf


Experimental Set-Up

20% Activated carbon(20-40 mesh size) by mass
80% sand
Mixed together

Mass of sand = 121.975 g
Multiply sand by 0.25 to get mass of AC
Mass of activated carbon = 30.493 g

75.156g mass remaining of mixed ration


Main issue faced: air bubble in our system

Volume of red dye, look at the


17th April
We tried running an experiment with -100 mesh (Used a ratio of 9:1 of sand and activated carbon )
Observation : the AC is too fine and it went through the mesh of the filters. We also did not tighten the filter enough and we did not align the mesh well as that led to some sand escaping the filters

We decided to face this issue for another day,

running an experiment with the 20-40 AC mesh with a ratio of 9:1 sand and AC



19th April 2019

Trying to figure out ways to change mesh filter for when we run -100 mesh AC. Promising observations with paper towels as a replacement.
Ian is now very excited trying to find different types of paper filters to use in the lab.

Current contenders:
Kimwipe
Brown Paper towel
White paper towels
Coffee Filter


note from rosie: pressure build up
note from ian: put mesh on both sides
note from jiwon: we're doing amazing sweetie

24th April

Running the -100 mesh for 2 days using 2 coffee filters as a mesh

checked the flow rate: 17 tubing size
set pump to 5 rpm  - flow rate recorded at 8 mL/min

(40 mL in 5 minutes)

looking at table 2 pump tubing selection
flow rate in 1 RPM gives 0.0467 mL/min  



25th April 2019

4-12 mesh arrived

Ran experiment with 9 to 1 ratio

Measure flow rate:
- 35 mL in 2.5 minutes


26th April 2019

20-40 mesh test
 Measured flow rate:
 - 28 mL in 2 minutes



29th April 2019

We are interested in finding a material that will physically stop -100 mesh from flowing out of our filter.

we will be measuring different mediums such as:

Current contenders:
Kimwipe
Brown Paper towel
White paper towels
Coffee Filter

We will be adding a pressure sensor in the influent stream and we will make a granular AC standard for our photometer so we can accurately measure how much AC is going through.

Running at 10 RPM

Making an Activated Carbon Standard
- running DI water (Blank Voltage) reading -0.43 mg/L

0.6 g/L

0.154 g in 500 mL = 0.308g/L


White paper towels from Bench 7
2200 cm of water - roughly 2.1 atm
Concentration - -0.58 mg/L

- made AC standard between experiments

Brown paper towels from Bench 5/6
Pressure -  1900 cm of water
Concentration - 0.09 g/L






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



 ```





**Brainstorming**
- Like looking at turbidity
- grinding down some AC and seeing how the different sizes of AC will be
- get sludge from ithaca beer brewery
- wastewater

volumes
concentration
etc.
things that are varying
