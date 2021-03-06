# Assembly guide for the Poppy Torso
## Robot overview
Here is the overview of the robot you are about to assemble, its 13 motor names and their associated digital id.
![](../../img/humanoid/torso-motors.png)

## Videos
This assembly guide can be followed by the means of videos splitted in 25 steps (25 consecutive videos). You will find the relevant video links in the detailed steps, however, if you prefer to follow only the video playlist, here is the link to the [Poppy Humanoid assembly video playlist](https://www.youtube.com/watch?v=SUlM_mE3plc&list=PL8wg9_Kkof8wwqgfFu0iCij73C-4gt95x&index=1).

Just note that your kit and the Poppy software may differ a bit from what you see in the videos. In particular:
* The videos showcase the assembly of a full Poppy Humanoid, but obivously you will not assemble the legs 
* The MX-28 motor is now obsolete and is being replaced by MX-28AT, almost identical except that one of its side is already threaded: then it won't be necessary to use nuts on this side if you must insert a screw there.
* The herborist software used in the videos requires to enter the configuration parameters of each motor (communicaiton speed, digital id, ...) but the Poppy Configure tool can replace Herborist: it does the same just but you will only have to know the motor name e.g. `bust_x`
* There is no video assembly of the head

## Assembly guide
Prepare your workbench and tools and then follow the guide step-by-step, in the list hereunder. Enjoy the assembly!

1. [Primordial warnings](warnings.md) 
2. [Bill of Material](bom.md)
3. [Mounting Dynamixel horns](dynamixel_hardware.md)
4. [Configuring Dynamixel motors](addressing_dynamixel.md)
5. [Arms assembly](arms_assembly.md)
6. [Full torso assembly](trunk_assembly.md)
7. [Head assembly](head_assembly.md)
8. [Wiring arrangement](wiring_arrangement.md)
9. Assembly is over, check out the [Programming](../../programming) section.

## Additional information
The repositories below host older documentation that you your might also checkout:
* [Poppy minimal head design](https://github.com/poppy-project/Poppy-minimal-head-design/tree/raspberry-pi-integration/)
* [Poppy multiarticulated torso](https://github.com/poppy-project/Poppy-multiarticulated-torso/tree/master/)
* [Poppy Torso](https://github.com/poppy-project/poppy-torso)

## Credits
Authors:
* [Manon Cortial, Génération Robots](http://www.generationrobots.com/en/278-le-robot-poppy-Torso)
* Matthieu Lapeyre
* Théo Segonds
* Yoan Mollard
![image](img/GR-logo.png)
