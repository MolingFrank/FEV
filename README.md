# FEV Team - WRO Future Engineers Competition
## Self-Driving Car

### Introduction
Welcome to the README.md file for our robotics team's self-driving LEGO car developed for the World Robot Olympiad (WRO) Competition. In this document, we will provide an overview of the robot, its components, the development process, and how to compile and upload the code to the vehicle's controller.

### Robot Overview
Our self-driving LEGO car is designed to navigate a predefined map while avoiding red and green obstacles. It utilizes a combination of hardware components and software modules to achieve autonomous navigation.

### Electromechanical Components
The robot consists of the following electromechanical components:

1. **LEGO EV3 Brick**: The core controller of the robot, responsible for processing sensor data and executing motor commands.

2. **Raspberry Pi**: Used for high-level computation and communication. It interfaces with the LEGO EV3 Brick and hosts the neural network for object detection.

3. **Motors and Wheels**: The robot is equipped with LEGO motors and wheels for movement control.

4. **Sensors**:
   - **Color Sensor**: Used for detecting red and green obstacles.
   - **Ultrasonic Sensor**: Provides distance measurement to avoid collisions.
   - **Camera**: Mounted on the Raspberry Pi for image capture and object recognition.

### Development Process
1. **Building the LEGO Car**: We assembled the physical components of the LEGO car, ensuring that the sensors were appropriately positioned for effective detection.

2. **Installing Required Software**:
   - Set up Raspbian on the Raspberry Pi.
   - Install Python libraries for TensorFlow and OpenCV.
   - Download and install the Donkey Car framework for autonomous vehicle control.

3. **Code Modules**:
   - **Tensorflow**: We developed a custom TensorFlow model for object detection and recognition. Training data was collected using the robot's camera.
   - **OpenCV**: Used for image processing and preprocessing tasks.
   - **LEGO EV3 Code**: Developed code to interface with the LEGO EV3 Brick, control motors, and read sensor data.
   - **Donkey Car Code**: Adapted the Donkey Car codebase to our LEGO car, integrating our TensorFlow model and defining control policies.

4. **Mapping and Navigation**: We created a map of the competition area and implemented algorithms for path planning and obstacle avoidance.

5. **Testing and Calibration**: Extensive testing was carried out to fine-tune the robot's behavior, sensor accuracy, and neural network performance.

### Compiling and Uploading the Code
To compile and upload the code to the vehicle's controller, follow these steps:

1. Clone the project repository to your Raspberry Pi.
   ```
   git clone <repository_url>
   cd <repository_directory>
   ```

2. Ensure that the required Python libraries (TensorFlow and OpenCV) are installed on your Raspberry Pi.

3. Configure the Donkey Car code to match your hardware setup and desired behavior by modifying the configuration files.

4. Train or load the pre-trained TensorFlow model for object detection.

5. Run the main script to start the autonomous navigation system.

   ```
   python main.py
   ```

### Conclusion
Our self-driving LEGO car is a result of the collaborative efforts of our robotics team. It combines hardware components like the LEGO EV3 Brick and Raspberry Pi with software modules such as TensorFlow, OpenCV, and Donkey Car code to achieve autonomous navigation while avoiding red and green obstacles.
