Report on a true autonomous vehicle solution



WRO Season 2023
Future  Engineering 

Using the method of machine learning, a CNN neural network is built to train and predict the pictures of the competition venue.
This is our AI CyberLEGO Car







OCT 4, 2023

Team FEV USA
Team Presentation
 
Team Members:  
 Fengmo Guo 
 Evan Yu Girard-Sun 
 Vinaya Ayinampudi

Coach:  Fei Guo 
 





FengMo Guo, a tenth-grade high school student from New York, United States. He had participated in WRO in previous seasons. He loves robots and is a very innovative person. 
 


Evan Girard-Sun, Evan is a 10th grade high school student who enjoys 3D design and modelling, soccer, and playing the violin, and was a member of 2022 WRO Junior RoboMission National Championship team!



Vinaya Ayinampudi，a tenth grader at Eastvale STEM Academy who enjoys playing volleyball, and coding in her free time. She loves working with new technology and is very enthusiastic about robotics!




 

Summary of our Project A combination of half-AI and half-robot, a real AI autonomous driving robot. 

Technical solution design
LEGO robot and car body structure design
AI operating environment design, including structure design, power supply design, communication design, remote control handle.
Remote monitoring system design, website design.

Communication Design:
The handle communicates with the Raspberry Pi and the Raspberry Pi communicates with the LEGO robot car.

Control logic design:
The remote control robot records the picture and data of the playing field
Design neural networks
Train a neural network with a field model.
During the game, the neural network calls in the trained behavioral model to make actions that mimic human operations.
This action data is transmitted to the LEGO robot. There are LEGO robots performing action parts.
At the same time, the LEGO robot carries out secondary control. Gyro sensors and a LEGO PIXY2-enabled AI camera verifies AI-made judgments. And participate in judgment, controlling vehicle start and customization at start and end.

AI software code design:
Take photos and record data sections.
SECTION USING WEB REMOTE MONITORING.
Run the AI neural network and train the part of the data that yields the result.
The part where the neural network model is called in real time to make a prediction of the captured video.
The part that transmits the prediction data to the LEGO robot.
The LEGO robot receives the data and performs the part of the action.


 
Overall technical solution design
Technical Background:
Machine learning (ML) is an umbrella term。 It refers to a computer software approach that lets machines find and optimize algorithms on their own. 

Convolutional neural network CNN is a multi-layered data processing structure. In particular, it has advantages in AI image recognition. Therefore, it has a very good performance in the field of autonomous driving.Convolutional neural network (CNN) is a regularized type of feed-forward neural network that learns feature engineering by itself via filters (or kernel) optimization.
 

TensorFlow is a free and open-source software library for machine learning and artificial intelligence.

Lego Mindstorms EV3 is LEGO Education's programmable robot hardware, which is very easy to build structures and very easy to program. AT PRESENT, WORLD-RENOWNED YOUTH ROBOTICS COMPETITIONS SUCH AS FIRST LEGO LEAGUE AND WRO ARE USING LEGO'S ROBOTICS PRODUCTS. 




Technical ideas:
Future Engineering is an autonomous driving competition that avoids obstacles at the venue. We designed to use the Raspberry Pi as avehicle for A-I operations. Under the operating system of Raspberry Pi's Linux OS, the python IDE integrates the runtime environment. Install Google's tensorflow. Install the lens on the Raspberry Pi. Start by running a program that records a video of a real vehicle moving and remote control data. The data is then fed to a CNN neural network, which uses machine learning methods to find connections between video images and remote control data. Then apply this model to the recognition of real lens photos. Let the AI give the vehicle's operating data. This data is then transmitted to a vehicle built with a LEGO EV3. Make LEGO cars self-driving. 

All vehicle photos are shown in v-photos file.



In order to display the vehicle data more accurately, we also designed a web server, which also runs on the Raspberry Pi. Each frame of the footage is transmitted in real time by this web server. In this way, the live view of the lens can be accessed through the web page.

 


After developing our robotic system, we found that it has effectively accomplished the task. The system can simulate real-life navigation by capturing video footage of the canal and making predictive navigational decisions. Although it may require further adjustments in a real-world setting, such as incorporating elements from autonomous car projects, we believe that it holds significant practical value, similar to that of autonomous vehicles.

Therefore, we decided to apply end-to-end (END TO END) autonomous driving technology to the task of guiding ships through these areas.

The heart of our system is a single-board computer, specifically a Raspberry Pi 4, coupled with a camera. This setup captures real-time images from the monitor displaying the canal. We also used a joystick that provides data for the learning phase of the project. This combination allows us to pair real images with steering and throttle data, creating a comprehensive learning file that the AI can use to improve its performance.



Photos of the Data We Captured Are Shown In The scr File.

 
 
Schematic Diagram of the CNN (Convolutional Neural Network) Recognition and Judgment after Training are shown in the schemes File.

 
 


In our project, the hardware aspect mainly includes the display, the single-board computer, especially the Raspberry Pi 4, and the camera. The combination of the Raspberry Pi 4 and camera is used to capture live images from the playing field. In addition, we have a joystick that provides data during the learning phase of the project. This combination allows us to pair live images with steering and throttle data to create a comprehensive learning file for the AI to improve its performance.



Initially, raw data, such as images, is collected and stored on a Raspberry Pi. Then, this data is transferred to a standard computer for further processing.

On the computer, a series of training programs are run, using the collected data to train an AI self-driving model. This training process results in a file which contains the AI model. This file, essentially our trained self-driving model, is then put back onto the Raspberry Pi.

The Raspberry Pi, with the help of the AI model, interprets real-time images and determines specific control instructions, like throttle and steering data. Then, this information is transmitted to the LEGO robot via Bluetooth.

The LEGO robot here mainly plays the role of a model demonstrator. Upon receiving the data, the LEGO robot displays corresponding movements, like moving forward or backward (corresponding to throttle control), and turning left or right (corresponding to the steering wheel). Therefore, the LEGO robot essentially serves as a tangible representation of the AI self-driving model's effects. Basically, that's all there is to the hardware part of the project!

 
Pi-os（linux）
 


Python
  


Tensorfolw
 


In terms of software, there are several important elements to note in our project. 

Firstly, we run the Linux operating system on our Raspberry Pi. Within this system, we use Python as our programming language and TensorFlow as the tool for our AI modelling and training tasks.

Let me walk you through how the software side works. Using Python, we control the Raspberry Pi's camera to capture images and collect data. Additionally, we connect a joystick via Bluetooth, and both the joystick data and the images from the camera are stored together.

Next, we package all of this data and hand it over to TensorFlow. Inside TensorFlow, we've built a Convolutional Neural Network (CNN) model for training. The inputs to the model are a video matrix, steering control input, and throttle data input. These three types of inputs pass through eleven layers of the network, and in the end, two types of outputs are produced: the steering wheel output and the throttle output. This process creates our AI self-driving model.

Finally, we transmit the data to our Lego robot via Bluetooth. The Lego robot is programmed using its proprietary language. It primarily serves to showcase the received data, controlling the motors to drive forward or turn left and right. This sums up the software portion of our project.
 

 
Challenges we met: Throughout the development of this project, we encountered a series of challenges. First off, there was the issue of image resolution. If we chose to work with larger image resolutions, our machine computations slowed down significantly, resulting in training sessions that could take longer than 8 hours. To solve this, we downscaled the data and used a resolution of 160 by 120 pixels.

Next, we grappled with a problem of overly lengthy road models. To address this, we segmented a portion of the data model for training. Finally, we faced issues of software compatibility. For instance, we found that a model trained on TensorFlow 2.9 wouldn't work on TensorFlow 2.4. To remedy this, we upgraded all systems to use TensorFlow 2.9 for a more unified approach to training.

Report on A true Autonomous Robotics Vehicle Solution

Using the method of machine learning, a CNN neural network is built to train and predict the pictures of the competition venue.
This is our AI CyberLEGO Car

WRO 2023
Future Engineers

Team
F.E.V. USA
Nov 07-09, 2023

Contents

Team Presentation

Summary of the Project Ideas
▫ Executive Summary
▫ Technical Solution Design
▫ Overall Technical Solution Framework
Project Detail Solution Analysis
▫ Mobility Management for Autonomous Robotics Vehicle
▫ Power & Sense Management
▫ Obstacle Management
▫ Software and Coding (Photos)
▫ Challenges and Solutions
Conclusion

Team Presentation

Team Members:
Fengmo Guo
Evan Yu Girard-Sun
Vinaya Ayinampudi
Coach:
Fei Guo

FengMo Guo, a tenth-grade high school student from New
York, United States. He had participated in WRO in previous
seasons. He loves robots and is a very innovative person.

Evan Girard-Sun, Evan is a 10th grade high school student
who enjoys 3D design and modelling, soccer, and playing
the violin, and was a member of 2022 WRO Junior
RoboMission National Championship team.

Vinaya Ayinampudi: Hello my name is Vinaya, I am a 10th
grader at eSTEM. In my free time I like to code, play
volleyball, and bake. I love to experiment with robots and
learn more about what we can do with AI. This year I have
learned a lot about robotics and I can’t wait to continue this
journey!

Summary of the Project Ideas

Project combination of semi-artificial intelligence and semi-robotics, a real artificial intelligence self-driving robot. Executive Summary Future Engineering is an autonomous driving competition that avoids obstacles at the venue. We designed to use the Raspberry Pi as a vehicle for AI operations. Under the operating system of Raspberry Pi's Linux OS, the python IDE integrates the runtime environment. Install Google's Tensorflow. Install the lens on the Raspberry Pi. Start by running a program that records a video of a real vehicle moving and remote control data. The data is then fed to a CNN neural network, which uses machine learning methods to find connections between video images and remote control data. Then apply this model to the recognition of real lens photos. Let the AI give the vehicle's operating data. This
data is then transmitted to a vehicle built with a LEGO EV3. Make LEGO cars self-driving.

Technical Solution Design

Design of LEGO Robot and Vehicle Structure:

We crafted the design of the LEGO robot and its car body, focusing on an AI-driven operating environment. This includes meticulous planning of the structural design, power supply, communication systems, and the remote control interface.

Communication Design:
Our design facilitates communication between the remote control interface and the Raspberry Pi, which in turn communicates seamlessly with the LEGO robotic car.

Control Logic Design:
The control logic involves recording the playing field's images and data through a remote-controlled robot. We designed and trained a neural network using a model of the field. During gameplay, the neural network accesses the trained behaviour model to execute actions reminiscent of human operations. These action commands are sent to the LEGO robot, which then performs the designated tasks. Additionally, the LEGO robot executes secondary control measures, with gyro sensors and an AI-enabled LEGO PIXY2 camera corroborating the AI’s decisions and aiding in the control of the vehicle's initiation and customized operations at the start and end of its tasks.

AI Software Code Design:
The software design includes segments for capturing images and data, utilizing web-based remote monitoring, and running the AI neural network. We trained it with the relevant data to yield actionable results. It also includes real-time invocation of the neural network model to predict outcomes based on captured video feeds, and subsequent transmission of these predictive data to the LEGO robot, which then acts accordingly.

Overall Technical Solution Framework
Technical Background:
Machine learning (ML) encompasses a spectrum of methodologies that empower computers to autonomously discover and refine algorithms. A convolutional neural network (CNN) is a specialized feed-forward neural network that inherently learns and perfects feature engineering through filter optimization, making it particularly effective in AI image recognition and autonomous driving applications.

TensorFlow is a renowned, open-source software library dedicated to machine learning and artificial intelligence, offering a versatile toolkit for developers. The LEGO Mindstorms EV3 represents LEGO Education's programmable robotics platform, lauded for its ease of assembly and programming. It's the hardware of choice in prestigious international youth robotics competitions, which underscore the global recognition and adoption of LEGO's robotics products.

Project Detail Solution Analysis

* Mobility Management for Autonomous Robotics Vehicle
Chassis Design and Component Mounting
Our Autonomous Robotics Vehicle (ARV) is designed with a prime focus on efficient mobility management, which is evident in the vehicle’s chassis design and component mounting. Initially conceptualized using the versatile LEGO EV3 platform, we selected this design framework due to its structural convenience and the abundant availability of components that facilitate ease of construction and accessibility. The chassis is composed of a durable and lightweight material suitable for competitive robotic applications. The design mirrors real-world vehicle dynamics with a front steering mechanism and a rear differential power structure. Unlike the conventional dual-wheel differential, our ARV employs a twin-motor system that propels a central axle using differential gears, similar to those found in full-scale automobiles and remote-controlled cars. This allows for precise power distribution to the left and right rear wheels, enabling the ARV to adjust the rotational speed of each wheel autonomously in response to the steering inputs. The major enhancement in the design came after initial testing, where we noticed a slight outward tilt in both front and rear wheels under the load. To counteract this, structural reinforcement was added to the outer sides of the wheels to ensure an even distribution of forces across the chassis, preventing any inclination and maintaining stability during maneuvers.

Motor Selection and Implementation
Selecting the appropriate motors was critical to achieving the desired speed, torque, and power specifications. Our team rigorously tested various motors
to determine the best fit for our ARV, ultimately settling on two high-torque motors capable of providing a balanced combination of speed and power. These motors enable the
vehicle to carry a total weight of 1.5 kilograms, including its own chassis and mounted components, while achieving speeds ranging from 1.2 to 1.5 meters per second. The motors are mounted on the rear of the chassis, directly connected to the central axle. This configuration uses differential gears to distribute power efficiently to the rear wheels, adjusting the vehicle's speed dynamically in response to steering inputs without compromising on the torque necessary for acceleration or inclines.

Lego structure design for Raspberry Pi is a very distinctive design, and since the Raspberry Pi itself cannot be connected to the Lego structure, we designed a Lego structure to tie the Raspberry Pi in the middle. The effect of this is that the structural parts on theoutside of the Raspberry Pi can be easily connected to the LEGO parts. Before making AI imitate how humans operate remote-controlled cars, it is necessary to make the vehicles manipulable by humans. We use theSony Playstation 4 Dual Shock 4 Controller as our vehicle remote.

Engineering Principles: Speed, Torque, Power Usage
In the engineering of our ARV, principles of speed, torque, and power usage are intricately balanced. The ARV's speed tests show that it can consistently achieve 1.2 to 1.5 meters per second, which represents an optimal range for maintaining control and stability during autonomous navigation

LEGO rear wheel power structure design:
“Please note that the two LEGO motors are not differential-driven. Instead, standard vehicle shaft transmission is used.”

Torque is a critical factor, especially when the ARV is expected to carry additional weight or navigate uneven terrain. The high-torque motors selected are crucial for these aspects, ensuring that the ARV can start moving from a standstill and overcome any obstacles with ease.

Structural design of steering gear
The LEGO EV3 medium-sized motor moves the gears left and right.

Power management is essential to maintain efficiency and ensure the longevity of operation. Our design ensures that power usage is optimized through the differential gear system, which not only provides a realistic driving experience but also conserves energy by adjusting the power output to the wheels based on the steering and speed requirements.

Assembly Instructions and experiences sharing
To facilitate the replication and further development of our Autonomous Robotic Vehicle (ARV), we have provided detailed assembly instructions thatguide builders through every step of the construction process. In addition, we have produced a video that gives an overview of our ARV's components, which is available on YouTube:

https://www.youtube.com/channel/UC-xgtNl2sAxedzdm55sLFWw

We hope to share these resources for the use of educational institutions and enthusiasts alike, with the aim of fostering a collaborative and innovative environment in the field of robotics technology.

In summary, the design of our ARV takes into account the practical realities of vehicle dynamics. We are confident that it stands as a robust entry in the World Robotics Olympiad, demonstrating our commitment to excellence in the competition.

Evolution of Design from National to Global Competition
The evolution of our Autonomous Robotic Vehicle (ARV) design from the national competition to the finals has been significant. The improvements were not limited
to the chassis but spanned various aspects of the vehicle.
() Upgraded Wheel Design for Improved Performance
Firstly, we transitioned to larger wheels, increasing the diameter by approximately 1.9 times compared to the original design. This adjustment led to enhanced speed
capabilities because larger wheels cover more distance with each rotation. Additionally, the contact area of the wheels was reduced to one-fourth of its original size, similar to the design principle of a bicycle. This reduction in contact area resulted in greater agility and reduced friction during movement. The narrower wheels, coupled with our front steering mechanism, allow for easier and more responsive steering.
() Chassis and Overall Structural Improvements
The main body of the chassis, constructed from LEGO EV3, remains integral to our design. For wheel control, we used the LEGO EV3 programmable brick. This facilitated precise movements and navigation during the competition. In terms of the vehicle's sensory capabilities, we incorporated a Raspberry Pi equipped with a camera. The main sensing device was a Raspberry Pi with a camera, running an end-to-end autonomous driving neural network within the Google TensorFlow software environment.
() Division of Structural Components
Overall, the structure of our ARV is divided into three main sections:
1. The chassis and powertrain are constructed using LEGO EV3 components.
2. The onboard computing is handled by a Raspberry Pi 4 board, supplemented by
a camera for real-time image processing.
3. The exterior structure for the Raspberry Pi and additional components is also
made from LEGO pieces, ensuring seamless integration with the rest of the
vehicle.
4. An AI-specific camera, the Pixy2, is used to distinguish between red and green
modules during the competition.

The advancements in the design and engineering of our ARV were deliberate and methodical, ensuring that each modification served a purpose towards enhancing
the vehicle's performance in anticipation of the global competition stage. The larger wheels for speed, reduced contact area for less friction, and the robust sensory apparatus provided by the Raspberry Pi and Pixy2 camera all contributed to a more competitive and agile machine. This holistic approach to the ARV's development reflects our commitment to innovation and excellence in the field of robotics.

The most frequently asked question:
Have you considered any vehicle types other than LEGO cars? What was the thought process during this decision-making?

"In our decision-making process for this project, we considered various vehicle models beyond the LEGO car. Despite exploring other options, we ultimately chose the LEGO vehicle due to specific advantages it offered. The LEGO car, unlike standard RC cars, allows for secondary programming and control through software, offering a two-tier control system. The upper tier utilizes AI programming for decisions like turning left or right, while the lower tier employs sensors such as gyroscopes, colour detectors, and camera sensors like Pixy for enhanced control. The flexibility of the LEGO system is significant. It is not confined to a single control unit, thus offering greater adaptability. However, this flexibility does come with its challenges, including increased potential for faults due to the complexity of having two independent systems and the need for more extensive programming. A notable limitation of the LEGO car is its lack of native support for data transmission. We circumvented this by emulating a 1V3 communication protocol with a Raspberry Pi, which added to the code complexity and operational procedures during startup and shutdown phases.Despite these issues, LEGO cars are well-suited for adaptability, easilyintegrating with other systems and facilitating smoother interaction with the control software. One might argue that speed is a compromise, as LEGO motors do not match the velocity and load-bearing capacity of high- performance RC cars, which affects their ability to be as rapid.

Nevertheless, the decisive factor in our choice was the suitability of the LEGO car for our current instructional and competitive requirements. It offers a balanced combination of speed and agility, familiarity with the hardware, and a certain ease in achieving the objectives of target recognition and control. Looking towards the future and considering real-world applications, such as autonomous driving, the technology we use now can be seen as a simplified version of AI driving. Actual vehicular AI encompasses multiple coordinated systems rather than a single end-to-end solution. This approach reflects a more complex and realistic model where various modules for sensing, video processing, target recognition, and map matching must work in concert to navigate effectively.

Vehicle Model Evaluation

To summarize, our design choice advocates for a comprehensive learning experience where the coordination of multiple systems is crucial. The LEGO platform, with its flexibility and high adaptability, serves as a robust starting point for finding innovative solutions to various challenges, unrestricted by the limitations of the vehicle's physical capabilities. Hence, after weighing all these considerations, we finalized our design choice for this competition."

Standard RC Cars LEGO Cars

- Pros: High speed and simple
mechanical structure.

Allows for complex programming, has a
dual-layer control system, and is equipped
with advanced sensor technology.

- Cons: Lack of programmability
and secondary control,
which limits advanced
autonomous functions.

Lower speed compared to high-
performance RC cars, more points of

failure due to complex system integration.

* Power & Sense Management:
Our technical solution incorporated a dual system approach for managing the
power and sensing capabilities of the autonomous LEGO vehicle.
Power Management:
The power supply for the LEGO Mindstorms EV3 system utilizes a 10.5-volt
lithium battery provided by LEGO. In parallel, the Raspberry Pi, which runs
the Google TensorFlow framework, is powered by a 10,000 mAh portable
charger, ensuring continuous operation during competitions. Communication
between these two systems is established via Bluetooth, enabling seamless
interaction and control.
Sensing and Decision-Making
The vehicle leverages a Convolutional Neural Network (CNN) for processing
visual inputs captured by the AI camera. This CNN is trained on images and
corresponding remote control actions, learning to mimic human steering
habits and movement patterns. During live performance, the neural network
makes predictions based on real-time visuals, determining appropriate
steering and throttle responses (strato). These predictions are then transmitted
to the EV3 system, which executes the actions through its motors.
Integrated Approach
Our design philosophy has always been to integrate Artificial Intelligence
with traditional programming techniques. By training the AI with vast
datasets, it acts like a brain, analyzing information and making predictive
judgments based on the learned driver behaviours. It's through this synthesis
of AI and conventional coding that the vehicle's entire operation is guided.
This innovative blend of power management, machine learning, and sensor
integration marks our standout feature. It represents a shift from relying
solely on pre-programmed machine responses or computer vision techniques

towards a model that encompasses pure AI-driven decision-making for real-
time control in robotic competitions.

* Obstacle Management:
In our autonomous LEGO vehicle project, the approach to obstacle
management is distinctively different from traditional automated
programming. Our technical philosophy has been consistent from the
beginning, focusing on a strategy that does not rely on pre-defined rules or
flowcharts for navigating around obstacles.
Instead of traditional programming techniques such as using flowcharts,
pseudocode, or annotated code, we employ a data-driven approach with our
AI. The AI learns to drive the vehicle through actual operation by a human
operator. The machine records how the operator drives, noting steering and
throttle data, and then this data is used to train a neural network.

Before making AI imitate how humans operate
remote-controlled cars, it is necessary to make
the vehicles manipulable by humans. We use the
Sony Playstation 4 Dual Shock 4 Controller as
our vehicle remote.

During the training phase, initially, the vehicle could not distinguish colours
such as red and green but was able to identify and navigate around obstacles.
With the accumulation of more data - around 70,000 data points - the vehicle
began to discern obstacles. At 90,000 data points, it could differentiate and
react to colours, associating red with turning right and green with turning left.
Our primary focus has been on accurately recording the operator's maneuvers
and feeding this extensive dataset to the model, allowing it to learn driving
habits and patterns - a process known as 'fitting.' There is no traditional
strategy or flowchart involved; the vehicle's ability to navigate through the
course and manage obstacles is entirely based on continuous training from
the data gathered during these driving sessions.

Key points:
- Our obstacle management doesn't depend on traditional programming
flowcharts or rules.
- We use neural networks to accumulate and learn from the behavioural data
of human drivers.
- As the amount of data grows, the AI's responsiveness and judgment
improve.
- Initially, the vehicle couldn't recognize colours, but eventually, it learned
how to respond to different obstacles through data training.
In summary, our core strategy for obstacle management is purely based on
training the AI model with real-world driving data, enabling it to make its
own judgments when encountering obstacles, without any pre-set turnarounds
or path strategies. This data-centric approach allows the AI to learn and adapt
in a way that mirrors human learning and decision-making processes.

* Photos of the Data We Captured
Photos of the Data We Captured

Photos of the Data We Collected

Schematic Diagram of the CNN (Convolutional Neural Network)
Recognition and Judgment after Training

In our project, the hardware components primarily consist of a display, a
single-board computer—specifically the Raspberry Pi 4—and a camera. We
use the Raspberry Pi 4 in conjunction with the camera to capture real-time
images from the play area. Additionally, during the learning phase, we
employ a joystick to collect control data. This setup enables us to synchronize
live footage with control input, such as steering and throttle actions, thereby
creating a detailed dataset for the AI to refine its driving algorithms.
At the outset, we gather raw data, like images, using the Raspberry Pi. This
data is subsequently transferred to a conventional computer for advanced
processing.
On this computer, we execute a series of specialized programs that leverage
the collected data to train an AI model capable of autonomous driving. The
outcome of this training is a file that encapsulates the AI model, which we
then reload onto the Raspberry Pi.
Armed with this AI model, the Raspberry Pi analyzes the live images and
generates precise control instructions, including throttle and steering
commands. These commands are sent wirelessly to the LEGO robot using
Bluetooth technology.
The LEGO robot acts as a physical proxy, demonstrating the AI model's
driving decisions in a tangible format. Upon receiving the instructions, the
LEGO robot exhibits movements such as advancing or reversing,
corresponding to throttle input, and executing left or right turns, indicative of
steering commands. Thus, the LEGO robot visibly manifests the capabilities
of the AI self-driving model. Essentially, this encapsulates the entirety of the
hardware aspect of our project.
Pi-os(linux) Python

Tensorfolw

In our project, the software component encompasses several critical elements.
We utilize the Linux operating system on our Raspberry Pi. Within this
environment, Python is our chosen programming language, and TensorFlow
serves as the backbone for AI model development and training.
Here’s an overview of how the software operates: Python scripts manage the
Raspberry Pi’s camera to take images and gather corresponding data. We also
connect a joystick through Bluetooth, combining its input with the camera's
images for storage.
Subsequently, this data is collated and processed with TensorFlow, where
we've constructed a Convolutional Neural Network (CNN) for the machine
learning aspect. The model ingests a composite of video feeds, steering
inputs, and throttle data. These inputs traverse through an eleven-layer
network, culminating in the generation of two types of outputs—steering and
throttle commands. This sophisticated process yields our AI self-driving
algorithm.
The final step involves transferring these commands to our Lego robot using
Bluetooth. The robot, programmed in its unique language, interprets the data
to manipulate its motors, enabling it to drive, turn, and showcase the practical
application of the AI model. This encapsulates the software facet of our
endeavour.

Python Code for Capturing Photos:

Code for the Lego Robot

Challenges we met
Throughout the development of this project, we encountered a series of
challenges. First off, there was the issue of image resolution. If we chose to
work with larger image resolutions, our machine computations slowed down
significantly, resulting in training sessions that could take longer than 8
hours. To solve this, we downscaled the data and used a resolution of 160 by
120 pixels.
Next, we grappled with a problem of overly lengthy road models. To address
this, we segmented a portion of the data model for training. Finally, we faced
issues of software compatibility. For instance, we found that a model trained
on TensorFlow 2.9 wouldn't work on TensorFlow 2.4. To remedy this, we
upgraded all systems to use TensorFlow 2.9 for a more unified approach to
training.

* Conclusion

Our team has employed a unique approach in the design of our intelligent vehicle,
which is characterized by the use of a pure Artificial Intelligence (AI) model. At
the heart of this system is a Convolutional Neural Network (CNN) that operates
under a Linux environment, utilizing Google's TensorFlow. The purpose of the
CNN is to learn and emulate the driving habits of the operator. It does this by
processing images captured by the camera and the movements of the remote
control, allowing the network to train itself to respond to these inputs.
In practice, the neural network analyzes images from the race, making predictions
about the best course of action in a given situation. These decisions are then
communicated to the vehicle's power system — in our case, the LEGO EV3 —
enabling the vehicle to execute commands for steering and throttle adjustments.
To support this system, we have implemented a dual power supply setup. The
LEGO EV3 is powered by a 10.5-volt proprietary lithium battery specific to
LEGO, and the Raspberry Pi is powered by a 10,000 mAh portable power bank.
The two systems communicate via Bluetooth, working in tandem to ensure stable
vehicle operation.
In terms of ground perception modules, our AI captures images with its camera and
processes them using the CNN, which then compares them with a well-trained
model to make accurate predictions. The decisions about steering and throttle are
sent to the LEGO EV3, which are then carried out by the EV3's motors.
Our design philosophy has been clear and consistent from the beginning: to merge
the benefits of traditional programming with AI. By feeding the AI a wealth of
data, it processes information and analyzes data like a brain, making predictions
while also learning the driver's habits, thus humanizing the vehicle's driving
behaviour. Our intelligent vehicle is not merely mechanically operated; it is driven
by an intelligent system that combines precise programming with an AI model for
an enhanced driving experience.

Index

Donkey car:https://www.donkeycar.com/
Pi camera:https://picamera.readthedocs.io/en/

release-1.13/index.html#

Tornado webserver:https://tornado-
zh.readthedocs.io/zh/latest/#

Tensorflow:https://www.tensorflow.org
Kersa:https://keras.io/about/
Github:https://github.com/

—-Thank You—-



