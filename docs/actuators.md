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
