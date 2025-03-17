# three-in-one-robot

This is part of my learning Fusion 360.  I would like to get better at constraints and parameterizing my designs (even if you don't change parameters, it seems helpful in keeping everything consistent, it forcing you to think about what the important measurements).    Modifying parameters seems to be a good way to realize that your designs are nt correctly or properly constrained.   I also need to get better at organizing my designs.

I have several projects that require a rotational platform.   The basic design is to use an aluminum lazy susan and a large main gear with an exterior rotary motor.   Lazy susans make
a very inexpensive and stable platform.   The design will use 3d printed gears, so the only cost in the basic platform is the stepper motor, lazy susan and filament.  By paramaterizing 
the model, any size stepper (as long as they are both the same) and and reasonable set of sizes of platform can be created.  I've only looked at doing this with 6 inch and 8 in - higher
shouldn't be a problem for the model, but quickly gets out of the range of my printer bed

 ![image](https://github.com/user-attachments/assets/7151c1f4-726e-4994-b89f-1011a3320ff9)

 So rather that redo everything up to the rotational platform everytime, I'll create a base platform as a component.
 
 The basic platform mock-up looks like


The center gear could be used to drive a SCARA arm, a radial arm, or the third project I have in mind is a string art project.
![Screenshot 2025-03-17 030009](https://github.com/user-attachments/assets/b0413ac4-e037-4e04-8d18-cb22f687676a)

##
One of the reasons I wanted to do this one is that I built the robot from Matt G at https://alwaystinkering.com/2021/03/12/setting-up-and-configuring-the-sandbot/.   At the time, I 
lacked the 3d modeling skills and the 3d printing skills to do a satisfying job, so I've been meaning revist this at come up with an improved design.   There were a couple of 
issues I wanted to overcome.   The arm had too much play in and tended to drop.  It was also difficult to get everything adjusted correctly for the belts.   I'm intending to address these
issues with the design below:

![image](https://github.com/user-attachments/assets/7c24c6e4-ea0a-4da1-af87-2058fd109eb3)

The 5 mm carbon fiber rods are incredibly strong - the end mechanism is a belt tensioning mechanism that slides along the carbon fiber rods and holds the outer arm.   I'll put a 
length adjustment for the position of the magnet on the outer arm so that the magnet can be in the exact center after homing (I'll include the rotational homing as part of the 
base platform - it's basically an M3 screw dropped through a hole in the main gear).   The height shown is for the smallest NEMA 17 motor I saw on Amazon.  So starting from the base platform, it's pretty straightforward to come up with the SCARA design

## 
The second design (actually the first I'm planning) is a radial arm Polar robot.    In this case the central gear drives a radial arm.  I wanted to get the base platform in good shape first.   Once that's done the radial design - very similar to the 

![image](https://github.com/user-attachments/assets/9a00e299-d5dc-4667-90a2-b11da11c8dfb)

is just a matter of attaching the radial arm.
##
The third design I wanted to explore is a string art machine.   My son wrote a program to transform images to string art, and I've been meaning to implement it.   I wanted to explore 3d printing the "pins".

##
There's a fourth design I've been thinking about.  Both the SCARA and radial arm robot need to make adjustments on the radial/elbow motor - basically they need to turn their gears at the same speed/direction as the main gear is moving in order to stay still.   This is easily done in software - but if you were a victorian steampunk engineer and wanted a purely mechanical solution to this issue, the solution would be to use a differential (one "wheel" gets driven at the speed the main gear is turning, the other acts like there's no coupling between the two.   You then use the "drive shaft" to control the SCARA arm or radial arm).   I've gotten as far as looking into RC model car differentials.   It's a pretty insane, convulated way to do things, but who wouldn't want a robot with a differential?
##
![image](https://github.com/user-attachments/assets/722deff9-4102-434f-8175-697cf08c401c)


