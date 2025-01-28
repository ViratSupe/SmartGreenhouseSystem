Smart Greenhouse System
This project is a Smart Greenhouse System built using an ESP32 microcontroller. It automates the monitoring and control of environmental conditions in a greenhouse to ensure optimal plant growth.

Features
Real-time Monitoring:
Soil Moisture Sensor
Light Intensity Sensor (LDR)
Temperature & Humidity (DHT11)
Automated Controls:
Water pump activation based on soil moisture.
LED lighting control based on ambient light levels.
LCD Display: Displays live sensor readings.
Web Interface:
View sensor data.
Manual control for water pump and LED.
Wi-Fi Connectivity: Access the system remotely via a local network.
Components Required
ESP32 microcontroller
Soil Moisture Sensor
LDR Sensor
DHT11 Temperature & Humidity Sensor
16x2 I2C LCD Display
2-channel Relay Module
Water Pump
LED Light
Jumper Wires
Power Supply
Circuit Connections
DHT11 Sensor: GPIO23
Soil Moisture Sensor: GPIO32
LDR Sensor: GPIO35
Water Pump Relay: GPIO26
LED Relay: GPIO27
I2C LCD Display: SDA to GPIO21, SCL to GPIO22
Installation and Setup
Hardware Setup:

Connect all components as per the circuit connections above.
Ensure the relays are connected to their respective devices (water pump and LED).
Software Setup:

Install the required libraries in the Arduino IDE:
LiquidCrystal_I2C
WiFi
WebServer
DHT
Configure your Wi-Fi credentials in the code:
cpp
Copy
Edit
**const char* ssid = "Your_SSID";
const char* password = "Your_PASSWORD";**
Upload the code to your ESP32.
Accessing the Web Interface:

Once the ESP32 is connected to Wi-Fi, note the IP address printed in the Serial Monitor.
Open a web browser and navigate to the IP address to access the control panel.
Usage
LCD Display: Displays real-time data for soil moisture, light intensity, temperature, and humidity.
Web Interface:
View sensor data updated every second.
Toggle the water pump and LED manually.
Automation:
The water pump turns on automatically if soil moisture falls below the threshold (40%).
The LED turns on automatically when ambient light is low (LDR < 50%).
Code Explanation
Sensor Data Reading: Reads soil moisture, light intensity, temperature, and humidity values.
Data Mapping: Sensor readings are mapped to a percentage scale (1–100).
Web Server: Hosts a webpage for monitoring and manual control.
LCD Update: Updates live sensor data on the 16x2 I2C LCD display.
Relay Control: Manages water pump and LED based on sensor data or web commands.
Screenshots
LCD Display
Displays live data such as:

Temperature: 25°C
Humidity: 60%
Soil Moisture: 45%
Light Intensity: 80%
Web Interface
Real-time gauges for sensor data.
Buttons to toggle water pump and LED.
Future Enhancements
Add more sensors like CO2 or pH.
Extend to control additional devices.
Implement cloud integration for remote access.
License
This project is open-source and available under the MIT License. Feel free to use and modify it as needed.
