# simple-robotics
A resource for hobbiest robotics and other animatronic projects.

This guide will be a mixture of hands on computer, mechanical, electrical engineering and fabrication with a touch of computational neuroscience. A lot of the math will be as simple as possible; being an engineer, I'm not good at maths. My hope is for this to be a Grimoire, or book of spells, I can consult when building a new project or faced with a familiar problem.

## Contents
1. Linkages
2. Micro Controllers
3. Sensors
4. Actuators
5. Servos
6. Motors
7. Simulations
8. BCI 
9. ANN
10. 3D Modeling
11. 3D Printing

## Linkages

Linkages are levers connected at multiple points, commonly 4-points, where three of the bars of the linkage move and one is static. An interesting example of this might be an end effector where two linkages are mirrored to create a kind of manipulator.  

![Screenshot 2024-12-17 203006](https://github.com/user-attachments/assets/71f6323f-ad55-44bf-bcd9-2b8e10e25575)

![Screenshot 2024-12-17 203006 - Copy](https://github.com/user-attachments/assets/fc965577-48de-4fe0-b023-00ccb4a598d1)

![Untitled](https://github.com/user-attachments/assets/8570c44a-f5a7-4cae-90cc-804914a9730a)

The mathematics can be simple. To move (x,y) to (x,y).2 simply move the two inner bars of the  linkage some degrees. The linkage is configured in a 1:1 ratio, so the degrees moved will be the same for each bar. Convenient! 

![image](https://github.com/user-attachments/assets/561b82a7-af5f-4ea8-8510-086aef6b6dde)

If we wanted to move some distance to a new X,Y but don't know what angle to use, it's simple.

![image](https://github.com/user-attachments/assets/5b37d756-4d3a-4d05-88d6-95740430e468)






## Sources
+ [Mini servo gripper](https://www.thingiverse.com/thing:2415)
+ [Gear Types, Design Basics, Applications and More - Basics of Gears](https://youtu.be/ZhDO16FDmxA?si=TrhTgkIMsFZLdley)
+ [Levers and 4 Bar Linkages](https://youtu.be/0MYF8YCf2jQ?si=RR6by026zaeGyJ01)
+ [Wavelets: a mathematical microscope](https://www.youtube.com/watch?v=jnxqHcObNK4&ab_channel=ArtemKirsanov)
+ [Easy inverse kinematics for robot arms](https://youtu.be/Q-UeYEpwXXU?si=-LuqWcVNqyQoCUL-)
+ [5.1 Inverse Kinematics](https://www.youtube.com/watch?v=RH3iAmMsolo&ab_channel=Woolfrey)
