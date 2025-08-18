# Refrigerator

## Thermodynamics
This is a rough approximation for modelling the fridge thermodynamics. The heat capacity of the air and eggs are lumped together so that the conduction from the air to the eggs is assumed to be instantaneous.
The only factors for the air temperature are 1. conduction through the fridge walls, 2. the transfer of warm air while the door is open, and 3. the transfer of cold air from the condensor/fan.

Fridge dimensions: 0.3 x 0.5 x 0.5m

Volume = 0.075m^3

Air density = 1.225kg/m^3

Air mass = 0.0919kg

Specific heat capacity of air = 1000J/(kg*degC)

Heat capacity of air = 91.9J/degC


Max number of eggs: 24

Single egg mass = 57g = 0.057kg

Max eggs mass = 1.37kg

Specific heat capacity of egg = 3320J/(kg*degC)

Heat capacity of eggs = 4540J/degC


Total heat capacity = 4630J/degC

Fan volume flow rate = 0.5m^3/min

Fan mass flow rate = 0.6125kg/min

Heat exchange from fan := (Mass flow rate) * (Heat capacity) * (Temperature difference)

Heat exchange from door := (Mass flow rate) * (Heat capacity) * (Temperature difference)

(Change in temp) = (Change in time) * ((Heat exchange from door) + (Heat exhange from fan) + (Heat exchange from walls)) / (Total heat capacity)
