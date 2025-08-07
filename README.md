# About
This is a test project to learn ladder logic, PLC, and HMI using Allen Bradley's Connected Components Workbench and a Micro850 simulator along with FactoryTalk.

The system is an imaginary cookie vending machine that automatically produces cookies from scratch when the user presses a button. All the ingredients are assumed to be stored properly at an appropriate temperature and can be dispensed with machines into a large mixing bowl. The mechanical systems and actuators are not simulated and are assumed to function properly. This project is only modelling the control system.

# I/O
Input Signals:
 - Start process push button
 - Weight of bowl [grams]
 - Photoelectric sensors near conveyor (when tray is in oven, at user presentation window, and returned to bowl)
 - Ingredient storage levels

Output Signals:
 - Dispense a stick of butter
 - Dispense sugar at a set rate
 - Dispense contents of a single egg
 - Dispense a drop of vanilla
 - Dispense flour at a set rate
 - Mix contents of bowl
 - Remove dough from bowl and form balls on tray (simplified into a single control signal)
 - Clean bowl
 - Advance conveyor belt
 - Reverse conveyor belt
 - Start oven
 - Present cookies to user

# Actuators
## Butter Dispenser
The butter dispenser dispenses a stick of butter for every high pulse received. It has not sensor or output to verify the butter has been dispensed and is assumed to be mechanically reliable.

## Sugar Dispenser
The sugar dispenser dispenses sugar at a constant rate while it receives a high signal. The PLC determines when to cutoff sugar dispensing based on the weight of the bowl. The distance between the dispenser and the bowl that would contain extra sugar from when the weight reached the desired amount and the dispenser signal was cutoff is assumed to be negligible.

# Recipe
The user will be able to define ingredient quantities to adjust the recipe as desired. For example a recipe might look like:
 - 1 stick of butter
 - 250 grams sugar
 - 2 eggs
 - 5 drops vanilla
 - 300 grams flour

# Process
1. Dispense butter, sugar
2. Mix
3. Dispense eggs, vanilla
4. Mix
5. Dispense flour, baking soda
6. Mix
7. Form balls from dough on tray
8. Transfer tray to oven and bake
9. Start bowl cleaning
10. Present tray to user

# Documentation
View the ladder logic and variables in the [documentation](https://github.com/ethanmcmike/cookie_vending_machine/blob/main/docs/Micro850.pdf).
