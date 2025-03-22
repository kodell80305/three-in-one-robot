# three-in-one-robot

This is a work in progress, and these are my notes.

I'm mostly doing this at least partially as an exercise to improve my 3d modeling skills. 


I would like to get better at constraints and parameterizing my designs (even if you don't change parameters, it seems helpful in keeping everything consistent, it forcing you to think about what the important measurements).    Modifying parameters seems to be a good way to realize that your designs are not correctly or properly constrained.   I also need to get better at organizing my designs.  Below is the current version of the basic platform.   This one uses a 6 inch lazy susan, 23 mm pancake stepper motors and the motor shafts cut down as much as possible.

![Screenshot 2025-03-19 143729](https://github.com/user-attachments/assets/45b9fb46-51ea-482a-8214-f8abd84f57f3)

The second one is more traditional with an 8 in lazy susan, 38 mm motors.  To get the build to the basic platform, you'll need  two stepper motors of the same size and either a six inch or eight inch lazy susan (8 inch is best unless it's too large for either the space or your printer).  There is a base which can be mounted on threaded rods/offsets for leveling/tramming, a holder for the center part of the lazy susan and the 3d printed gears.  There will be a rotation sensor mount, a radial sensor mount and one for the SCARA outer arm, 16 short M4 bolts and 16  M4 heated inserts.  There will be a couple of additional M3 screws and associated heat inserts (a USB C soldering iron + heat inserts is ne of my favorite 3d printing gotos.  I can be done with assembly where normally I would be looking for the nut/washer I dropped on the floor)  Minimal parts to print, so it's a very easy build.

![Screenshot 2025-03-18 105408](https://github.com/user-attachments/assets/6667d86c-5a57-4203-88a5-3525c1b6c738)

I'll use the first to build a Dune Weaver https://github.com/tuanchris/dune-weaver Ombonod style robot with the radial arm the same length/gear modulus,  gear ratio of the rotational.    It should be fully software compatible.  I haven't yet designed the rotational/radial sensors holders in the basic platform, but the Ombonod Dune Weaver. doesn't use these anyway.  I used a 6 inch lazy susan for the "Polar Sandtable" robot and was able to fit a Hall effect radial/optical rotational sensor in, so I'll pull that design in.   

I have several projects that require a rotational platform.   The basic design is to use an aluminum lazy susan and a large main gear with an exterior rotary motor.   Lazy susans make
a very inexpensive and stable platform.   The design will use 3d printed gears, so the only cost in the basic platform is the stepper motor, lazy susan and filament.  By paramaterizing 
the model, any size stepper (as long as they are both the same) and and reasonable set of sizes of platform can be created.  I've only looked at doing this with 6 inch and 8 in - higher
shouldn't be a problem for the model, but quickly gets out of the range of my printer bed

 ![image](https://github.com/user-attachments/assets/7151c1f4-726e-4994-b89f-1011a3320ff9)

 So rather that redo everything up to the rotational platform everytime, I'll create a base platform as a component.

 
The center gear could be used to drive a SCARA arm, a radial arm, and the third project I have in mind is a string art project

## First robot design

Off and printing ...

![Screenshot 2025-03-21 111509](https://github.com/user-attachments/assets/59bb6583-f6e7-476c-8c66-85d7a795f2b8)

40 cm SCARA on eight inch lazy susan.  I think I've made about an order of magnutide fewer errors in this process.   I started one print but caught the error when only the first few layers were printed.   


 ## V.1 Update

 It's pretty clear that updating gears is going to be a stumbling block to be fully parameterized.   Since the gear generation tool is a pluging, there is no way to truely parameterize gear generation - I can see that traditionally gears were something you got from a catalog, but in an age of 3d printing it would be nice to have this truely integrated.

 (I can't really complain when I'm using a pretty nifty tool provided to me for free)
 
![Screenshot 2025-03-18 085822](https://github.com/user-attachments/assets/10ecae43-aa26-4886-a2fa-5493d855afce)

Still, it was nice to see the motors update from what shown above (which I'll use one of for the string art project) to the onces I'm currently using on the polar robot.
These are 38 mm long 42 Ncm motors.  I'll complete more of the platform support.  So a couple of things I want to keep in mind.

1. Central gear is going to be different for the different cases 
  * Similar to the rotary gear for the polar robot (but I should switch to the 30 tooth gear used in the Dune Weaver project to be as compatible as possible)
  * A GT2 gear for the SCARA robot
  * Non-existant for the string art case.
2. Use heat inserts as much as possible.  Thecombination of the USB C soldering iron and heat insert makes it incredibly quick to put these in.  This will simplify that I need to print the radial arm in two pieces.  I'll join them with a top plate, secured with M3 screws/heat inserts , since they'll be mostly supported by the carbon fiber rods.   I've found that heated inserts solve problems I didn't know I had ... e.g. to join three things together usually takes one long screw.  With the heated insert you use a short screw,quick to remove and either end can be taken off indpendently (my current design is extremely hard to get the plates holding the arm off, as it screws from underneath and that area is not accessible without taking everything apart).

3. Decide how to handle the different ways the main gear is going to be used.  
  * Polar robot needs the radial arm supported across the center (and obviously needs to move!)
  * SCARA doesn't need anything other than rigid carbon fiber rods attached to the platform, these can be on perimeter.
  * String art likewise can have the frame on the perimeter (I'll use foam board as the backing for a frame printed in 4 parts and secured to the gear this gives me a diameter of roughly 500 mm with the 256 mm x 256 mm print bed of the X1C).
4. My previous robots used a circular base (200 mm) using 4 5/8 threaded steel rods - for tramming, height adjustment.   I'll design the base around this - not that it's a universal standard, but I've already got the holes drilled.

5. Spend some time to model items that need to fit on the robot ... they can be used as cutting tools later.

6. The bottom plate needs to serve as adapter between original mounting plate and whatever is used in the current design.  

Including the base, Current version is shown at the top - the eight inch version will fit on a 256 x 256 build plate (barely).     The rotary sensor is common to both. In the base I've added the 15 tooth gear (allows the slot on the radial arm to be narrower).

## Using Base Platform

I still need to do a few tweeks, but I'm going to do an experiment to create a SCARA robot based on a 6 in lazy suzan, a 24 tooth rotary gear and a 240 tooth main gear. 

First create new top level component (I'm not sure what an assembly is) and copy and paste the base platform  This should create a new independant copy of the parameters.
Create a new component for e.g. the main gear.


The main gear will need something to mount the arm to (i.e.) a guide attached from underneath, posts for sleeve bearings, a slot for idle sleeve bearing to adjust, holes for optical.  I don't think it needs anything else

1. Hole for outer Arm ... OD of bearins used and heat inert holes for guild
2. optical pointer > lazy susan mid + 13 additonal holes for adjustments
3. 
4. bearing sleeve posts
5. Mounting holes to lazy susan

There's one issue that I still need to deal with ... the slot for the idle adjustment was directly above the lazy susan ... I'll just need to fit something holding a sleave bearing to take up the slack, so it won't be adjustable.  Everything else seems good.  I need to do the outer arm, a guide/mounting for the arm and the cutouts for the gt2 gear.   I maded the post for the idle bearing sleeve a little short ...  I may neet to print an extension and then the bearing.  It should be as tall as the gt2 gear, not as tall as the main gear






## History
One of the reasons I wanted to do this one is that I built the robot from (Matt G )[https://alwaystinkering.com/category/sand-table/].   At the time, I 
lacked the 3d modeling skills and the 3d printing skills to do a satisfying job, so I've been meaning revist this at come up with an improved design.   There were a couple of 
issues I wanted to overcome.   The arm had too much play in and tended to drop.  It was also difficult to get everything adjusted correctly for the belts.   I'm intending to address these issues with the design below:

The inner arm is made of up two 5 mm carbon fiber rods (about $9 for a pack of 5 on [Amazon](https://www.amazon.com/MECCANIXITY-Carbon-Fiber-300mm-Quadcopter/dp/B0CTTBSBNN/ref=sr_1_3?crid=23AJ794M031PM&dib=eyJ2IjoiMSJ9.MJMeH6QCTyoHL-ZEP7HK383_D5m7PvBB6umXPj412T82ivodgDwwibtP-o99J82awkXbBVNg6YtYdp0IcY5KSYMnMyv4WD5BTGDfNwqVEZvL3AO2EfehHA3-aUxMxHUbDV3WPDU3brXmNrpYyupg3zEqk20EA3a1WjvzvC-7nav0SX84Rhcg9OvzAG8pIeWm___IUwbI6N8TGsc19B4hIliI1wySKjRjpnN3WFXdPponAJsvwQeWk-QBfgMZVEMf01K42pAfz6SMQs4IGNKMBMFHWvP3rgJJXHq7G8xhCwtAwYNUt0BJbvU_Rj2J92nrpFCMhCWAHMo44yrs9E4OWFgAjeFTK5GGM2dhwCLgc0U.uLn67MjOrLTEv2xcwRVmrgF7J6BWl-cumq0-pPBESwc&dib_tag=se&keywords=5%2Bmm%2Bcarbon%2Bfiber%2Brod&qid=1742215634&s=industrial&sprefix=5%2Bmm%2Bcarbon%2Bfiber%2Brod%2Cindustrial%2C140&sr=1-3&th=1)   I'll add the attachments to the main gear, a end cap to hold the rods together and an adjustable/sliding mechanism to hold the elbow gear and keep the belt snug.  Pretty simple!

The 5 mm carbon fiber rods are incredibly strong.   The trick to getting the sandtable robots working well seems to keep the arm as stiff as possible and provide a cylinder for the magnets that they can freely float up and down (while keeping the cylinder as perpendicular to the table surface as possible.  I think I can do all that with this design.

I'll put a length adjustment for the position of the magnet on the outer arm so that the magnet can be in the exact center after homing (I'll include the rotational homing as part of the 
base platform - it's basically an M3 screw dropped through a hole in the main gear).   The height shown is for the smallest NEMA 17 motor I saw on Amazon.  So starting from the base platform, it's pretty easy to come up with the SCARA design.  Homing the radial/SCARA depends on the design of the robot and needs to be in the derived model (homing of the SCARA is done by gettng the rotational to a known postition and then rotating the outer arm until it sees an optical/hall effect sensor).    A radial design can be done in a very similar manner ... it usual involves getting the rotation to a known spot first.

Rough mockup of design ... inner arm consists of two 8 mm carbon fiber rods.  The outer arm platform can slide along to get the correct length (I want to add a swing arm idler pully to take out the rest of the slack and add a pretty standard outer arm.  The two issues I had with belts on the SCARA design was that it can be difficult to source the exact length you want, so getting rid of an extra 10-40 mm or so would be useful.  Second issue is getting the tension correct to minize backlash, but not bind anything up.  

![Screenshot 2025-03-17 030613](https://github.com/user-attachments/assets/2a320b4a-673c-4ce3-82dd-5c566bb7a17c)

## 
The second design (actually the first I'm planning) is a radial arm Polar robot.    In this case the central gear drives a radial arm.  I wanted to get the base platform in good shape first.   Once that's done the radial design - very similar to the [Dune Weaver project] (https://github.com/tuanchris/dune-weaver) is just a matter of attaching the radial arm.   I would use the Dune Weaver software ... which is pretty great to control the robots.   I think Tuan has come up with the right approach by using off-the-shelf hardware and software for the stepper control (Fluidnc running on the mksdlc32) and then using a Raspberry Pi Zero 2w with code written in python for the user interface.  Both Tuan/Dune Weaver and Fluidnc deserver your (and my!) support.
##
The third design I wanted to explore is a string art machine.   My son wrote a program to transform images to string art, and I've been meaning to implement it.   I wanted to explore 3d printing the "pins".

##
There's a fourth design I've been thinking about.  Both the SCARA and radial arm robot need to make adjustments on the radial/elbow motor - basically they need to turn their gears at the same speed/direction as the main gear is moving in order to stay still.   This is easily done in software - but if you were a victorian steampunk engineer and wanted a purely mechanical solution to this issue, the solution would be to use a differential (one "wheel" gets driven at the speed the main gear is turning, the other acts like there's no coupling between the two.   You then use the "drive shaft" to control the SCARA arm or radial arm).   I've gotten as far as looking into RC model car differentials.   It's a pretty insane, convulated way to do things, but who wouldn't want a robot with a differential?
##
![image](https://github.com/user-attachments/assets/722deff9-4102-434f-8175-697cf08c401c)

### Design One

This is an 8 inch SCARA with the two trees pancake stepper for a 40 cm Ombonad table.  I have no idea if this motor is power.  Configuration of this will be modified Dune Weaver software to work with SCARA Fluidnc.    Unlike the real Ombonad, SCARA requires homing.

The eight inch lazy susan is (currently) $16.99 while the six in is $14.99.   I'll probably only every do eight inch designs.

Parameter Settings:

Gear goes from the 150 tooth to 240 tooth version.  Rotary gear at 24 teeth to keep gear ratio unchanged
MainGearPitchDiameter: 240
RotaryPitchDiameter: 24

LazySusanOuterHole: 189
LazySusanInnerHole: 157
LazySusanOuter: 200
LazySusanInner: 145
LazySusanMid: 172

MotorLength: 24
ShaftLength: 22.6

Produces one warning for Hole3 

<b>4 Reference Failures</b><br/>The face reference is lost and this feature is using cached geometry.<br/>Edit this feature and select new face references.

Height 54.60 (this is distance to main gear + other gears), i.e. 6 mm above main gear

Before I start printing I need:

1. Optical mount attachment points
2. Add additional attachment points on base (e.g. for centering within Ombonad space

My Ombonad table has a inner radius of 396 mm, magnet, arm takes at least an additonal 20 m, so we are down to 380.  I think 350 should be okay.  I'll use 350 which means an arm length of 87. This is a little awkward, as this is right at the edge of the lazy susan midpoint. .   Since I need the optical sensor underneeth, I need a shaft through the main gear for the elbow gear.  There is an exclusion zone from 72.5 to 100 (plus and minus room for the shaft and clearance.   There is also an excusion zone for clearance around the outer stepper .. which is at (MainGearPitchDiameter + RotaryGearPitchDiameter)/2

At 150 teeth/15 teeth we're at 82.5.  Nope
At 180 teeth/18 we're at 99. Maybe - center of shaft is between motor and central platform
At 200 teeth/20 we're at 110. Looking better.
At 220 teeth/22 we're at 121
At 240 teeth/24 we're at 132

So, looking at 200/20, we're in the region between the middle of the lazy susan at 82.5 (distance from origin).  I guess there is no easy way to make a eight lazy susan work ... I guess I am going to do a six inch version.


SCARA_Arm_Length: 87

## Six inch gear

Numbers for this one would be

LazySusanOuterHole: 128
LazySusanInnerHole: 101
LazySusanOuter: 140
LazySusanInner: 88.5
LazySusanMid: 114

This puts the edge of central platform support at 57 mm, and the elbow 30 mm beyond that.  So we want at least 30 mm before the motor shaft.  So we want  (MainGearPitchDiameter + RotaryGearPitchDiameter)/2  to be 30 mm greater than the arm length of 87, so 117.  240/24 geas seem like a good option.  I'll start the design with these numbers.

MainGearPitchDiameter: 240
RotaryPitchDiameter: 24

From shaft to central support 87-57= 30
From shaft to rotary motor shaft 111-87=41. 

This seems workable .. 6 inch lazy susan with 240/24 tooth

Shaft diameter of 15 works with the bearings I have (21 OD, 15 ID)

SCARA_Arm_Length: 87

New components - 40 cm SCARA robot

I'll extrude a platform that can be joined to the 240 tooth gear later

![image](https://github.com/user-attachments/assets/8bca2507-025c-4213-a905-7a51a1a512fd)



So, I need to take care of modelling the following:

* Extrude platform
* Rotary pointer (m3 screw dropped through the gear)
* Outer arm with 15 mm shaft & adjustment for magnet holder, slot
* Magnet holder cylinder m3 insert,  for 20 mm diameter magnet
* Elbow pointer/end cap to fit over shaft and secure with cotter pin
* Holder for bearings to fill space between elbow pointer and main gear
* 2 40 tooth? gt2 gears. One to fit nema motor, and one to fit a starred patter on shaft.   This fits above gear ... hopefully gears can be tight enough around shaft.   Larger bearings and a collar?
*Idler mechanism to take up slack I'll have with 400 mm belt (what I have on hand).  2 fixed and one that can slide along a slot.  Need to check size on skate bearings
* Outer arm

For fun I'll inset the belt into the platform by 4 mm ... I need to temporarilly set main gear thickness to far (effective height of main gear).

Printing base - 2 hours/20 minutes, blue PETG, 87 grams of filament
Centering mechanism for platform? ... attachment points  This can just be pressure fit.

Printing Central support 1 hr/12 minutes, white PETG 30 grams of filament.  The heat inserts are quite large .. may want to make feet of support wider









