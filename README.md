# three-in-one-robot

![image](https://github.com/user-attachments/assets/a1185e0c-d6f3-4ce7-bffb-e886d29a4895)

The goal in this project is to develop a fully parameterized rotational platform that can be used for a few projects I'm doing.

 1. The first one is a 40 cm SCARA robot.   My original sand table was done using a SCARA robot I found from the "Always Tinkering" blog by Matt G.   This was based on work by Rob Dobson.  (I'll do the links later).   I actually built two coffee table size versions (one for me and one for my son).    I was never completely happy with a few aspects - mostly due to my lack of experience in 3d printing, 3d modeling.   It was difficult (for me!) to get the arm lengths correct and to get the belt tension correct.   I ported the software to the dlc32 board and added support for addressable leds and a serial smart screen.    I wanted a smaller SCARA robot to use to get the Dune Weaver software running and abandon my previous efforts (because Tuan's software and architecture is much better than what I have)

 2. The second will be a Dune Weaver - style radial arm convert my table to.  The design here won't be too origina it's very similar to the Dune Weaver Pro - I'll need to split the arm in two, so it will be supported by 5 mm carbon fiber rods.   I've already designed and build one of these, so this will be pretty quick.   I'll have support for a rotational optical switch and a hall effect central switch.  I have not tried the sensorless homing used by the Dune Weaver folks, ut that is an option.

 3. The third drops the central motor entirely and just uses the rotational portion ... it would be for a image-to-string project to implement an algorithm my son wrote.

(I actually want to do a fourth, which would be a full size SCARA robot and I have a design in mind for a Ombonad-size SCARA robot with a differential that I really want to do ...)

So, what's the point of all this?

In programming terms, what I want to do is design a "base class" that you could use to create derived classes for a particular purpose.   All of these will use a lazy susan (of various sizes), a support for the lazy susan, support for optical sensing, support for different size of stepping motors (but all NEMA 17) and implementations of 15, 24, 150, 180, 240 tooth gears, GT2 gears, etc.   The idea is that you can chose whatever makes sense for your application ... you just need to design whatever needs to attach to the outer lazy susan.   I'll document the 40 cm SCARA version and hopefully this will make sense.

The 40 cm SCARA turned out to be an interesting choice for a first test ... due to the constraints of where the elbow needed to be I ended up with a six inch lazy susan, but a 240 tooth/240 mm pitch diameter outer gear.   The elbow sits between the support for the lazy susan (which is the inner ring) and the rotational motor.

In real, practcial terms what I've found is that using parameters on this project has been the single biggest improvement to my Fusion 360 skills and organization.   It's really just a list of all the variables that go into your design and their values.   Using parameters means:

1. I've thought through what the important constraints/numbers are & am consistent across the design.
2. I tend to do many more, simpler sketches - before I was trying to cram everything into a single sketch
3. I don't use projection geometry
4. I'm consistent across the sketches
5. My error rate is a fraction of what is was before.

This is a work in progress (as of March 2025), so I'll be updating this fairly   I'm mostly doing this at least partially as an exercise to improve my 3d modeling skills. 

Status:

The Ombonad robot is complete - but I just realized that once again I was making life way too hard so I have one change I want to make.  The plan is to get this working, go back and tweak the base platform to fix some weaknesses and then start on what is essentially a copy of the Dune Weaver Pro to fit my table.

Critical constraints/vertical

Rotary gear needs to mesh with the main gear.

Height of rotary = Top of main gear - clearance (it should be at least 1 mm below top)
                 = base thickness + Motor length

*** So MainTop = BaseHeight + NemaML + Clearance 

Second would be that the Lazy Susan support + Lazy SusanHeight + MainGearHeight = MainTop
So MainTop = LZSupportHeight + LZHeight + MainGearHeight,

***Computed: LZSupportHeight = BaseHeight + NemaML + Clearance - LZHeight - MainGearHeight

Lazy Susan support starts at BaseHeight & is (BaseHeight + NemaML + Clearance - LZHeight - MainGearHeight)

where BaseHeight just for additional support, I'm using 3 mm here.
NEMA motor length depends on motors chosen, I'm using some pancake steppers for this.
Clearance is 1 mm
LZ Height is the purchased Lazy Susan - 8.5 mm
MainGear Height is chosen to be 8 mm (it won't effect the overall robot height - actually the thicker the main gear the lower the robot in this particular case)

1. Change bearing size to 21x15
2. Get rid of m3 heat inserts - use generic m3hole size of 2.7 mm for "self tapping" holes

3. Arm guide = Top is at MainTop - MainThickness, bottom at MainTop - MainThickness - ArmGuideHeight


Arm redesign

Shaft is inner diameter of bearing
Need a circle size of gt2 40 tooth pully

Assume bottom of rotary is zero:

ML - RotaryHeight = MainBottomHeight

Constraint 1: Rotary Motor should mesh with main gear ... bottom of rotary should line up with bottom of main gear (main gear is taller, so provides clearance)

MainBottom = ML - RotaryHeight
MainBottom = SupportHeight + LazySusanHeight

ML - depends on what motor is picked
LazySusanHeight - depends on manufacturer of lazy susan

So SupportHeight = ML - RotaryHeight - LazySusanHeight

Radial motor:

GTHeight should include shim for clearance, so call in 10 mm
End of motor - GT2 Height = MainTopEffective  <- same level as gear driving outer arm ... we don't need clearance, but we do on outer arm 








