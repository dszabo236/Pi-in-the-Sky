Project Completed on June 6th, 2018. Original [wiki webpage](http://wiki.chssigma.com/index.php?title=Dani_and_Cole%27s_Pi_in_the_Sky).  
* [Table of Contents](#table-of-contents)
* [Plan #1 - Hot Air Balloon](#Plan-#1---Hot-Air-Balloon)

## Initial Ideas
- Hot Air Balloon
- Water Rocket
- Quad-copter
- Pressurized Air Rocket
- Catapult
- Potato Cannon
# Plan #1 - Hot Air Balloon
We originally chose to design a hot air balloon. We felt like the main challenge would be with the design of the balloon and figuring out what systems we wanted on board.
Important things to note are:
- How to stop the balloon from rising
- Release the Raspberry Pi
- Get enough lift
- Hold the materials under the balloon
## Materials
- Nichrome
- Light, Large, Bag
- Styrofoam
- Pi
- Altimeter
- Gyroscope
- Relay (for current)
- Heating device (heat gun, hair dryer, blow torch)
## Pseudo Code
// initialize Accelerometer

// initialize Altimeter

// start recording

// loop for a minute

// write to .txt file

// relay after two minutes
### [Plan Picture](media/CDplan.png)
# Final Plan
## Materials
- PVC pipe
- Spark plug
- Trigger
- 5 feet of 1.5" ABS (DWV) pipe
- 2 feet of 3" ABS pipe
- A 3" to 1.5" reducer
- A 3" threaded adapter
- A 3" end cap
- A BBQ ignitor (+1 Screw)
- ABS cement
- Cheap aerosol hairspray
## Description
A potato cannon is the most basic form of combustion cannon. Easy and cheap, it has been adapted by DIY'ers many times. In its most fundamental design, a potato is shoved down a pipe that is connected to a compartment where a flammable gas is sprayed and then ignited. The combustion reaction pushes the potato out of the pipe at a high velocity. There is obviously some worry about the force of the projectile damaging the Pi, but part of the project will be figuring out how to effectively protect it. The Cannon itself will be made of PVC pipe.
## Plan Drawing
[Plan Drawing](media/PotatoDC.png)
## Photos of Finished Product
- [Pi-Sensor Circuit](media/CDFritz.png)
- [Potato Canon Final Build](media/Dani_Cannon.jpg)
- [Pi Capsule Final Build](media/Capsule_CD.jpg)
## Code
Our code came from the simpletest.py file inside a Github repository for the LSM303 sensor:
https://github.com/adafruit/Adafruit_Python_LSM303
This code to read the sensor is coupled with two lines of code that output the sensor data to a .txt file. The program runs on startup, so when connected to a battery, it will output two minutes worth of data.
[Code](code/code.py)
## Solidworks and Project Design
The most challenging part of the project was figuring out how to enclose the sensors and Pi in order to record data. The pictures below show our final design, which was a cylindrical capsule outfitted to the exact radius of the barrel of the cannon. The best way to enclose everything compactly and securely is with a screw thread, which was perfect as we could make use of the Solidworks Thread tool. The first test thread we printed was very fine and always got stuck when screwed in. In the second iteration, we printed slightly larger threads (still over 5 per inch) and encountered the same problem. Our final iteration we decided to make the largest threads possible and settled on "1.500-6" size. This worked out perfectly and the thread fit tightly and screwed in without inhibition. See the design below.
- [Final Thread](media/Thread1.png)
- [Base Design](media/Basecd.png)
## Data Analysis
Our code outputted 2 mins, or 250 lines, worth of data. Because of the lack of rifling in the barrel or the capsule, the projectile did not fly straight and oscillated and turned violently. This motion caused the acceleration data in the X, Y, and Z directions to be all over the place. The X data ranged between -7m/s/s to 6m/s/s; Y between -3 and 4m/s/s; Z between -16 and 8 m/s/s. We fulfilled the project by putting a Pi in the Sky and determining accel data. The execution and range of motion allowed a sub-optimal analysis of actual acceleration.
In addition to printing the raw data, you can see in our lines of code that we added a line to analyze the X, Y, and Z accelerations to come up with a total acceleration. As expected, the half second delay missed the actual launch, so the mid-air acceleration should have been relatively constant even while spinning and messing up the data, with adjustments for drag and such of course. Here is a sample of our .txt output for the data while being shot. note the jump from a constant mid-air, to low accel at impact:
'''python
Accel X=8.09, Accel Y=3.49, Accel Z=2.44  Total Accel= 9.14
Accel X=5.84, Accel Y=4.02, Accel Z=3.03  Total Accel=7.71
Accel X=1.89, Accel Y=6.74, Accel Z=5.80  Total Accel=9.11
Accel X=5.98, Accel Y=6.39, Accel Z=2.30  Total Accel=9.07
Accel X=6.96, Accel Y=5.17, Accel Z=4.70  Total Accel=9.87
Accel X=3.91, Accel Y=0.13, Accel Z=9.44  Total Accel=10.22
Accel X=1.55, Accel Y=2.63, Accel Z=9.60  Total Accel=10.13
Accel X=-1.84, Accel Y=2.90, Accel Z=8.98  Total Accel=9.61
Accel X=-1.19, Accel Y=2.32, Accel Z=3.24  Total Accel=4.16
'''
## Challenges
- Figuring out an original project that would fit the task; 
  - **Solution: tried hot air and then went big with guaranteed flight.**
- Designing capsule threads; 
  - **Solution: Larger Threads**
- Printing capsule correctly; 
  - **Solution: Making interior thinner.**
- Launching capsule without falling into chamber; 
  - **Solution: Launch potato behind capsule.**
- Combustion of hair spray multiple times in a row; 
  - **Solution: Dry chamber after each launch.**
# Conclusion
From this project we got to learn a variety of skills by doing. Our initial idea of creating a hot air balloon was a slightly complex way of putting a Pi in the sky. We attempted to use a heat gun to fill a large trash bag with hot air and lift it up. This worked, but was not able to support the weight of a pi. In order to create enough lift for a pi we would have had to use materials that were not at our disposal, and even with that strategy there would have been no guarantee that we could bring the pi back down, as the nichrome wire failed to work in a proper manner at cutting down the pi. Therefore, we switched to a potato canon design, which would not only allow us to have data that provided us with more intriguing data. Building the potato cannon itself was relatively easy, cementing PVC pipe and such. We utilized our advanced Solidworks skills to craft the capsule and learned a lot about the Thread feature as a result. The Python code write-up taught us about Python syntax, utilizing Github, and doing data analysis. Finding a combustible fluid was not difficult, and it worked well. we also discovered that over-saturating the barrel led to combustion issues, and therefore attempted to keep the barrel as dry as possible. Overall, the project was multi-faceted, and provided us with thorough understanding of different aspects of solid works, raspberry pi's, and accelerometers.
