# ESP32-CAM-Vehicle-Number-Plate-Recognition

ESP32-CAM Vehicle Number Plate Recognition
📌 Overview
This project captures a vehicle’s number plate using the ESP32-CAM, uploads the image via HTTPS to a cloud server (Circuit Digest), and displays the recognized number plate data on an OLED display.

🔧 Built with:

ESP32-CAM

SSD1306 OLED display (I2C)

Circuit Digest number plate recognition API

⚙ Features
✅ Capture image on button press
✅ Upload image securely to the server
✅ Display recognized plate on OLED
✅ Flashlight support for low-light capture
✅ Clean JSON parsing and user feedback

🧰 Components
Component	Notes
ESP32-CAM Module	Camera and WiFi microcontroller
SSD1306 OLED Display	Shows status and results
Push Button	Trigger image capture
Flashlight LED	Better visibility during capture

🛠 How it works (flow):
Waits for trigger button press.

Captures image using ESP32-CAM.

Uploads JPEG image to server using HTTPS POST.

Receives JSON response with:

"number_plate" → recognized text

"view_image" → link to uploaded image

Displays number plate text on OLED.

📦 Libraries Used
WiFi.h and WiFiClientSecure.h

esp_camera.h

Adafruit_GFX & Adafruit_SSD1306 (OLED)

Wire.h (I2C communication)

🧪 Setup & Configuration
Replace:

cpp
Copy
Edit
const char* ssid = "*****";
const char* password = "******";
String apiKey = "******";
String serverName = "www.circuitdigest.cloud";
String serverPath = "/readnumberplate";
with your actual WiFi credentials and API key.

Connect:

Pin	Function
GPIO 13	Trigger Button
GPIO 4	Flashlight
GPIO 14, 15	I2C SCL, SDA (OLED)

Confirm camera pins in camera_config_t match your ESP32-CAM board.

