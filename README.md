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

The length of the links can be varied to influence the angles. Commonly, this seems to be done in ratios much like gears.

![image](https://github.com/user-attachments/assets/26e2d486-ed61-4540-8d3b-001e17789239)

This mechanism seems to be called a "rocker" because it rocks back and forth.

How about hain arms that needs to reach some point (x,y)? 

![image](https://github.com/user-attachments/assets/fead1917-ac5b-40c3-bf0f-dc92c5530992)

![image](https://github.com/user-attachments/assets/0ad5f3c8-1cdc-4bb8-86c4-1e17e3d73a99)

![image](https://github.com/user-attachments/assets/f1c57a79-f68d-4517-8098-6859209c4414)

![image](https://github.com/user-attachments/assets/ee28983a-3374-4cfb-a598-afc05dcb9c9c)

![image](https://github.com/user-attachments/assets/383225ab-e5f0-42ef-8619-c380ebecfe26)

![image](https://github.com/user-attachments/assets/1e477b67-06e8-4012-82b2-7772cadbf009)

![image](https://github.com/user-attachments/assets/eca88777-612d-4a4e-ab53-8a280a8a3641)

![image](https://github.com/user-attachments/assets/4e90ee4d-287a-4f9c-8c7d-8d388248f62f)

![image](https://github.com/user-attachments/assets/ab961bae-4b86-4d57-98ad-88d477b3055f)

![image](https://github.com/user-attachments/assets/253ddeb9-f257-4d0d-a86b-ec59e4849dd0)

![image](https://github.com/user-attachments/assets/8a781126-5877-4449-9512-b54b38dc5e69)

![image](https://github.com/user-attachments/assets/c34706ed-6128-4f25-bd8e-c6be04ed1f0f)

![image](https://github.com/user-attachments/assets/842a21de-2347-4665-9fa6-19d5094b026e)





## Sources
+ [Mini servo gripper](https://www.thingiverse.com/thing:2415)
+ [Gear Types, Design Basics, Applications and More - Basics of Gears](https://youtu.be/ZhDO16FDmxA?si=TrhTgkIMsFZLdley)
+ [Levers and 4 Bar Linkages](https://youtu.be/0MYF8YCf2jQ?si=RR6by026zaeGyJ01)
+ [Wavelets: a mathematical microscope](https://www.youtube.com/watch?v=jnxqHcObNK4&ab_channel=ArtemKirsanov)
+ [Easy inverse kinematics for robot arms](https://youtu.be/Q-UeYEpwXXU?si=-LuqWcVNqyQoCUL-)
+ [5.1 Inverse Kinematics](https://www.youtube.com/watch?v=RH3iAmMsolo&ab_channel=Woolfrey)
+ [Mechanical Design](https://www.youtube.com/watch?v=CZuBeBztzSY&ab_channel=InfinityMFG)
