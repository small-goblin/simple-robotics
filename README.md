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

How about a chain arms that needs to reach some point (x,y)? 

![image](https://github.com/user-attachments/assets/fead1917-ac5b-40c3-bf0f-dc92c5530992)

We can express this chain arm first in 2d. The segments of the arm move in a circular motion. The segments themselves form the radius of a circule, with the joint being at the center. If the previous segment moves, this displaces the location of next segment. 

![image](https://github.com/user-attachments/assets/0ad5f3c8-1cdc-4bb8-86c4-1e17e3d73a99)

![image](https://github.com/user-attachments/assets/f1c57a79-f68d-4517-8098-6859209c4414)

The arm itself will only ever be able to reach points that are under each segments combined length. Provided there are no restrictions on the angle that the segments can bend. 

![image](https://github.com/user-attachments/assets/ee28983a-3374-4cfb-a598-afc05dcb9c9c)

If we'd like to align the arm to some point (x,y) it's possible by defining each segment as a circlular equation and then solving where they intersect. Where the circles intersect (often more than one place) is where the joint (h,k) can be moved to angle the arm properly to reach (x,Y)

![image](https://github.com/user-attachments/assets/383225ab-e5f0-42ef-8619-c380ebecfe26)

Once we know the complete cordinates, finding the angles is manner of solving some trig functions. 

![image](https://github.com/user-attachments/assets/eca88777-612d-4a4e-ab53-8a280a8a3641)

We can add a third dimension. The base (shoulder) has 2 degrees of freedom while the elbow has 1 degree of freedom. We can slice the arm into two places. Once which the base rotates along, and another which the elbow rotates along. The because 2, 2d operations.

![image](https://github.com/user-attachments/assets/ab961bae-4b86-4d57-98ad-88d477b3055f)

![image](https://github.com/user-attachments/assets/253ddeb9-f257-4d0d-a86b-ec59e4849dd0)

First the position of the elbow in 2d space. 


![image](https://github.com/user-attachments/assets/4e90ee4d-287a-4f9c-8c7d-8d388248f62f)

![image](https://github.com/user-attachments/assets/8a781126-5877-4449-9512-b54b38dc5e69)

Then the rotation of the base to align the plane.

![image](https://github.com/user-attachments/assets/c34706ed-6128-4f25-bd8e-c6be04ed1f0f)

![image](https://github.com/user-attachments/assets/842a21de-2347-4665-9fa6-19d5094b026e)

### Sources
+ [Mini servo gripper](https://www.thingiverse.com/thing:2415)
+ [Gear Types, Design Basics, Applications and More - Basics of Gears](https://youtu.be/ZhDO16FDmxA?si=TrhTgkIMsFZLdley)
+ [Levers and 4 Bar Linkages](https://youtu.be/0MYF8YCf2jQ?si=RR6by026zaeGyJ01)
+ [Wavelets: a mathematical microscope](https://www.youtube.com/watch?v=jnxqHcObNK4&ab_channel=ArtemKirsanov)
+ [Easy inverse kinematics for robot arms](https://youtu.be/Q-UeYEpwXXU?si=-LuqWcVNqyQoCUL-)
+ [5.1 Inverse Kinematics](https://www.youtube.com/watch?v=RH3iAmMsolo&ab_channel=Woolfrey)
+ [Mechanical Design](https://www.youtube.com/watch?v=CZuBeBztzSY&ab_channel=InfinityMFG)


## Micro Controllers

Typically a micro controller is a system on a chip that contains a real time operating system or some kind of bootloader that launches user defined programs. There is usually a number of general purpose IO pins that can do both digital and analog signals. 

Commonly you might output a digital signal like pwm to drive a servo motor or input an analog signal from a sensor. 

The RP2040 is a low cost, low powered, controller. It has a lack of peripherals which makes it undesirable for many IOT projects, but more than capable for hobbyst robotics projects. 

Debugging should be done through the SWD interface using a pico probe or some similar probe board. The offical documentation suggest using their version of openOCD to debug and flash the pico2040 as the standard openocd branch does not suggest all 2040 chips.

### Sources

+ [RP2040](https://en.wikipedia.org/wiki/RP2040)
+ [RP2040 vs ESP32](https://www.embedic.com/technology/details/rp2040-vs-esp32--which-microcontroller-is-best-for-your-project-2023-)
+ [RP2040 datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)
+ [PID Controller](https://en.wikipedia.org/wiki/Proportional%E2%80%93integral%E2%80%93derivative_controller)

## Servos

Servos are geared motors which can be turned to different angle position based off of PWM. A pulse is sent to the server and the width of this pulse determines the position that is being requested. 

A servo will try to maintain this position regardless of outside force so long as it recieves this pwm. 

Servos typically have a neutral position of about 90 degrees. 

Cheap servos have to be calibrated via software to make up for their oddities. The actual limitis and range of a servo should be checked before fully integrating it into a project. 

### Sources 

+ [Servo Control](https://en.wikipedia.org/wiki/Servo_control)
+ [Servo](https://en.wikipedia.org/wiki/Servo_(radio_control))

## Motors

Driving the direction of a motor requires an H-Bridge. Because the direction of a motor is determined by polarity of voltage, to move forwards or backwards, requires the switching of polarity at varying current. The H-Bridge is a simple way to change polarity of voltage quicky. Interanlly the h bridge is 4 switches that can influence the voltage of a circuit. 

### Sources
+ [H-Bridge](https://en.wikipedia.org/wiki/H-bridge)
+ [H-Bridge](https://www.build-electronic-circuits.com/h-bridge/)
+ [sn754410](https://www.ti.com/lit/ds/symlink/sn754410.pdf)


## 3D Printing

FDM (Fused deposition modeling) is where you drive hot pastic through a nozzle in layers one after another to create a 3D print.

In regards to robotics, tolerance of parts is very important. These settings impact tolerances:

- Horizontal Expansion
- Over Extruding
- Temperature
- Print Speed

### Horizontal Expansion
Negative values remove material, positive values add material. This can compensate for parts that don't fit together nicely. Holes in prints will get larger, but the overall print will be smaller, for negative values. The opposite is also true. 

![image](https://github.com/user-attachments/assets/ed09f260-eddc-464d-929f-c37a3ed14e9d)


### Over Extruding
It is best to first correct any over or under extrusion that may be happening as that can also impact the tolerance of a part.

### Temperature
1. Configure the printer to correctly print at the filament brand stated temperature as it can be different between vendors.
2. Control the ambient temperature of the room the the printer operates in
3. Print at the lowest settings required for the material if possible.

### Print Speed
Lowering the print speed ultimately decreases errors that the printer may make due to jerk. Ultimately it impacts the shape of the final print. 

### Sources
+ [fdm printing](https://all3dp.com/2/fused-deposition-modeling-fdm-3d-printing-simply-explained/)
+ [Horizontal Expansion](https://the3dprinterbee.com/cura-horizontal-expansion/#:~:text=The%20horizontal%20expansion%20is%20specified%20in%20millimeters%20and,object%2C%20only%20the%20first%20layer%20or%20for%20holes.)
+ [How To Calibrate Your 3D Printers Extruder Esteps ](https://youtu.be/6PL_rSPZ3M8?si=Yx9DdClGU_MXlPtU)


