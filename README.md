# IoT based automated voice controlled device with obstacle avoidence

This project implements a voice-controlled robot with obstacle avoidance capabilities using an Arduino. The robot uses an ultrasonic sensor to detect obstacles and control the motors to avoid collisions. It also responds to voice commands received via serial communication.

## Components used:
* Arduino board (compatible with AFMotor library)
* Ultrasonic sensor (HC-SR04 or similar)
* Motor Driver Shield (AFMotor shield)
* DC Motors
* Servo motor
* Wires and breadboard

## Pin configuration:
* Trig: A1
* Echo: A0
* Motor 1 (M1): Motor port 1 on AFMotor shield
* Motor 2 (M3): Motor port 3 on AFMotor shield

## Dependencies:
* AFMotor library
* Servo library

## Installation
1. Connect the Hardware:

  * Connect the ultrasonic sensor's Trig pin to A1 and Echo pin to A0 on the Arduino.
  * Attach the motors to the motor driver shield on ports 1 and 3.
  * Attach the motor driver shield to the Arduino.
  * Setup the Software:

2. Install the AFMotor library and Servo library in your Arduino IDE.
  * Upload the provided code to your Arduino.

## Usage
 1. Power the Robot:

  * Ensure the Arduino is powered on.
 2. Voice Control:

  * Open the Serial Monitor in the Arduino IDE.
  * Send the following commands to control the robot:
  * froward: Move forward
  * backword: Move backward
  * stop: Stop
 3. Obstacle Avoidance:

  * The robot will automatically avoid obstacles by moving backward when an obstacle is detected within 12 cm.

## Code Explanation
### Global Variables and Setup
  * Echo, Trig, motor, Speed: Define the pins and speed.
  * char value: To store the serial input.
  * int distance: To store the measured distance.
  * Servo servo: Servo object.
  * AF_DCMotor M1(1), AF_DCMotor M3(3): Motor objects.

### Functions
  * setup(): Initializes the serial communication, sets pin modes, and motor speed.
  * loop(): Continuously checks the distance and decides between voice control and obstacle avoidance.
  * Obstacle(): Handles the obstacle avoidance logic.
  * voicecontrol(): Reads and processes serial commands to control the motors.
  * ultrasonic(): Measures the distance using the ultrasonic sensor.
  * forward(), backward(), Stop(): Motor control functions.

## Future Improvements
* Add more voice commands for enhanced control.
* Implement more sophisticated obstacle avoidance algorithms.
* Integrate other sensors for improved navigation.
  
## Troubleshooting
* Serial Communication Issues: Ensure the baud rate is set to 9600.
* Ultrasonic Sensor Accuracy: Ensure proper wiring and connections.
* Motor Control: Check the motor driver connections and power supply.

## License
* This project is open-source and available for modification and distribution.


