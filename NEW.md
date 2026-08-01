# 🛰️ MESHBULLET

PoE and non-PoE Meshtastic node supporting OTA over Ethernet, utilizing custom ABS parts sponsored by [Justway Manufacturing](https://justway.com).

## 📌 Features

*   **Core:** Raspberry Pi Pico RP2350 (or similar PoE EVB).
*   **Connectivity:** SPI Wiznet Ethernet.
*   **RF:** SX1262 / LR1121 / LR2011 modules.
*   **Enclosure:** Custom 3D-printed (FDM ABS).

---

## 🚀 Project Sponsor: Justway 3D Printing

Enclosures and structural parts are proudly printed by [Justway](https://justway.com), utilizing FDM with high-durability ABS for rugged deployment. Upload the project `.step`/`.stl` files directly for instant quoting and rapid prototyping.

---

## 🛠️ General Instructions

1.  **PCB:** Fabricate boards using provided Gerbers.
2.  **3D Print:** Print all enclosure components.
3.  **Assembly:** Solder components, use B-7000 glue to secure the RJ45 port and antenna, and align the core into the ABS housing.
4.  **Firmware:** Flash with supported Meshtastic firmware.

---

## 🔌 Hardware Variants & BOM

*   **Non-PoE:** Pico RP2350 + Wiz850io (W5500) + Seeed WIO-SX1262/LR1121.
*   **PoE:** Wiznet W6100/W5100S-EVB-Pico2 + WIO/Waveshare LoRa modules.
*   *See full repository for solder sequence instructions.*

---

## 📸 Media & Component Links

*   **Renderings:** See `[images/]` in repository for assembly views and PCB layouts.
*   **Components:** Components such as Wiznet modules and Seeed/Waveshare LoRa modules are linked in the main [README.md](https://github.com).

---

## 🤝 Credits

*   **[MESHTASTIC Project](https://github.com)**
*   **Carlos Valdes** (Ethernet stack/OTA contributions)
*   **Justway** (3D printing support)

---

## ⚠ Disclaimer

Use of PCB GERBER and 3D files is at your own risk.
