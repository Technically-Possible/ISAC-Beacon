# ISAC Beacon (Upgraded Version)

This project is a modern, enhanced version of the original ISAC Beacon, designed to provide both short-range Bluetooth connectivity and long-range LoRa mesh communication using Meshtastic. It integrates advanced environmental sensors, NeoPixel visual feedback, and audio playback in a modular, solder-free design for accessibility and expandability.

---

## 📦 Features

- **Bluetooth Low Energy (BLE)** for real-time communication with smartphones.
- **LoRa (Meshtastic)** support for encrypted long-range messaging and location sharing.
- **Environmental Sensing**:
  - **Full-spectrum UV (A, B, C)** detection.
  - Ambient light level.
  - Temperature, humidity, and CO₂ concentration.
  - Air quality / particulate matter (PM1.0, PM2.5, PM10).
- **Audio feedback** via plug-and-play STEMMA QT speaker.
- **Visual feedback** with NeoPixel ring.
- **Accessible, solder-free design** using Qwiic/STEMMA QT connectors for sensors and audio.

---

## 🧠 Hardware Used

### Microcontrollers & Communication
- [Adafruit ESP32 Feather V2 w.FL Antenna - 8MB Flash + 2 MB PSRAM - STEMMA QT](https://www.adafruit.com/product/5438) – BLE, Wi-Fi, STEMMA QT/Qwiic ready.
- [TTGO T-Beam v1.1 / v1.2](https://www.banggood.com/LILYGO-TTGO-T-Beam-v1_1-ESP32-LoRa-433-or-868-or-915Mhz-WiFi-GPS-NEO-6M-18650-WiFi-bluetooth-Board-Module-p-1609523.html) – LoRa mesh communication with GPS, running Meshtastic firmware.

### Sensors (All Qwiic/STEMMA QT)
- [SparkFun Spectral UV Sensor - AS7331](https://www.sparkfun.com/products/19243) – Full-spectrum UV (A/B/C).
- [Adafruit BH1750 Light Sensor](https://www.adafruit.com/product/4681) – Ambient light.
- [Adafruit SCD-40 CO₂ Sensor](https://www.adafruit.com/product/5187) – CO₂, temperature, humidity.
- [Adafruit PMSA003I Air Quality Sensor](https://www.adafruit.com/product/4632) – Air quality particulate sensing (PM1.0/PM2.5/PM10).

**I²C Multiplexer (optional)**:
- [Adafruit PCA9548 8-Channel STEMMA QT / Qwiic Multiplexer](https://www.adafruit.com/product/5626) – To avoid address conflicts if needed.

### Audio & Visual
- [Adafruit STEMMA Speaker with built-in amplifier](https://www.adafruit.com/product/3885) (Plug-and-play JST PH 2mm connection).
- [Adafruit NeoPixel 16x RGB LED Ring](https://www.adafruit.com/product/1463).

### User Inputs
- Two tactile push buttons for user interaction.

### Power
- [3.7V LiPo Battery (1200–2000mAh)](https://www.adafruit.com/product/2011).
- [USB-C Cable](https://www.adafruit.com/product/4474).

### Cabling
- [STEMMA QT / Qwiic JST SH 4-Pin Cables](https://www.adafruit.com/product/4399) for sensor daisy-chaining.

---

## 📐 System Architecture

```plaintext
[ UV | Light | CO₂ | Air Quality ]
             ↓
 [ Feather ESP32 V2 ]
         ↙    ↓     ↘
  BLE ↔ Phone    NeoPixel   Speaker
             ↓
   Serial UART → TTGO T-Beam → LoRa Mesh
