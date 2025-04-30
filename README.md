# ISAC Beacon (Upgraded Version)

This project is a modern, enhanced version of the original ISAC Beacon, designed to provide both short-range Bluetooth connectivity and long-range LoRa mesh communication using Meshtastic. It also integrates environmental sensors, NeoPixel visual feedback, and audio playback in a modular, solder-free design for accessibility.

---

## 📦 Features

- **Bluetooth Low Energy (BLE)** for real-time communication with smartphones
- **LoRa (Meshtastic)** support for encrypted long-range messaging between beacons
- **Environmental Sensing**: UV, temperature, humidity, pressure, light, and motion
- **Audio feedback** via DFPlayer Mini and speaker
- **Visual feedback** with NeoPixel ring
- **Designed to be accessible with plug-and-play JST and Qwiic connectors**

---

## 🧠 Hardware Used

### Microcontrollers
- [Adafruit Feather nRF52840 Express (u.FL version)](https://www.adafruit.com/product/4062)
- [TTGO T-Beam v1.1 / v1.2 (LoRa + GPS)](https://www.banggood.com/LILYGO-TTGO-T-Beam-v1_1-ESP32-LoRa-433-or-868-or-915Mhz-WiFi-GPS-NEO-6M-18650-WiFi-bluetooth-Board-Module-p-1609523.html)

### Sensors (Qwiic/STEMMA compatible)
- [VEML6075 UV Sensor](https://www.adafruit.com/product/3964)
- [BME280 Temperature, Humidity, and Pressure Sensor](https://www.adafruit.com/product/2652)
- [BH1750 Ambient Light Sensor](https://www.adafruit.com/product/4681)
- [ADXL345 Accelerometer](https://www.adafruit.com/product/1231) *(optional)*

### Audio & Visual
- [DFPlayer Mini MP3 Module](https://www.dfrobot.com/product-1121.html)
- [3W 8Ω Speaker w/ JST Connector](https://www.amazon.com/CQRobot-JST-PH2-0-Interface-Electronic-Projects/dp/B0738NLFTG)
- [NeoPixel 16x RGB LED Ring](https://www.adafruit.com/product/1463)

### Power
- [3.7V LiPo Battery (1200–2000mAh)](https://www.adafruit.com/product/2011)
- [USB-C Cable](https://www.adafruit.com/product/4474)

### Connectors & Cables
- [Qwiic / STEMMA QT Cable](https://www.adafruit.com/product/4210)
- [JST-PH 2-Pin Connector / Cable](https://www.amazon.com/jst-ph/s?k=jst+ph)

### Antenna System
- [u.FL to SMA Adapter Cable](https://www.adafruit.com/product/851)
- [2.4GHz SMA BLE Antenna](https://www.adafruit.com/product/944)

---

## 🔧 Software Stack

- Feather nRF52840: Arduino BLE + UART communication
- T-Beam: Meshtastic firmware (flashed via [Meshtastic Flasher](https://flasher.meshtastic.org/))
- Sensor code and BLE GATT server on Feather (Arduino sketch in `/firmware` directory)

---

## 📐 Architecture

```
[ Sensors ]
     ↓
[ Feather nRF52840 ] ↔↔↔ BLE ↔↔↔ [ Phone ]
     ↓
 [ Serial/UART ]
     ↓
[ TTGO T-Beam (LoRa) ] ↔↔↔ Meshtastic Mesh Network
```

---

## 🔋 Powering the System

- All components powered from a 3.7V LiPo battery
- USB-C on the Feather can charge and program the device
- Shared power to T-Beam via JST splitter or powered separately

---

## 📲 Coming Soon

- Arduino code for Feather BLE and sensor integration
- Wiring diagrams for JST/Qwiic connections
- Printable plug-and-play user setup sheet

---

## 🧩 License

Open hardware and firmware under MIT license. Feel free to fork, remix, and improve.

---

## 🙏 Acknowledgments

Inspired by the original ISAC Beacon project by WedgeTheJedi, with adaptations for accessibility, expandability, and real-world networking.
