plotclock
=========

My copy of Johannes's awesome plotclock
See: http://www.thingiverse.com/thing:248009/#instructions

In simple words, a clock that plots time

What is changed in this fork
-------------
- This is assembled with different HW from Taobao.com. See link below. Updated sizes according to new HW.
- Added calibration routine for lift and for sweep position for easier setup for beginners like me
- Changed width of sweep function

How To:
--------
This kit was purchased: https://item.taobao.com/item.htm?spm=a1z09.2.0.0.20ff2e8dlEPqDe&id=39370904218&_u=q201fslvce58e0

Start by assembeling all components expept from attaching the arms to the servos.

Remove the // in front of //CALIBRATION_ARMS and upload to the arduino controller. This will drive the top two servos 90~ish Degrees with 0.5 seconds between each cycle. 
When both servos are turning clockwise and comes to a stop, remove the power to the arduino and install the arms on the servos. Install arms so that the Right Servo arm is horizontal and pointing to the right, and the left servo arm is pointing upwards. 
Install the arms as close as possible to horizontal and vertical positions

For the Lift servo, attach the arm to the servo so that the angle of the arms on the top two servos are parallel with the drawing board.

Power the arduino back up and verify correct arm movement, when left servo is pointing left, the right points upwards, when left servo points upwards, the right servo point right. 

As the servos are most likely not bang on at this point, we need to adjust the starting position of its 90 Degree travel, which is the horisontal position of the arm.
Adjust "#define SERVOLEFTNULL 2170" value until its dead on in the horisontal position. Do the same for the Right servo. Start by adjusting with +100 to get the feeling of what direction you need to move and how much.

Once the arms have a starting position that is horizontal, the "#define SERVOFAKTORLEFT 710" can be adjusted to ensure that the servo is moving exactly 90 degrees. Do this for Right servo also.

Put the // back in front of "#define CALIBRATION_ARMS" and remove the // in front of "//#define CALIBRATION_LIFT".
Pen holder should move to center of drawing board and lifting servo will start to move in steps between the positions.

Turn off power to arduino, install the pen firmly in the holder and then power back on the arduino, adjust the lift heights so that there is applied some pressure on the drawing board with the pen when at "LIFT0" and so that there is a 1-2mm air gap between pen and drawing board on "LIFT1" and adjust "LIFT2" so thats the tip of the pen clears the height of the sweeper.

Adjust #define SweepX 72.1 and Y for sweeper position while running CALIBRATION_SWEEPER.

Put back the "//" in front of the CALIBRATION_XXX to start writing the current time on your arduino.



------------------------

This is my first git project and its as much about learning Github as learning the plotclock.
