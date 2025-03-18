# three-in-one-robot

This is part of my learning Fusion 360.  I would like to get better at constraints and parameterizing my designs (even if you don't change parameters, it seems helpful in keeping everything consistent, it forcing you to think about what the important measurements).    Modifying parameters seems to be a good way to realize that your designs are not correctly or properly constrained.   I also need to get better at organizing my designs.

I have several projects that require a rotational platform.   The basic design is to use an aluminum lazy susan and a large main gear with an exterior rotary motor.   Lazy susans make
a very inexpensive and stable platform.   The design will use 3d printed gears, so the only cost in the basic platform is the stepper motor, lazy susan and filament.  By paramaterizing 
the model, any size stepper (as long as they are both the same) and and reasonable set of sizes of platform can be created.  I've only looked at doing this with 6 inch and 8 in - higher
shouldn't be a problem for the model, but quickly gets out of the range of my printer bed

 ![image](https://github.com/user-attachments/assets/7151c1f4-726e-4994-b89f-1011a3320ff9)

 So rather that redo everything up to the rotational platform everytime, I'll create a base platform as a component.
 
 The basic platform mock-up looks like


The center gear could be used to drive a SCARA arm, a radial arm, and the third project I have in mind is a string art project.  
![image](https://github.com/user-attachments/assets/87883334-30a8-41c0-b6ee-92d0d5f486bd)


##
One of the reasons I wanted to do this one is that I built the robot from Matt G at https://alwaystinkering.com/2021/03/12/setting-up-and-configuring-the-sandbot/.   At the time, I 
lacked the 3d modeling skills and the 3d printing skills to do a satisfying job, so I've been meaning revist this at come up with an improved design.   There were a couple of 
issues I wanted to overcome.   The arm had too much play in and tended to drop.  It was also difficult to get everything adjusted correctly for the belts.   I'm intending to address these issues with the design below:


The inner arm is made of up two 5 mm carbon fiber rods (about $9 for a pack of 5 on [Amazon](https://www.amazon.com/MECCANIXITY-Carbon-Fiber-300mm-Quadcopter/dp/B0CTTBSBNN/ref=sr_1_3?crid=23AJ794M031PM&dib=eyJ2IjoiMSJ9.MJMeH6QCTyoHL-ZEP7HK383_D5m7PvBB6umXPj412T82ivodgDwwibtP-o99J82awkXbBVNg6YtYdp0IcY5KSYMnMyv4WD5BTGDfNwqVEZvL3AO2EfehHA3-aUxMxHUbDV3WPDU3brXmNrpYyupg3zEqk20EA3a1WjvzvC-7nav0SX84Rhcg9OvzAG8pIeWm___IUwbI6N8TGsc19B4hIliI1wySKjRjpnN3WFXdPponAJsvwQeWk-QBfgMZVEMf01K42pAfz6SMQs4IGNKMBMFHWvP3rgJJXHq7G8xhCwtAwYNUt0BJbvU_Rj2J92nrpFCMhCWAHMo44yrs9E4OWFgAjeFTK5GGM2dhwCLgc0U.uLn67MjOrLTEv2xcwRVmrgF7J6BWl-cumq0-pPBESwc&dib_tag=se&keywords=5%2Bmm%2Bcarbon%2Bfiber%2Brod&qid=1742215634&s=industrial&sprefix=5%2Bmm%2Bcarbon%2Bfiber%2Brod%2Cindustrial%2C140&sr=1-3&th=1)   I'll add the attachments to the main gear, a end cap to hold the rods together and an adjustable/sliding mechanism to hold the elbow gear and keep the belt snug.  Pretty simple!

The 5 mm carbon fiber rods are incredibly strong.   The trick to getting the sandtable robots working well seems to keep the arm as stiff as possible and provide a cylinder for the magnets that they can freely float up and down (while keeping the cylinder as perpendicular to the table surface as possible.  I think I can do all that with this design.

I'll put a 
length adjustment for the position of the magnet on the outer arm so that the magnet can be in the exact center after homing (I'll include the rotational homing as part of the 
base platform - it's basically an M3 screw dropped through a hole in the main gear).   The height shown is for the smallest NEMA 17 motor I saw on Amazon.  So starting from the base platform, it's pretty easy to come up with the SCARA design.  Homing the radial/SCARA depends on the design of the robot and needs to be in the derived model (homing of the SCARA is done by gettng the rotational to a known postition and then rotating the outer arm until it sees an optical/hall effect sensor).    A radial design can be done in a very similar manner ... it usual involves getting the rotation to a known spot first.

## 
The second design (actually the first I'm planning) is a radial arm Polar robot.    In this case the central gear drives a radial arm.  I wanted to get the base platform in good shape first.   Once that's done the radial design - very similar to the [Dune Weaver project] (https://github.com/tuanchris/dune-weaver) is just a matter of attaching the radial arm.   I would use the Dune Weaver software ... which is pretty great to control the robots.   I think Tuan has come up with the right approach by using off-the-shelf hardware and software for the stepper control (Fluidnc running on the mksdlc32) and then using a Raspberry Pi Zero 2w with code written in python for the user interface.  Both Tuan/Dune Weaver and Fluidnc deserver your (and my!) support.
##
The third design I wanted to explore is a string art machine.   My son wrote a program to transform images to string art, and I've been meaning to implement it.   I wanted to explore 3d printing the "pins".

##
There's a fourth design I've been thinking about.  Both the SCARA and radial arm robot need to make adjustments on the radial/elbow motor - basically they need to turn their gears at the same speed/direction as the main gear is moving in order to stay still.   This is easily done in software - but if you were a victorian steampunk engineer and wanted a purely mechanical solution to this issue, the solution would be to use a differential (one "wheel" gets driven at the speed the main gear is turning, the other acts like there's no coupling between the two.   You then use the "drive shaft" to control the SCARA arm or radial arm).   I've gotten as far as looking into RC model car differentials.   It's a pretty insane, convulated way to do things, but who wouldn't want a robot with a differential?
##
![image](https://github.com/user-attachments/assets/722deff9-4102-434f-8175-697cf08c401c)


