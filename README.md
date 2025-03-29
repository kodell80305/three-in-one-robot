# three-in-one-robot

![image](https://github.com/user-attachments/assets/a1185e0c-d6f3-4ce7-bffb-e886d29a4895)

The goal in this project is to develop a fully parameterized rotational platform that can be used for at least a few projects that I would like to do:

 1. The first one is a 40 cm SCARA robot.   My original sand table was done using a SCARA robot I found from the "Always Tinkering" blog by Matt G.   This was based on work by Rob Dobson.  (I'll do the links later).   I actually built two coffee table size versions (one for me and one for my son).    I was never completely happy with a few aspects - mostly due to my lack of experience in 3d printing, 3d modeling.   It was difficult (for me!) to get the arm lengths correct and to get the belt tension correct.   I ported the software to the dlc32 board and added support for addressable leds and a serial smart screen.    I wanted a smaller SCARA robot to use to get the Dune Weaver software running and abandon my previous efforts (because Tuan's software and architecture is much better than what I have)

 2. The second will be a Dune Weaver - style radial arm that I'll use to convert my table to.  The design here won't be too original - it's very similar to the Dune Weaver Pro - I'll need to split the arm in two, so it will be supported by 5 mm carbon fiber rods.  I'll have support for a rotational optical switch and a hall effect central switch.  I have not tried the sensorless homing used by the Dune Weaver folks.

 3. The third drops the central motor entirely and just uses the rotational portion ... it would be for a image-to-string arg project.

(I actually want to do a fourth, which would be a full size SCARA robot and I have a design in mind for a Ombonad-size SCARA robot with a differential that I really want to do ...)

So, what's the point of all this?

In programming terms, what I want to do is design a "base class" that you could use to instantiate different versions of what is essentially the same thing.   In real, practial terms what I've found is that using parameters on this project has been the single biggest improvement to my Fusion 360 skills and organization.   It's really just a list of all the variables that go into your design and their values.   Using parameters means:

1. I've thought through what the important constraints/numbers are & am consistent across the design.
2. I tend to do many more, simpler sketches - before I was trying to cram everything into a single sketch
3. I don't use projection geometry

This is a work in progress (as of March 2025), so I'll be updating this fairly   I'm mostly doing this at least partially as an exercise to improve my 3d modeling skills. 

Status:

The Ombonad robot is complete - but I just realized that once again I was making life way too hard so I have one change I want to make.  The plan is to get this working, go back and tweak the base platform to fix some weaknesses and then start on what is essentially a copy of the Dune Weaver Pro to fit my table.






