This project demonstrates how to use the ESP32-CAM (AI Thinker) module to capture images and save them directly to a microSD card. 
The board takes a photo at regular intervals (default: every 5 seconds), names it sequentially, and stores it on the SD card.

🔧 Hardware Requirements
1. ESP32-CAM (AI Thinker board recommended)
2. MicroSD card (formatted FAT32)
3. Micro USB programmer (FTDI / CP2102 / CH340)
4. Jumper wires (for flashing and powering)
5. External 5V power source (recommended for stability)[Laptop/Computer]

🚀 Setup Instructions
1. Install Arduino IDE (or PlatformIO).
2. Install ESP32 Core in Arduino IDE:
  Open File > Preferences → Add this URL to “Additional Board URLs”: // https://dl.espressif.com/dl/package_esp32_index.json //
  Then Tools > Board > Boards Manager → search ESP32 → install.
3. Select board:
  AI Thinker ESP32-CAM
  Partition Scheme: Huge App (3MB No OTA)
4. Connect ESP32-CAM to FTDI adapter:
  U0T ↔ TX, U0R ↔ RX, GND ↔ GND, 5V ↔ 5V
  Short IO0 to GND while uploading.
5. Upload the code. Source: {photo.ino} Includes: {camera_pins.h}
6. Insert formatted microSD card.
7. Reset the board and open Serial Monitor (115200 baud).

🖼️ Usage
Every 5 seconds, a photo will be captured and saved
...
Images are stored on the SD card.
You can change the delay in loop().

✅ Features
Auto-detects PSRAM for higher resolution.
Saves photos in JPEG format.
SD card write protection & error handling.
Image flip & mirror correction included.

🛠️ Future Improvements
 Timestamp-based filenames (e.g., 2025-08-24_12-30-01.jpg)
 WiFi upload (FTP/HTTP/MQTT)
 Web interface for live streaming
 Motion detection (PIR sensor or image diff)
 Deep sleep for battery-powered timelapse.
 
📜 License
This project is licensed under the MIT License – see LICENSE for details.

🙌 Acknowledgements
Espressif ESP32 Camera Driver
AI Thinker ESP32-CAM module
