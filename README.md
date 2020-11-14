# G-Code to CW/CCW
G-Code translate to CW/CCW protocol for driving СNC. __
CW - rotate stepper motor clockwise; __
CCW - rotate stepper motor counterclockwise.
This program translate G-Code to the sequence of bits.
For example: 
bit 0 - X axis CW; 
bit 1 - X axis CCW;
bit 2 - Y axis CW;
bit 3 - Y axis CCW;

This sequence of bits will cause the engine to take 2 steps counterclockwise (Y-axis stepper motor) and 2 steps clockwise (Y-axis stepper motor): 
00001000 - (1)This byte was received as a result of the program
00000000 - (2)This byte must be inserted on the side of the microcontroller or other device that sends CW/CCW signals to the stepper motor driver
00001000 - (1)
00000000 - (2)
00000100 - (1)
00000000 - (2)
00000100 - (1)

5 bits is used to turn the laser and etc on/off state.
Bit state is determined by negative value of Z axis in G-Code.



