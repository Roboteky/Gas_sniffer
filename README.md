# 🛑 Gas_Sniffer 

A real-time gas monitoring and alert system using MQ9 and MQ2 sensors, designed to detect harmful gases and alert authorities or users via WhatsApp, SMS, and a visual dashboard. The system integrates safety features like a fan (extractor), LED indicators, GSM fallback for remote connectivity, and real-time location tracking.

---

## 🚀 Features

- **Dual Gas Detection**: Uses MQ9 and MQ2 sensors to detect various gases (Carbon Monoxide, Methane, Propane, etc.).
- **Temperature Monitoring**: Integrated temperature sensor to provide environmental data.
- **Live Dashboard**: Web-based dashboard with user login (Account & Admin) to monitor real-time sensor readings and alerts.
- **Multi-Channel Alerts**: Sends notifications via:
  - **WhatsApp**
  - **SMS (Twilio API)**  
  (Up to **3 predefined numbers** when hazardous levels are detected.)
- **Display Panel**:
  - Real-time gas and temperature readings.
  - Status of notifications pushed.
- **LED Indicators**: Show safe, warning, and danger states.
- **GSM Connectivity**:
  - Automatically switches to GSM mode if Wi-Fi is unavailable.
  - Sends data and location to authorities via mobile network.
- **Fan Activation**: Turns on an extractor fan when high gas levels are detected.

---

## 📦 Hardware Components

- MQ2 Gas Sensor  
- MQ9 Gas Sensor  
- DHT11 / DHT22 Temperature Sensor  
- SIM800L GSM Module / GPS + GSM Module  
- OLED / LCD Display  
- RGB or Multi-color LEDs  
- 5V Relay & Fan (Extractor)  
- NodeMCU / ESP32 / Arduino + GSM  
- Power Source and supply [ battery powered ]

---

## 🔧 System Workflow

1. Sensors continuously read gas and temperature levels.
2. Display shows real-time values.
3. If threshold is breached:
   - Fan turns on.
   - LED switches to red.
   - Location is fetched.
   - Notification is sent via Twilio (SMS/WhatsApp).
   - Data is logged on the dashboard.
4. If Wi-Fi is lost:
   - System uses GSM to send data directly.

## 📲 Notification System

- **Twilio API**:
  - Predefined max of 3 phone numbers.
  - Automatically pushes SMS/WhatsApp messages when dangerous levels are recorded.
- Notification also appears on:
  - Web Dashboard
  - Local Display

## 📡 Message Payload Format

Messages sent to the authorities include:

The message payload [  →  {{ location }}, {{ temperature recorded }}, {{ Gas detected }} & {{ Combustible or Non-combustible }}.  ] —  Message to Authority.

## 🧪 Testing & Deployment

- Simulate gas levels using lighter near sensor (carefully).
- Test Wi-Fi disconnect to confirm GSM fallback.
- Monitor Twilio logs for message delivery status.
- Ensure fan and LEDs operate under correct thresholds.


## 📞 Emergency Contact Setup

In `alert_sender.py`, define:

```python
EMERGENCY_NUMBERS = [
    "+2547XXXXXXX1",
    "+2547XXXXXXX2",
    "+2547XXXXXXX3"
]

📞 Emergency Contact Setup
 MIT License – Free to use with attribution.

🤝 Contributors
Developed by: [ QUANT ELECTRICS ]
Contact: [ kirumba693@gmail.com ]