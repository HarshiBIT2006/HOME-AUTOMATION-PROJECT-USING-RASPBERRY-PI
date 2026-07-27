# HOME-AUTOMATION-PROJECT-USING-RASPBERRY-PI
This project implements a Home Automation and Security System using Raspberry Pi 4 Model B
The system continuously monitors the home environment using multiple sensors and immediately alerts the user whenever an abnormal condition is detected.

The system includes:
1. Human Intrusion Detection using PIR and IR Sensors
2. LPG Gas Leakage Detection using MQ-2 Gas Sensor
3. Fire Detection using Flame Sensor
4. Temperature and Humidity Monitoring using DHT11 Sensor
5. LED and Buzzer Alarm System
6. Whenever any dangerous situation is detected, the Raspberry Pi activates an LED and buzzer while displaying warning messages on the terminal.

Objectives-
1. Detect unauthorized human entry.
2. Detect LPG gas leakage.
3. Detect fire or flame.
4. Monitor room temperature and humidity.
5. Alert the user immediately during emergencies.
6. Build a low-cost smart home safety system.

Features-
1. Real-time monitoring
2. Automatic alarm system
3. Low power consumption
4. Multiple sensor integration
5. Easy to install
6. Expandable for IoT applications
7. Raspberry Pi based automation
8. Continuous monitoring (24×7)

Components Required-
1. Component	Quantity
2. Raspberry Pi 4 Model B	
3. Micro SD Card (16GB or higher)	
4. Raspberry Pi Power Adapter	
5. PIR Motion Sensor	
6. IR Obstacle Sensor	
7. MQ-2 Gas Sensor	
8. Flame Sensor	
9. DHT11 Temperature & Humidity Sensor	
10. LED	
11. 220Ω Resistor	
12. Active Buzzer	
13. Breadboard	
14. Jumper Wires

Software Requirements-
1. Raspberry Pi OS
2. Python 3
3. Thonny IDE or VS Code
4. GPIO Zero Library
5. Adafruit DHT Library

Install libraries:
1. sudo apt update
2. sudo apt install python3-gpiozero
3. pip3 install adafruit-circuitpython-dht
4. sudo apt install libgpiod2

GPIO Connections-(ONLY DIGITAL PINS ARE USED FOR ALL SENSORS)
1. PIR Motion Sensor-PIN11 (ACTIVE HIGH)
3. VCC	3.3V- PIN1
4. GND- PIN6
5. IR Obstacle Sensor
6.  IR Pin	Raspberry Pi
VCC	3.3V
 GND	
OUT	GPIO27
7. MQ-2 Gas Sensor (Digital Output)
MQ2 Pin	Raspberry Pi
VCC	5V
GND
DO	GPIO22
8. Flame Sensor
9. Flame Pin	Raspberry Pi
VCC	3.3V
GND
DO	GPIO12
10. DHT11 Sensor
DHT11 Pin	Raspberry Pi
VCC	3.3V
DATA	GPIO4
GND
11. LED
LED Pin	Raspberry Pi
Anode (+)	GPIO23 (through 220Ω resistor)
Cathode (-)	GND
12. Buzzer
Buzzer Pin	Raspberry Pi
Positive (+)	GPIO24
Negative (-)	GND

Raspberry Pi GPIO Summary-
1. GPIO	Connected Device
2. GPIO4	DHT11
3. GPIO12	Flame Sensor
4. GPIO17	PIR Sensor
5. GPIO22	MQ-2 Gas Sensor
6. MGPIO23	LED
7. GPIO24	Buzzer
8. GPIO27	IR Sensor

Working Principle-
Step 1- The Raspberry Pi initializes all GPIO pins.
Step 2- PIR sensor continuously detects human movement.
If:
PIR = HIGH
AND IR = LOW
The system assumes an intruder has entered.
Message:
Intruder has entered!
Step 3- MQ-2 continuously checks LPG concentration.
If gas exceeds the threshold:
LPG Leakage Detected!
Alarm becomes active.
Step 4- Flame sensor continuously checks for fire.
If flame is detected:
Flame Detected!
Alarm activates immediately.
Step 5- DHT11 measures
Temperature
Humidity
Temperature is printed every second.
If
Temperature ≥ 35°C
System displays
High Temperature Detected!
Step 6- If any alarm condition is true:
LED ON
Buzzer ON
Otherwise:
LED OFF
Buzzer OFF

Code Logic-
The program continuously performs the following operations:
1. Read PIR sensor.
2. Read IR sensor.
3. Read MQ-2 sensor.
4. Read Flame sensor.
5. Read DHT11 temperature.
6. Read DHT11 humidity.
7. Check temperature threshold.
8. Activate alarm if any abnormal condition exists.
9. Repeat every second.

Expected Output-
1. Normal Operation
2. Home Automation System Started
3. Temperature: 29 °C
4. Humidity: 58 %
5. Intruder Detection
6. Intruder has entered!
7. LED ON
8. Buzzer ON
9. LPG Leakage
10. LPG Leakage Detected!
11. LED ON
12. Buzzer ON
13. Flame Detection
14. Flame Detected!
15. LED ON
16. Buzzer ON
17. High Temperature
18. Temperature: 38 °C
19. High Temperature Detected!
20. LED ON
21. Buzzer ON

Applications-
1. Smart Homes
2. Home Security
3. Fire Detection Systems
4. LPG Leakage Monitoring
5. Smart Apartments
6. Industrial Safety
7. Offices
8. Laboratories
9. Warehouses
10. Hostel Rooms

Advantages-
1. Low Cost
2. Easy Installation
3. Real-Time Monitoring
4. Fast Response
5. Automatic Alerts
6. Energy Efficient
7. Easy to Upgrade
8. Reliable Operation
9. Open Source Software
10. Suitable for IoT Integration

Limitations-
1. Requires continuous power supply.
2. MQ-2 sensor requires a warm-up period for accurate readings.
3. DHT11 has limited accuracy compared to advanced sensors.
4. No internet connectivity in the current implementation.
5. Alarm is local only (LED and buzzer).

Future Enhancements-
1. Send alerts via mobile app.
2. Email and SMS notifications.
3. Cloud data logging.
4. Camera integration for image capture.
5. Face recognition for authorized access.
6. Relay-based appliance control.
7. Voice control using Google Assistant or Alexa.
8. Mobile dashboard using MQTT or Blynk.
9. AI-based intrusion detection.
10. Integration with smart door locks.
