# IOT-BASED-GESTURE-CONTROLLED-MOUSE-SYSTEM-FOR-INDIVIDUALS-WITH-HAND-IMPAIRMENTS
# Gesture-Controlled Mouse System (Arduino-Based)

This project presents a hardware-based gesture-controlled mouse system designed to assist individuals who are hand-impaired or have no hands. Traditional input devices like a mouse or keyboard can be challenging or unusable for such users. This system provides an alternative by enabling computer control through body or head gestures, improving accessibility and usability.

## 💡 Features
- Hands-free mouse control using gestures
- Built using affordable components
- Customizable gesture training mode
- Real-time motion tracking using gyroscope
- Uses Dynamic Time Warping (DTW) for gesture recognition

## 🛠️ Hardware Components
- Arduino Uno
- MPU6050 Gyroscope Sensor
- Servo motors
- Gear motors


## 🔄 System Workflow

The gesture-controlled mouse system operates through a coordinated sequence of sensor input, signal processing, and physical output.

1. **Sensor Input**:  
   The MPU6050 gyroscope detects real-time gestures such as tilt, rotation, and directional shifts. It captures motion data across multiple axes and sends digital signals that represent these movements.

2. **Processing Unit (Arduino UNO)**:  
   The Arduino UNO receives motion data and processes it using embedded C code. It identifies specific gesture patterns and translates them into corresponding mouse control commands like cursor movement or mouse clicks.

3. **Output Execution**:  
   - **Gear Motor 1** controls horizontal cursor movement (left-right/X-axis)  
   - **Gear Motor 2** manages vertical cursor movement (up-down/Y-axis)  
   - **Servo Motor 1** simulates a left-click action  
   - **Servo Motor 2** simulates a right-click action  

Each gesture results in the Arduino sending precise signals to the motors, allowing the user to fully control the mouse using only hand gestures.


## 📂 Files Included
- `Mouse.txt` – Arduino source code
- `Architecture Diagram for Hand Gesture.png` –  Architecture Diagram for Hand Gesture
- `IoT based Gesture-Controlled Mouse real time.png` – IoT based Gesture-Controlled Mouse real time
- `README.md` – Project overview and instructions

## 📊 Response Time Analysis

Response time is a critical performance metric in gesture-based systems, as it directly influences the user experience. In the context of this system, response time refers to the delay between a user's gesture and the corresponding action being executed on the computer screen. Efficient response times contribute to a natural and uninterrupted interaction, thereby enhancing usability.

The system exhibited a fast response time of approximately **0.1 seconds** for general cursor movements—such as moving forward, backward, left, right, or stopping. These gestures corresponded to defined threshold values from the gyroscope’s **X** and **Y** axes, and were recognized and processed almost instantaneously. 

For click actions, which involved activating the servo motors, the response time was slightly longer—approximately **0.2 seconds** for initiating the click, and **1.0 second** for resetting the servo to its default position. This additional time accounts for the physical actuation of the servo and ensures proper positioning before accepting the next command.

### 📈 **Action and Sensor Values for Motor Control**

| Action         | Sensor Values                                | Description                                                                                          | Response Time (sec)        |
|----------------|----------------------------------------------|------------------------------------------------------------------------------------------------------|----------------------------|
| **Forward**     | xValue <= -20                               | Moves the motors forward when the x-axis tilt exceeds -20 units.                                     | 0.1                        |
| **Backward**    | xValue >= 30                                | Moves the motors backward when the x-axis tilt exceeds 30 units.                                     | 0.1                        |
| **Left**        | yValue < -20                                | Turns left when the y-axis tilt is less than -20 units and x-axis tilt is within -5 to 5 units.      | 0.1                        |
| **Right**       | yValue > 30                                 | Turns right when the y-axis tilt exceeds 30 units.                                                   | 0.1                        |
| **Left Click**  | xValue <= -10 and yValue <= -10             | Simulates a left-click by controlling the second servo when x and y-axis tilt exceed -10 units.      | 0.2 (click), 1.0 (reset)   |
| **Right Click** | xValue <= -10 and yValue >= 0               | Simulates a right-click by controlling the first servo when x-axis tilt is <= -10 and y is positive. | 0.2 (click), 1.0 (reset)   |
| **Stop**        | xValue, yValue, and zValue within -10 to 10 | Stops all motor actions when the tilt in all axes is minimal.                                        | 0.1                        |


## ⚙️ How It Works
1. The MPU6050 gyroscope tracks user movements.
2. The Arduino processes the data and matches gestures using the DTW algorithm.
3. Servo motors simulate mouse actions.
4. Users can train the system to recognize custom gestures.

## 🧪 Use Case
This project aims to empower individuals with physical impairments by providing them with an affordable and accessible way to use a computer without traditional input devices.

## 📸 Demo
![ IOT-BASED-GESTURE-CONTROLLED-MOUSE-SYSTEM-FOR-INDIVIDUALS-WITH-HAND-IMPAIRMENTS](project_photo.jpg)


