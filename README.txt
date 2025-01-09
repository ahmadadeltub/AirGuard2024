# AirGuard: A Sustainable IoT-Driven System for Real-Time Environmental Monitoring and Fire Hazard Detection

## Overview
The **AirGuard System** is an IoT-enabled project designed for real-time environmental monitoring and fire hazard detection. It integrates sensors, actuators, and cloud platforms to provide a comprehensive safety solution. The system utilizes **Arduino MKR 1000** and **Raspberry Pi 4** to monitor air quality, detect harmful gases, and alert users about potential hazards through visual, auditory, and digital notifications.

This README file provides a guide to understand, set up, and run the project.

---

## Features
- **Real-Time Monitoring:** Tracks temperature, humidity, and harmful gas levels.
- **Fire Detection:** Alerts users when flames are detected.
- **Automation:** Controls fan and traffic light LEDs (Green, Yellow, Red) based on hazard levels.
- **IoT Dashboard:** Visualizes sensor data and allows remote control of the system via Arduino IoT Cloud.
- **Telegram Notifications:** Sends instant alerts to users about hazardous conditions.
- **Sustainability:** Energy-efficient design suitable for industrial, residential, and public applications.

---

## Hardware Requirements
| Component               | Description                                            |
|-------------------------|--------------------------------------------------------|
| Arduino MKR 1000 WiFi  | Microcontroller for sensor data acquisition.           |
| Raspberry Pi 4         | Processes data, controls actuators, and manages alerts.|
| DHT11 Sensor           | Measures temperature and humidity.                     |
| MQ135, MQ2, MQ7, etc.  | Gas sensors for air quality monitoring.                |
| Flame Sensor           | Detects fire or flame hazards.                         |
| Fan                    | Provides ventilation and hazard response.              |
| Traffic Light LEDs     | Visual alerts for hazard levels (Green, Yellow, Red).  |
| Power Supply           | 5V, 3A for Raspberry Pi and USB for Arduino.           |
| Jumper Wires           | Connect components to the microcontrollers.            |
| Enclosure (Optional)   | Protects hardware and organizes layout.                |

---

## Software Requirements
- **Arduino IDE** (for programming the MKR 1000)
- **Python 3** (for Raspberry Pi scripts)
- **Arduino IoT Cloud Dashboard**
- **Telegram Bot** for notifications
- Required Python Libraries:
  - `serial`
  - `RPi.GPIO`
  - `pygame`
  - `telepot`

---

## Installation and Setup

### 1. Arduino MKR 1000 Setup
1. Install the **Arduino IDE** and required board drivers for MKR 1000.
2. Connect the sensors (DHT11, MQ-series, Flame Sensor) to the MKR 1000.
3. Upload the provided `ArduinoCode.ino` file to the MKR 1000 using the Arduino IDE.
4. Ensure the MKR 1000 is connected to the Raspberry Pi via a USB cable.

### 2. Raspberry Pi Setup
1. Install Raspbian OS on the Raspberry Pi.
2. Install the required Python libraries:
   ```bash
   sudo apt update
   sudo apt install python3-pip
   pip3 install pyserial RPi.GPIO pygame telepot
   ```
3. Connect the fan and traffic light LEDs to the Raspberry Pi GPIO pins:
   - **Fan:** GPIO 16
   - **Green LED:** GPIO 24
   - **Yellow LED:** GPIO 23
   - **Red LED:** GPIO 25
4. Place the warning sound file (`warning.mp3`) in the appropriate directory (e.g., `/home/pi/airguard/`).

### 3. IoT Dashboard Configuration
1. Create an account on **Arduino IoT Cloud**.
2. Set up a new Thing and add variables for temperature, humidity, gas levels, and flame status.
3. Link the MKR 1000 to the IoT Cloud and connect the dashboard to visualize data.

### 4. Telegram Bot Setup
1. Create a Telegram bot using **BotFather** and obtain the bot token.
2. Add your chat ID and bot token to the Python script on the Raspberry Pi.

---

## Running the Project
1. **Start the Arduino MKR 1000:**
   - Ensure all sensors are connected.
   - Power the MKR 1000 via USB.
2. **Run the Python Script on Raspberry Pi:**
   ```bash
   python3 airguard.py
   ```
3. **Monitor the IoT Dashboard:**
   - Access the Arduino IoT Cloud to view real-time sensor data.
4. **Receive Alerts:**
   - Telegram notifications will be sent during hazardous conditions.
5. **System Response:**
   - Observe the fan, traffic light LEDs, and sound alerts responding to environmental changes.

---

## Code Structure

### Arduino Code (`ArduinoCode.ino`):
- **Functionality:**
  - Reads data from sensors and sends it to the Raspberry Pi via USB.
  - Updates IoT Cloud variables for dashboard monitoring.

### Raspberry Pi Python Code (`airguard.py`):
- **Functionality:**
  - Receives data from Arduino.
  - Processes sensor readings and triggers fan, LEDs, and sound alerts.
  - Sends Telegram notifications for critical conditions.
  - Logs data for performance evaluation.

---

## Example Telegram Alerts
- **Flame Detected:** "⚠️ Flame Detected! Take immediate action!"
- **High CO2 Levels:** "⚠️ High CO2 Levels Detected! Improve ventilation."
- **Gas Leak Warning:** "⚠️ Hazardous Gas Levels Detected!"

---

## Future Enhancements
1. **Mobile Application:** Develop an app for monitoring and controlling the system remotely.
2. **AI Integration:** Use predictive analytics for hazard forecasting.
3. **Cloud Storage:** Enable long-term data storage and analysis.
4. **Renewable Energy:** Incorporate solar panels to power the system sustainably.

---

## Contributors
- **Project Lead:** [Your Name]
- **Software Development:** [Your Name]
- **Hardware Integration:** [Your Name]

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---

## Contact
For questions or support, please contact: [y.qahtani1604@education.qa].


