# cookie_vending_machine
PLC/HMI learning project

This is a test project to learn ladder logic, PLC, and HMI using Allen Bradley's Connected Components Workbench and a Micro850 simulator along with FactoryTalk.

The system is an imaginary cookie vending machine that automatically produces cookies from scratch when the user presses a button. All the ingredients are assumed to be stored properly at an appropriate temperature and can be dispensed with machines into a large mixing bowl. I am not simulating or thinking through all the mechanical systems of how ingredients are dispensed or how the dough is transferred, only the control system assuming that those systems are in place.

Input:
Start process button
Weight of bowl

Output:
Dispense a stick of butter
Dispense sugar at a set rate
Dispense contents of a single egg
Dispense a drop of vanilla
Dispense flour at a set rate
Mix contents of bowl
Remove dough from bowl and form balls on tray (simplified into a single control signal)
Clean bowl
Advance conveyor belt
Start oven
Present cookies to user

The user will be able to define ingredient quantities to adjust the recipe as desired. For example a recipe might look like:
1 stick of butter
250 grams sugar
2 eggs
5 drops vanilla
