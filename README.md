# About
This is a PLC project with multiple ladder logic, structured text, and function block diagram programs that includes indexed sequences, latched sequences, timers, and pulse generators.

The system is an imaginary cookie vending machine that automatically produces cookies from scratch when the user presses a button. All the ingredients are assumed to be stored properly at an appropriate temperature and can be dispensed with machines into a large mixing bowl. The mechanical systems and actuators are not simulated and are assumed to function properly. This project is only modelling the control system.

Software
 - Connected Components Workbench (Allen Bradley)
Hardware:
 - Allen Bradley Micro800 Simulator

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

Up to 8 sticks of butter can be stocked in the machine. A low stock warning triggers at 1 stick remaining. A photoelectric sensor on the bottom of the stack detects when butter stock is empty and triggers a low stock error. Pressing the restock button resets the count to 8 assuming the dispenser has been refilled to the max. The low stock error may appear before the warning if stocked to less than full capacity.

## Sugar Dispenser
The sugar dispenser dispenses sugar at a constant rate while receiving a high signal. The PLC determines when to cutoff sugar dispensing based on the weight of the bowl. The distance between the dispenser and the bowl that would contain extra sugar from when the weight reached the desired amount and the dispenser signal was cutoff is assumed to be negligible.

The sugar is simulated to dispense at a rate of 100g/s by generating a pulse with a 250ms period and dispensing 25g each period.

Two photoelectric sensors are in the sugar tank. One is located about a 1/4 of the height from the bottom to indicate low level. And the second is near the opening at the bottom to indicate empty.

## Egg Dispenser

The egg dispenser requires a high pulse for every egg it should dispense. The timing of the pulses to not affect the speed of dispensing eggs. The dispenser counts how many pulses it receives and then dispenses that many eggs at its own rate.

The controller does not receive any feedback from the egg dispenser about when eggs have been dispensed. And because vanilla is being dispensed at the same time, weight measurements might be tricky to detect. So the controller simply delays an estimated amount of time for an egg to dispense multiplied by the number of eggs in the recipe.

## Vanilla Dispenser

The vanilla dispenser requires a high signal to dispense drops. While dropping, the dispenser outputs a pulse where each high represents a successful drop of vanilla dispensed.

The controller counts the number of drops from the dispenser output signal and turns the signal low when the required drops has been achieved.

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

# Documentation
View the ladder logic and variables in the [documentation](https://github.com/ethanmcmike/cookie_vending_machine/blob/main/docs/Micro850.pdf).
