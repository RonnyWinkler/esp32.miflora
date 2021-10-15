# esp32.miflora
MiFlora adapter for ESP32 (MiFlora->BT->ESP32->Wifi->MQTT)

Thid ESP32 code is based on: https://github.com/sidddy/flora/
Sidddy made a nice manual, too :-)

A manual (german) for ESP configuration and installing the code into the ESP you can find here:
http://chrigi.me/wordpress/mi-flora-gateway/

Additions to original version:
- Connect/Disconnect to Wifi/MQTT
- Reconnect MQTT for every sensor to prevent timeouts
- using retained topics (last value keeps stored in MQTT broker)

Short description:
With his app, you can read the data from your MiFlora sensors via Bluetooth and send it via Wifi to your MQTT Broker.
Follow these steps:
- Install Arduino IDE
- Connect the Board via USB
- Open the menu in Arduino IDE: File> Preferences
- Add path https://dl.espressif.com/dl/package_esp32_index.json to "Additional Board Manager URLs"
- Select your Board: ESP32 Dev Module
- Select partition zize: "Tools -> Partition Scheme -> No OTA"
- Download "flora.ino" and "config.h.example" into a local folder
- rename "config.h.example" to "config.h"
- Create a new Arduino project and open the folder 
- edit the file "config.h". Set your data (Wifi, MQTT, Bluetooth MAC addresses...)
- Upload the program to ESP
- Restart ESP if it's not started automatically
- Check the Console output (Tools -> Serial monitor). Set "Baud" to 115200.
- Check your MQTT Broker using MQTT Explorer app.