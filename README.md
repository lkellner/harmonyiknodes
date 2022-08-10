# harmonyIknodes


This plugin is currently only available for Windows in Toon Boom Harmony 21.0 and won’t function in Harmony 21.1.1. Updates to come soon

As this is a beta version it is not recommended for use in animation productions yet, please report and potential bugs at the issues page.

<b>Installing the plugin</b>


Download the files, unzip them and copy the IKHub and IKSelector folders into Toon Boom Harmony's plugin folder. Administrator permission will be required.
e.g.

![image](https://user-images.githubusercontent.com/11638171/183882052-99fc4d62-2499-4222-9668-a8cff886f02b.png)
![image](https://user-images.githubusercontent.com/11638171/183881996-24946799-d9d4-4c70-9863-b38c59935b8d.png)



<b>Setting up the scene</b>


The IK Hub and the IK Selector nodes can be added by going to Node View -> Insert -> (Effects ->) Plugins. 

The IK Hub node can have up to six possible inputs which are all required to be pegs.
Out of these, four (Upper Limb inport, Lower limb inport, Extremity inport and Effector inport) are madatory while the other two (Toe inport and Heel inport) are optional.

Each of of the inports has its own specific functionality which makes it necessary to connect the pegs in the following order:

![image](https://user-images.githubusercontent.com/11638171/183883472-ed6ec244-014f-4e37-95d9-16c1a559e5f0.png)

These pegs should also be parented to each other following the set-up in the picture.


The IK Hub node’s outport offers four different transformations to choose from (Upper Limb, Lower Limb, Extremity and Toe). To be able to select the appropriate one an IK Selector node must be inserted between the IK Hub and the different parts of the rigs that are meant to be controlled by the IK set-up (e.g Upper Leg, Lower Leg, Foot).

In the IK Selectors' drop down menu, choose the transformation that corresponds to the out connection of each node. 

![image](https://user-images.githubusercontent.com/11638171/183881237-d80258bc-c97e-45c8-9cb0-fa23deacfddb.png)

The limbs will now follow the position of the Effector peg.




<b>IK Hub attributes </b>


Active: Switches between FK (0) and IK (1) mode.

Clockwise: Changes the direction of the calculated IK limb angles.

Foot Roll: This will only function when a heel peg and/or toe peg are connected. It will rotate the Foot(Extremity) around these pegs while recalculating the limb               rotations with the goal to help with keeping the feet planted on the ground.

Stretch Factor: Allows for the limbs to stretch until reaching the Effector peg (100) or keep the limb length constant (0).
          Use the values between 0 and 100 to interpolate between the two when necessary

Follow Limb Rotation: Setting this to 0 keeps the Extremity’s rotation in space consistent, ignoring any rotation of the parent limbs. 100 follows the parents'                   rotation completely.
          Use the values between 0 and 100 to interpolate between the two when necessary
         
         
<b>Best practices </b>

While the set-up usually doesn’t break when scaling it, is recommended to only use scaling for flipping or uniform scaling as otherwise the rig might not behave as desired.

To ensure the rig will stretch as intended, it is best to line up the Upper Limb, Lower Limb and Extremity pegs in a straight line. 
 
 
 
<b>Known issues</b>


Setting any of the IK pegs' or their parents' (direct and indirect) scaleto 0 might not result in the desired effect.

 
 
<b>Credits</b>


This plugin was created by Laura Kellner. All rights reserved.
 
 
 
<b>Acknowledgements</b>


https://www.motionscript.com/design-guide/ik.html whose After Effects tutorial on IK helped me understand the foundation necessary to write this plugin.
https://rxlaboratory.org/ who with their After Effects plugin DUIK inspired me to create something similar for Toon Boom Harmony.
