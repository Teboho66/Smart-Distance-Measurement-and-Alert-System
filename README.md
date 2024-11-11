Project Report: IoT Distance Alert System with Enhanced Features

Submitted by: Teboho Mokoni
              Lindiwe Magagula
              Sinokholo Singazi
              Matthew Shaw
Subject: IOT

#1. Introduction
The IoT Distance Alert System is an Arduino-based project that combines multiple sensors and output components to create a responsive, real-time alert system. This system continuously measures distance using an ultrasonic sensor and responds visually, audibly, and via Bluetooth and Wi-Fi modules to provide alerts based on distance thresholds. It is designed to enhance safety and monitoring applications, providing live feedback locally and remotely.

#2. Objective
The main goal of this project is to develop a fully functional IoT system that measures the distance to an object and triggers alerts based on proximity. The project can be expanded to log data, display distance on an LCD screen, and provide remote access to monitor and manage alerts using Bluetooth and Wi-Fi capabilities.

#3. System Design
The IoT Distance Alert System incorporates multiple sensors and output devices:

Ultrasonic Sensor: Measures distance to nearby objects.
LEDs (Red, Blue, Green): Provides visual alerts based on distance range.
Buzzer: Delivers audio alerts with varying intensities for different distances.
LCD Display: Shows real-time distance data and current alert mode.
SD Card Module: Logs distance and time data for tracking.
RTC Module: Tracks time for accurate data logging.
IR Remote and Bluetooth: Controls the system and provides wireless communication for mobile monitoring.
ESP8266 Module: Hosts a local web server, allowing remote access to the data.
4. Components
Arduino UNO: Main microcontroller for managing sensors and outputs.
Ultrasonic Sensor (HC-SR04): Measures distance using sonar.
LEDs (Red, Blue, Green): Visual indicators of proximity.
Buzzer: Audio alert for different proximity levels.
LCD Display (I2C): Displays distance, mode, and alert status.
SD Card Module: Logs data over time.
RTC Module (DS3231): Provides time for data logging.
IR Remote Control: Enables user control over alert modes.
Bluetooth Module (HC-05): Transmits data to mobile devices.
ESP8266 Wi-Fi Module: Sets up a web server for remote monitoring.
5. System Operation and Functionality
5.1 Distance Measurement
The ultrasonic sensor emits ultrasonic waves, and by measuring the time taken for the echo to return, the system calculates the distance. Based on the distance, it triggers different alerts:

Red LED: Distance < 10 cm
Blue LED: Distance between 10 cm and 20 cm
Green LED: Distance > 20 cm
5.2 Alert Modes
Using the IR remote or Bluetooth, users can set the system to different alert modes:

Normal Mode: All indicators (LEDs, buzzer, and LCD) are active.
Silent Mode: Only LEDs and LCD display are active; the buzzer is muted.
Alert Only Mode: Only the buzzer activates at close proximity, ignoring LEDs.
5.3 Real-Time Display
The LCD displays the measured distance and the current alert mode, providing real-time feedback to the user.

5.4 Data Logging
The SD card logs data in a CSV format, recording:

Distance in cm
Alert mode
Timestamp from the RTC module
This provides a historical view of distance measurements over time.

5.5 Remote Monitoring and Control
Bluetooth: Allows the system to transmit data to a mobile application or receive commands to change alert modes.
ESP8266 Web Server: Hosts a local web interface accessible on mobile or desktop browsers. This interface displays the distance data and updates every second, allowing real-time remote monitoring.
6. Code Overview
The code integrates sensor readings, output management, remote control, and data logging. Key functions include:

Setup Function: Initializes sensors, SD card, RTC, LCD, and communication modules.
Loop Function: Continuously measures distance and updates outputs based on the current mode.
Alert Mode Control: Manages input from the IR remote and Bluetooth to switch between modes.
Data Logging: Saves distance and mode data to the SD card with timestamps.
Web Server Code (ESP8266): Provides an HTML interface that displays distance data and refreshes dynamically.
7. Project Enhancements
Additional features implemented include:

Multiple Modes: Controlled via IR remote and Bluetooth, allowing user customization.
Audio Alerts: Frequency of the buzzer varies with distance.
Data Logging: Logs data on an SD card with timestamps.
Remote Monitoring: Hosts a local web server for real-time data viewing and control.
8. Hardware Setup
Ultrasonic Sensor:

VCC to 5V, GND to GND, TRIG to digital pin 12, ECHO to digital pin 11.
LEDs (Red, Blue, Green):

Connected to digital pins 6, 7, and 8, respectively, with resistors.
Buzzer:

Positive to digital pin 4, GND to GND.
LCD Display (I2C):

VCC to 5V, GND to GND, SDA to A4, SCL to A5.
SD Card Module:

VCC to 5V, GND to GND, MOSI to pin 11, MISO to pin 12, SCK to pin 13, CS to pin 10.
RTC Module (DS3231):

VCC to 5V, GND to GND, SDA to A4 (shared with LCD), SCL to A5 (shared with LCD).
Bluetooth Module (HC-05):

VCC to 5V, GND to GND, TX to pin 9, RX to pin 8 (through voltage divider).
ESP8266 NodeMCU:

VCC to 3.3V, GND to GND (common with Arduino), D6 (RX) to Arduino TX (through voltage divider), D5 (TX) to Arduino RX.
9. Troubleshooting Tips
Bluetooth Connection Issues: Ensure the baud rate is set correctly. HC-05 default is 9600.
SD Card Issues: Format the SD card as FAT32.
ESP8266 Wi-Fi Issues: Confirm Wi-Fi credentials are correct.
Power Supply: Use a stable power supply as sensor noise can interfere with performance.
10. Future Enhancements
Bluetooth App Development: Create a mobile app to receive data and manage modes.
Wi-Fi Data Logging: Send data to an online database for real-time access from anywhere.
Battery Integration: Add a rechargeable battery for portability.
Multiple Sensors: Use additional sensors for broader coverage in larger spaces.
11. Conclusion
The IoT Distance Alert System project is a practical implementation of IoT technologies for monitoring and alerting based on distance measurements. With multiple alert modes, remote monitoring, and data logging, the system can be used in various applications, including safety alerts, object detection, and environmental monitoring. This project showcases the potential of IoT for real-time, data-driven solutions and can be further expanded for advanced applications.
