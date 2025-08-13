# About
This is a PLC project with multiple ladder logic programs that include sequences, timers, pulse generators, low-level warnings, and error management.

The system is an imaginary cookie vending machine that automatically produces cookies from scratch when the user presses a button. All the ingredients are assumed to be stored properly at an appropriate temperature and can be dispensed with machines into a large mixing bowl. The mechanical systems and actuators are not simulated and are assumed to function properly. This project is only modelling the control system.

Software:
 - Connected Components Workbench
 - FactoryTalk Optix Studio

Hardware:
 - Micro850 Simulator

# Documentation
View the ladder logic and variables in the [documentation](https://github.com/ethanmcmike/cookie_vending_machine/blob/main/docs/Micro850.pdf).

<img width="1265" height="152" alt="image" src="https://github.com/user-attachments/assets/dbfe6030-1a1c-462a-a6f9-6d827801caee" />

# HMI
The interface is simple yet functional. The user can start a process, view the active components, reset the stock values, and modify the recipe.

<img width="402" height="432" alt="image" src="https://github.com/user-attachments/assets/09a8c74e-1af5-4fb8-abbd-fa6ac3ecf66a" />

<img width="402" height="432" alt="image" src="https://github.com/user-attachments/assets/db807d22-a612-4f0c-b0c8-f02c56b80053" />

# I/O
Input Signals:
 - Push buttons
 - Weight scale
 - Photoelectric sensors
 - Float switches

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

# Recipe
The user will be able to define ingredient quantities to adjust the recipe as desired. For example a recipe might look like:
 - 1 stick of butter
 - 250 grams sugar
 - 2 eggs
 - 5 drops vanilla
 - 300 grams flour

# Process
1. Dispense butter
2. Dispense sugar
3. Mix
4. Dispense eggs, vanilla
5. Mix
6. Dispense flour
7. Dispense baking soda, salt
8. Mix
9. Form balls from dough on tray
10. Transfer tray to oven and bake
11. Start bowl cleaning
12. Present tray to user
