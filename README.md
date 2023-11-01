WRO-Kazakhstan<br>
This is the inctruction for WRO 2023-Kazakhstan, team "Qyzylorda" from Qyzylorda, Kazakhstan. the program written for lego mindstorms ev3.

Team name: Qyzylorda<br>
Country: Kazakhstan<br>
Team participants:
  <li>Sadu Yernur</li>
  <li>Adilbek Nurdaulet.</li>
<br>
Coach: Akhmetov Serik<br><br>
Git repository include files with program both for qualification and final rounds.<br><br>
<b>Description of documentation files and folders:</b>
<li>models - constructions of robot</li>
<li>resourses - some files are just codes</li>
<li>schemes - schemes of device in pdf files</li>
<li>t-photo - photos of team</li>
<li>v-photos - photos of robot</li>
<li>videos - links to youtube video and same video files</li>
<li>readme - full information about the team and a full description of the vehicle (robot)</li><br><br>

<b>Briefly about the vehicle (robot)</b><br><br>
Robot consists of 3 motors and 4 sensors, including 1 camera. They are 3 middle lego motors, one for steering and others for driving. One of the sensors is a gyroscope, it helps to straighten the robot to correct course after turning. Second one is a ultrasonic sensor to see whether robot must stop or should continue to drive. also, it see obstacles we should avoid. main robot's processing center is lego ev3 brick. it is connected to sensors and motors through lego cabels.We use 2 medium motors to drive the vehicle which rotate one axis to add extra power.<br>

![imgonline-com-ua-Resize-0iMIDs2Cbz](https://github.com/tellwouldrun/WRO-2023-Qyzylorda-FE/assets/142982463/97c595a1-8303-4ace-996d-4a38ba5323dd)


<b>Algorithm of operation of the vehicle program</b>
<li>Data refresh(Zeroing the gyroscopic sensor value)</li>
<li>Detection of lines to determine the direction of the robot</li>
<li>Detection of obstacles for the corresponding robot movements (if the obstacle is red, then turn right, and if green, then turn left)</li>
<li>Lap count</li>
<li>Changing the direction of movement of vehicles depending on the last obstacle</li>
<li>Finish</li><br>
<b>Ultrasonic Sensor</b>

This is a digital sensor, which measures the distance to an object.

In addition to the ultrasound receiver, which is a kind of a special microphone, this sensor also has an ultrasound transmitter. The transmitter sends an ultrasonic wave that bounces off the obstacle and reflects back to the robot. This returning wave is picked up by the receiver, which is the actual sensor. The robot calculates the distance to an obstacle by measuring the time elapsed from the moment the ultrasonic wave was emitted until the echo of this wave, which has reflected back from an object, came back.

The ultrasonic sensor enables three different modes. It enables making distance measurement up to 250 cm (100 Inches) with an accuracy of 1 cm (0.393 Inches) in either centimeters or inches. It also enables a listen mode where the ultrasonic sensor is measuring whether other ultrasonic sensor are active within its surroundings. This sensor is implemented as a digital sensor, meaning the sensor includes a small 8-bit microcontroller which communicates with the EV3 P-brick using UART communication on pin 5 and 6. The microcontroller handles all sensor measurements and data analysis which is then communicated back to the EV3 P-brick. The ultrasonic sensor sends back new distance measurement whenever a new distance is detected. If the distance is 250 cm (100 Inches) the duration between new sensor values will approximately be every 15 mS. With a smaller distance the ultrasonic sensor will be able to return measurement faster. The ultrasonic sensor measure the distance to an object by sending out an ultrasonic sound signal, 12 sound burst at 40 KHz. The receive transducer is most sensitive at 40 KHz and has a beam angle of approximately 90 degree.<br><br>
<img src="https://m.media-amazon.com/images/I/51wnwlOTfCL._AC_UF894,1000_QL80_.jpg" width="300"/>

<b>Gyroscope</b>

Gyroscope is a digital sensor, which detects movement and changes in the movement of the robot. When the robot moves, this sensor will present this as the change in the rotation speed in degrees per second (deg/s). The maximum rate is 440 deg/s.

The microcontroller handles all sensor measurements and data analysis which is then communicated back to the EV3 P-brick. The gyro sensor is able to return new sensor values 1000 times a second if the sensor reading changes fast enough. The sensor is programmed to automatically return a new sensor value whenever the value changes or if the EV3 P-brick requests a latest sensor value.

Based on this data, the user can determine whether the robot is turning, and also to program these turns (with the accuracy of +/- 3 degrees for a 90-degree turn). We used gyroscope to hold correct direction of movement and make proper turnings. Also, our PID regulator is based on data from the gyroscope. Although having great applications, the gyrocope needs time between 2-5 seconds at the beginning to get rid of drift; it means random unwanted errors.<br><br>
<img src="https://ae01.alicdn.com/kf/S4b4967d9fce44c16965c3bc0974fe9554.jpg" width="250"/>

<b>Color sensor</b><br>

Color sensor is essential for our robot in determining direction of the movement. Because it defines reflected light intensity and, thus, color of the line before turnings. It can calculate RGB components of colors. After, native block in lego determines exact color of lines. it helps to recognize where turn is. if first seen line is orange, then robot turns right and vice verse. The microcontroller handles all sensor measurements and data analysis which is then communicated back to the EV3 P-brick. The color sensor is able to return new sensor values 1000 times a second if read surface changes fast enough. The sensor is programmed to automatically return a new sensor value whenever the value changes or if the EV3 P-brick requests a latest sensor value. When the color sensor are connected to the EV3 P-brick it automatically starts by identifying itself to the EV3 P-brick as a color sensor and it communicates the modes and value ranges it supports before it switches to the default mode which is light sensor mode.<br><br>
<img src="https://ae01.alicdn.com/kf/H479026f5da574e38ac828a8d4bd54138Y/Serie-de-funciones-de-potencia-de-alta-tecnolog-a-para-45544-EV3-Sensor-de-Color-Sensor.jpg" width="250"/>

<b>Camera Pixy 2.1</b><br><br> 
Pixy camera is used to determine the color and location of the obstacles that are located in the path of the vehicle. With the help of this camera, the vehicle goes around objects and completes tasks.<br><br>
<img src="https://cdn1.botland.de/img/art/inne/12375_13b.jpg" width="400"/>


<b>Medium motor </b><br><br>
The Medium Motor block controls the Medium Motor. You can turn the motor on or off, control its power level, or turn the motor on for a specified amount of time or rotations. Select the motor (A, B, C, or D) that you want the Medium Motor block to control by using the Port Selector on the top of the block.<br><br>
<img src="https://ae01.alicdn.com/kf/H3c02e7a620ae4d7f99ff510a7a126cean.jpg" width="250"/>

<b>Gyro</b>

Use the Mode Selector to select how you want to control the motor. After selecting the mode, you can choose values for the inputs. The inputs available will change depending on the mode. The modes and inputs are described below.
