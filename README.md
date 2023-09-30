# Robotics Team - WRO Competition
## Self-Driving LEGO Car

### Introduction
Welcome to a comprehensive overview of our robotics team's remarkable creation - the self-driving LEGO car meticulously engineered for the World Robot Olympiad (WRO) Competition. In this document, we will delve into the technical aspects, elucidating the hardware components, the development process, and the procedures for compiling and uploading the code to the vehicle's controller.

### Robot Overview
Our self-driving LEGO car represents a significant technological achievement. Its primary goal is to autonomously navigate a course while demonstrating obstacle avoidance capabilities, particularly in the presence of red and green obstacles.

### Electromechanical Components
The fundamental electromechanical components that compose our self-driving LEGO car include:

- **LEGO EV3 Brick**: Serving as the central controller, the LEGO EV3 Brick plays a pivotal role in processing sensor data and executing precise motor commands.

- **Raspberry Pi**: Functioning as the computational powerhouse, the Raspberry Pi manages high-level tasks, acting as an intermediary between the LEGO EV3 Brick and our neural network for object detection.

### Mobility Management
Our mobility management revolves around the use of standard LEGO motors. These motors are renowned for their reliability and precision, enabling our self-driving LEGO car to achieve fluid and controlled movement. The motors are meticulously integrated with the vehicle's wheels to ensure agile and stable navigation.

### Power and Sense Management
The power and sense management aspects are crucial for the smooth operation of our self-driving LEGO car.

### Power Source
The primary power source for our vehicle is carefully selected to ensure uninterrupted operation during competition. We employ rechargeable batteries to power both the LEGO EV3 Brick and the Raspberry Pi. This choice provides the necessary endurance for prolonged competition rounds while maintaining consistent voltage levels for optimal performance.

### Camera
The onboard camera captures real-time images for object recognition and navigation.

### Obstacle Management
Our robot's ability to perceive and negotiate obstacles is a critical aspect of its performance. Here, we outline our strategy for obstacle management, including flow diagrams and pseudocode.

#### Obstacle Detection Flow Diagram
![Obstacle Detection Flow Diagram](insert_link_to_image_here)

#### Obstacle Negotiation Flow Diagram
![Obstacle Negotiation Flow Diagram](insert_link_to_image_here)

#### Obstacle Detection Pseudocode
```python
# Pseudocode for obstacle detection
while navigating:
    if obstacle_detected():
        distance = measure_distance()
        if distance < safe_threshold:
            stop()
            if is_red_obstacle():
                bypass_red_obstacle()
            elif is_green_obstacle():
                avoid_green_obstacle()
            else:
                backtrack_and_recalculate()
        else:
            continue_navigating()
    else:
        continue_navigating()

# Pseudocode for bypassing red obstacle
def bypass_red_obstacle():
    turn_left()
    move_forward()
    turn_right()
    move_forward()

# Pseudocode for avoiding green obstacle
def avoid_green_obstacle():
    turn_right()
    move_forward()
    turn_left()
    move_forward()

# Pseudocode for recalculating path
def backtrack_and_recalculate():
    reverse()
    turn_around()
    calculate_alternative_path()
```

### Compiling and Uploading the Code
To compile and upload the code to the vehicle's controller, follow these procedural steps:

1. Clone the project repository to the Raspberry Pi:
   ```
   git clone <repository_url>
   cd <repository_directory>
   ```

2. Ensure that essential Python libraries, including TensorFlow and OpenCV, are correctly installed on the Raspberry Pi.

3. Customize the Donkey Car code to align with your specific hardware configuration and desired operational behavior by modifying the configuration files.

4. Train or utilize a pre-trained TensorFlow model for object detection.

5. Launch the main script to initiate the autonomous navigation system:
   ```
   python main.py
   ```

### Conclusion
Our self-driving LEGO car stands as a testament to the dedication and expertise of our robotics team. It seamlessly combines advanced hardware components, including the LEGO EV3 Brick and Raspberry Pi, with sophisticated software modules such as TensorFlow, OpenCV, and Donkey Car code.

