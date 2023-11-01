# IOT
SMART WATER FOUNTAIN
PHASE 1:
https://github.com/SwarnaUmasankar/IOT/files/12843981/smartwaterfountain-phase1.pdf

PHASE 2:
INNOVATION:

Components:

Microcontroller:

Arduino or Raspberry Pi for controlling the system.

Sensors:

Ultrasonic sensor, water level sensor for detecting water levels

and user presence.

Actuators:

Water pump, relays for controlling the flow of water.

Wi-Fi Module:

ESP8266 or ESP32 for IoT connectivity.

Indicators:

LEDs, buzzers for indicating water status or system alerts.

Power Supply:

To power the microcontroller and components.
Software:

Arduino IDE:

Programming the microcontroller to read sensor data and

control actuators.

IoT Platform:

ThingSpeak, Blynk, or AWS IoT Core for storing data and

enabling remote monitoring.

MQTT Protocol:

Lightweight messaging protocol for IoT communication.

Data Visualization:

Grafana, Google Charts for real-time visualization.

Mobile App Development (Optional):

Android Studio (for Android apps), Xcode (for iOS apps).

Methods:

Sensor Data Collection:

Use ultrasonic and water level sensors to gather data on water

levels and user presence.

Data Processing:
Process sensor data on the microcontroller to control the

water pump based on readings.

IoT Connectivity:

Integrate Wi-Fi modules for internet connectivity.

Use MQTT protocol for communication between the

microcontroller and IoT platform.

Cloud-Based IoT Platform:

Choose an IoT platform for data storage and remote

monitoring.

Configure the platform to receive and display real-time sensor

data.

Data Visualization:

Utilize Grafana or Google Charts to create visual

representations of sensor data.

User Interaction (Optional):

Develop a mobile app for user control and monitoring.

Alerts and Notifications:

Implement alerts (email, SMS, or app notifications) for

critical events like low water levels.

Testing and Calibration:

Test sensors, actuators, and IoT connectivity thoroughly.

Calibrate sensors for accuracy and fine-tune system parameters.

Documentation:

Document the project comprehensively, including circuit

diagrams, code explanations, and setup instructions.

Maintenance and Support:

Provide guidelines for regular maintenance and

troubleshooting.

Establish customer support channels for user assistance.








SMART WATER FOUNTAIN – PHASE III

INTRODUCTION

In this project, we have created a Smart Water Fountain system that can be controlled remotely 

via a web interface. The system includes components such as NodeMCU ESP8266, Water 

Pump, Relay Module, and Ultrasonic Sensor (HC-SR04). The simulation was done using the 

Wokwi simulator, allowing us to test the functionality of the system virtually.

COMPONENTS USED

1. NodeMCU ESP8266: Microcontroller board.

2. Water Pump: Used to pump water from a container to the fountain.

3. Relay Module: Controls the water pump.

4. Ultrasonic Sensor (HC-SR04): Detects water level in the fountain.

5. Wokwi Virtual Components: Virtual elements used for creating the web interface and 

simulation.

SIMULATION SETUP

1. Wokwi Account: Created a Wokwi account to access the simulation platform.

2. Circuit Configuration: Set up the circuit in the Wokwi Circuit Editor, connecting NodeMCU 

ESP8266, Water Pump, Relay Module, and Ultrasonic Sensor. Virtual components like Button 

and Range were added for the web interface.

CIRCUIT CONNECTIONS (SIMPLIFIED)

1. NodeMCU ESP8266:

 - Connected to Relay Module (Control Pin)

 - Connected to Ultrasonic Sensor (Trigger and Echo Pins)
2. Relay Module:

 - Controls the Water Pump

3. Ultrasonic Sensor (HC-SR04):

 - VCC to 5V

 - GND to GND

 - Trig to NodeMCU GPIO (e.g., D2)

 - Echo to NodeMCU GPIO (e.g., D3)

4. Button (Virtual Component):

 - Connected to NodeMCU GPIO (e.g., D4)

5. Range (Virtual Component):

 - Connected to NodeMCU GPIO (e.g., D5)

ARDUINO CODE

The Arduino code was developed to control the water pump based on user input from the web 

interface and monitor the water level using the Ultrasonic Sensor.

#include <ESP8266WiFi.h>

#include <WiFiClient.h>

#include <Ultrasonic.h>

Const char* ssid = “YourWiFiSSID”;

Const char* password = “YourWiFiPassword”;

Const int trigPin = D2; // Trigger pin of Ultrasonic Sensor

Const int echoPin = D3; // Echo pin of Ultrasonic Sensor

Const int relayPin = D1; // Relay module control pin

Ultrasonic ultrasonic(trigPin, echoPin);

WiFiServer server(80);
Void setup() {

pinMode(relayPin, OUTPUT); 

digitalWrite(relayPin, LOW);

Serial.begin(115200);

WiFi.begin(ssid, password);

While (WiFi.status() != WL_CONNECTED) {

 Delay(1000);

 Serial.println(“Connecting to WiFi...”);

 }

Server.begin();

}

Void loop() {

WiFiClient client = server.available();

If (client) {

 String request = client.readStringUntil(‘\r’);

 If (request.indexOf(“/on”) != -1) {

 digitalWrite(relayPin, HIGH); // Turn the pump on

 delay(2000); // Run the pump for 2 seconds

 digitalWrite(relayPin, LOW); // Turn the pump off

 }

 Client.flush();

 }

 // Check water level

 Float distance = ultrasonic.read();

 If (distance < 10) {

 // Water is low, update the web interface

 // You can send an HTML response to the client here

 }


SIMULATION AND TESTING

1. Code Implementation: Implemented the Arduino code to control the water pump and monitor 

water level.

2. Simulation: Clicked the "Simulate" button in Wokwi to start the simulation.

3. Testing: Interacted with the virtual components in the simulation to test the system's 

functionality.

CONCLUSION

The Smart Water Fountain system simulation was successfully carried out using the Wokwi 

simulator. The system demonstrated remote control capabilities and real-time monitoring of 

the water level. This simulation provides a basis for further development and implementation 

in real-world IoT projects.

SMART WATER FOUNTAIN-PHASE III:

1. Introduction

In this technology project, we have developed a Smart Water Fountain Control System using MIT 

App Inventor. The system allows users to remotely control a water fountain, monitor its status (Idle 

or Active), and start/stop the fountain as desired.

2. Project Objectives

The primary objectives of the project include:

- Remote Control: Enable users to control the water fountain remotely.

- Status Monitoring: Display the current status of the fountain (Idle or Active).

- User Interaction: Provide intuitive buttons for starting and stopping the fountain.

3. Technology Stack

- MIT App Inventor: Used for designing and implementing the mobile application.

- Web Development Technologies: Utilized for potential backend communication (if applicable).

- Smart Devices:The app communicates with smart devices controlling the water fountain.

4. App Features

The Smart Water Fountain Control App developed using MIT App Inventor includes the following 

features:

- Status Display: Shows the current status of the water fountain (Idle or Active).

- Start Button: Initiates the fountain, changing the status to Active.

-Stop Button: Halts the fountain, changing the status to Idle.
5. Implementation Details

5.1 User Interface Design

The app interface consists of:

- A label displaying the current status ("Idle" or "Active").

- Start and Stop buttons for controlling the fountain.

5.2 App Logic and Functionality

- Initialization: Upon app startup, the initial status is set to "Idle."

- Start Button Click Event: When the Start button is clicked, the status changes to "Active."

- Stop Button Click Event: When the Stop button is clicked, the status changes to "Idle."

6. Future Enhancements

While the current implementation provides basic functionality, the project can be enhanced further 

with the following features:

- User Authentication: Implement user accounts and authentication for secure access.

- Real-time Data: Integrate sensors to gather real-time data (e.g., water level) for more advanced 

control.

- Historical Data: Store and display historical fountain usage data.

- Mobile Alerts: Send notifications/alerts to users based on fountain activity.

7. Conclusion

The Smart Water Fountain Control System developed using MIT App Inventor successfully achieves 

the project objectives. It provides users with an intuitive interface to control and monitor the water 

fountain remotely.
