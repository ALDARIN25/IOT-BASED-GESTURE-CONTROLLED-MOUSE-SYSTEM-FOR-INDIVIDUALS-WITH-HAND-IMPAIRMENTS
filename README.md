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
- `gesture_mouse.ino` – Arduino source code
- `circuit_diagram.png` – (Optional) Circuit setup image
- `README.md` – Project overview and instructions

## ⚙️ How It Works
1. The MPU6050 gyroscope tracks user movements.
2. The Arduino processes the data and matches gestures using the DTW algorithm.
3. Servo motors simulate mouse actions.
4. Users can train the system to recognize custom gestures.

## 🧪 Use Case
This project aims to empower individuals with physical impairments by providing them with an affordable and accessible way to use a computer without traditional input devices.

## 📸 Demo
![ IOT-BASED-GESTURE-CONTROLLED-MOUSE-SYSTEM-FOR-INDIVIDUALS-WITH-HAND-IMPAIRMENTS](project_photo.jpg)


