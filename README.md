# PID Line Follower. ESP32

I built a robot that follows a line using a kind of control called PID. It is based on the ESP32 DevKit V1. The robot uses an array of sensors a motor driver and Bluetooth to adjust its settings in real time.

## Features

- The PID control makes the robot follow the line smoothly and accurately
- The robot has a 5-channel infrared sensor array to detect the line
- You can adjust the robots settings using Bluetooth
- If the robot loses the line it will spin around until it finds it again
- The robot has a custom circuit board with a voltage regulator

## Hardware

- The brain of the robot is the ESP32 DevKit V1
- The motor driver is a TB6612FNG
- The robot uses 5 analog sensors
- The voltage regulator is an LM7805
- The robot has capacitors and connectors for the power and sensors

### Pin Mapping

The robots signals are connected to the ESP32 as follows:

- Motor 1 direction is connected to pins 21 and 22
- Motor 1 speed is connected to pin 23
- Motor 2 direction is connected to pins 25 and 33
- Motor 2 speed is connected to pin 32
- The infrared sensors are connected to pins 26, 27, 14, 12 and 13

## Software Dependencies

To make the robot work you need to install some libraries:

- L298N for the motor driver
- QTRSensors for the sensors
- BluetoothSerial for Bluetooth communication

### Board Setup

To set up the board you need to:

- Install the ESP32 Arduino core
- Select the ESP32 Dev Module as your board
- Make sure Bluetooth is enabled

## How It Works

### Calibration

When you turn on the robot it will calibrate itself for 10 seconds. During this time you need to move the robot over the line so the sensors can learn what the line looks like.

### PID Loop

The robot uses a kind of math to follow the line. It calculates an error value based on how the robot is from the line. The robot then uses this error value to adjust its speed.

PID value is calculated using the error value and some special numbers called Kp, Ki and Kd. The robot uses these numbers to adjust its speed and stay on the line.

### Line-Loss Recovery

If the robot loses the line it will spin around until it finds it again. It does this by remembering the direction it was going and spinning in that direction.

### Bluetooth PID Tuning

You can adjust the robots settings using Bluetooth. You can send packets of data to the robot to change its Kp, Ki and Kd values. This allows you to tune the robots performance.

## PCB

The robots circuit board is designed using a program called KiCad. The board has all the components, including the ESP32, motor driver, voltage regulator and infrared sensors.

## Getting Started

To get started with the robot you need to:

1. Open the PID_Line_Follower_ESP32 code in the Arduino IDE
2. Install all the libraries
3. Select the board and port
4. Flash the code to the robot
5. Turn on the robot. Let it calibrate
6. Connect to the robot using Bluetooth. Send a special packet to start it
7. Adjust the robots settings until it is following the line smoothly

## Tuning Tips

- Start with Ki and Kd set to 0 and adjust Kp until the robot is following the line but oscillating
- Add Kd to reduce the oscillation
- Add a Ki if the robot is drifting off the line
- Use the multipliers to tune the robots performance without losing resolution over Bluetooth
- Remember to use the PID Line Follower. ESP32 to adjust the robots settings and keep it following the line smoothly. The PID Line Follower. ESP32 is a tool for tuning the robots performance.
