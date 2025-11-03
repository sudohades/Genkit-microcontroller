Monitoring DHT11 Sensor Project with ESP8266/ESP32 and Google Firestore

Want to learn how to connect physical devices to the cloud? This project is a perfect starting point! You will learn how to read data from a DHT11 sensor and send it to Google Firestore for real-time monitoring from anywhere. We provide two clear code examples for the ESP8266 and ESP32 platforms, complete with explanations to help you build your first IoT project.

This is an excellent basic project to get started with the Internet of Things (IoT), cloud integration, and sensor data visualization.

Main Features 🚀

Real-Time Data Logging: Sends temperature and humidity data to the cloud every 10 seconds.

Multi-Platform Support: Provides separate codes for NodeMCU ESP8266 and ESP32.

Scalable Cloud Database: Uses Google Firestore, a reliable NoSQL database for storing time-series data.

User Authentication: Secures data writing to the database using Firebase’s email/password authentication system.

Two Coding Approaches: Showcases two different scheduling methods:

Blocking (delay()) for simplicity on the ESP8266.

Non-Blocking (millis()) for efficiency on the ESP32.

Hardware Requirements 🔌

NodeMCU ESP8266 or ESP32 Dev Kit

DHT11 Temperature & Humidity Sensor

Jumper Wires

Micro USB Cable

Access to Wi-Fi network

Software & Libraries 💻

Arduino IDE

Board Managers:

esp8266 by the ESP8266 Community.

esp32 by Espressif Systems.

Arduino Libraries:

Firebase ESP Client by Mobizt (for Firebase communication).

DHT sensor library by Adafruit (for reading the DHT11 sensor).

Configuration
1. Firebase Project Setup

Before uploading the code, you need to set up a project in Firebase.

Create a Project:
Open Firebase Console
, click Add Project, and name your project (for example, “DHT11 Firestore”).

Enable Authentication:

In the left menu, go to Build > Authentication.

Click Get Started, select Email/Password as the sign-in method, and enable it.

Go to the Users tab and click Add user to create a new user account that your ESP will use.

Create Firestore Database:

Go to Build > Firestore Database.

Click Create Database and start in test mode.

Get Credentials:

Click the gear icon next to Project Overview and choose Project settings.

Under the General tab, copy the Web API Key and Project ID.

You’ll need these in your Arduino code.

2. Arduino Code Setup

Select the appropriate file for your board:

FirebaseESP8266V2DHT.ino for ESP8266.

FirebaseESP32V2DHT.ino for ESP32.

Open the file in Arduino IDE.

Fill in your credentials on the following lines:

// --- WIFI CREDENTIALS ---
#define WIFI_SSID "YOUR_WIFI_NAME"
#define WIFI_PASSWORD "YOUR_WIFI_PASSWORD"

// --- FIREBASE CREDENTIALS ---
#define API_KEY "YOUR_WEB_API_KEY"
#define FIREBASE_PROJECT_ID "YOUR_PROJECT_ID"

// --- USER CREDENTIALS ---
#define USER_EMAIL "YOUR_REGISTERED_EMAIL"
#define USER_PASSWORD "YOUR_PASSWORD"

Wiring Diagram

Connect the DHT11 sensor to your ESP board as follows. The data pin connects to D4 (GPIO 4).

DHT11 Pin	ESP8266 / ESP32 Pin
VCC / +	3V3
GND / -	GND
DATA / OUT	D4
How to Use

Ensure all Firebase and Arduino code setup steps are complete.

Assemble the hardware according to the wiring diagram above.

Connect the ESP board to your computer.

In Arduino IDE, select the correct Board and Port.

Click Upload to upload the code.

Open Serial Monitor and set the baud rate to 115200. You’ll see Wi-Fi connection logs and data posting status.

Open the Firebase Console, navigate to Firestore Database, and you’ll see temperature and humidity data appear and update every 10 seconds!

License

This project is licensed under the MIT License.
