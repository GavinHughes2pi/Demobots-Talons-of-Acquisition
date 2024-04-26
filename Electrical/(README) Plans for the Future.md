# TOA Electrical Plans

## What's been done
- We have the motors
- We have some stepper drivers
- We have wires
- We have a joystick
- We have buttons
- We have limit switches
- We have a servo for the claw

## What we need to do
- Write joystick control program
- Figure out the motor drivers (which ones work?)
- Wire everything together
- Autonomous claw homing using limit switches

## What needs to be acquired
- New Arduino (or other method of controlling)
- New stepper drivers (if there aren't enough working ones)
- Other

## Tips and Tricks
- There are two motors for the x axis, and one motor for the z axis. Wire the "step" pin of the two x motors to the same digital pin for 100% synchronous control.
- Stepper drivers may have different colors and slightly different pins, but they're all pretty much the same thing at their core. ![image](https://github.com/GavinHughes2pi/Demobots-Talons-of-Acquisition/assets/112124643/bd29157a-7faf-47fe-8852-0166f1100bc2)

  This diagram should help you greatly.

- Using simple delays to drive the step pins of the stepper motors might be fine for a while, but as the code grows in complexity the steppers might start to jitter (the additional code might cause delays). Using a library like Stepper() or AccelStepper() might help alleviate this issue.
- The joystick has four limit switches, two of which can be pressed at a time (for diagonal control). Do your checks for the switches BEFORE doing any stepper stuff.
- There are some limit switches available to use for homing the stepper motors. 3D printers home themselves by moving the stepper until the switch is hit, then moving backwards until the switch is un-hit, then moving *slowly* until the switch is hit again.
- Since this isn't a precise machine, a homing sequence isn't really needed upon powering it on. However, you should still use the limit switches and aforementioned homing method to guide the claw towards the prize bin.
- **Be careful when doing stuff with the stepper motors! Do not disconnect or connect the stepper wires while the driver is energized. You may damage the motor that way!**
- You can power an Arduino using anywhere from 9 to 12 volts using its barrel jack. Using some clever wiring, you might be able to power both the stepper drivers AND the microcontroller using the same power source.
- **Be careful when wiring up the stepper motor drivers to the Arduino while your Arduino is connected to your computer. Certain configurations may cause the USB port to overload, requiring you to restart your computer (or worse...)**
- A protoboard shield (it's a thing that fits over an Arduino and lets you solder stuff like headers to it) might be useful to use.

Q: Where's the code?

A: There is no code. You gotta write it. Sorry.


Q: But I don't know how to write code!

A: ChatGPT is your friend.
