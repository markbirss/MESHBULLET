# 🛰️ MESHBULLET

PoE and non-PoE Meshtastic version node featuring dual-variant hardware pathways.

---

## 📌 Features
* **Core:** Powered by the Raspberry Pi Pico RP2350 microcontroller.
* **Connectivity:** High-performance SPI Wiznet Ethernet.
* **RF Engine:** Flexible SPI LoRa radio module support (SX1262 / LR1121 / LR2011).
* **Enclosure:** Compact, custom 3D-printable enclosure system.

---

## 🛠️ General Instructions

### Prerequisites
1. **PCB Fabrication:** Submit the provided PCB Gerber files to a manufacturer (e.g., [JLCPCB](https://jlcpcb.com/RGE) — 5 pieces minimum).
2. **3D Printing:** Print all required enclosure components.
3. **Firmware:** Flash the board with the firmware (Note: This specific DIY variant firmware is pending release/merge).

### Assembly Steps
* **RJ45 Cap:** Glue the RJ45 end securely into the RJ45 LAN Cap using B-7000 glue. Ensure it is aligned at a precise 90-degree angle. Allow **2 days** to fully cure.
* **RF Assembly:** Assemble the SMA connectors and uFl pigtails, then glue the matching structural parts together.

---

## 🔌 Hardware Variants & Bill of Materials (BOM)

### 1. Non-PoE Version
* **Core Board:** Raspberry Pi Pico RP2350
* **Ethernet:** Wiz850io (W5500)
* **LoRa Options:** Seeed WIO-SX1262 or WIO-LR1121 only *(Note: WS-LR1121/WS-LR2021 footprints are unavailable as they overlap with the W5500 Wiz850io footprint).*
* **Hardware & Consumables:** MESHBULLET Non-PoE PCB, 2.54mm pitch headers, B-7000 Glue.
* **Solder Sequence:**
  1. Solder the LoRa Module onto the PCB.
  2. Solder the Wiz850io module onto the PCB.
  3. Insert the pin headers into the PCB, seat the Pico onto the headers to ensure perfect alignment, solder the headers to the Pico, and finally solder them to the PCB.

### 2. PoE (Power over Ethernet) Version
* **Core Board:** Wiznet W6100-EVB-Pico2 or W5100S-EVB-Pico2
* **LoRa Options:** Seeed WIO-SX1262 / WIO-LR1121 or Waveshare WS-LR1121 / WS-LR2021 *(shared universal footprint).*
* **Hardware & Consumables:** MESHBULLET PoE PCB, 2.54mm pitch headers, B-7000 Glue.
* **Solder Sequence:**
  1. Solder the LoRa Module onto the PCB.
  2. Solder the Wiznet PoE module into the Wiznet EVB, leaving a tiny air gap between the Wiznet EVB and the Wiznet PoE board.
  3. Insert headers into the PCB, seat the Wiznet EVB assembly to ensure alignment, solder to the EVB, and then solder to the PCB.

---

## 📸 Media Gallery

### Hardware Overview
<img width="100%" alt="MESHBULLET Hardware Architecture" src="https://github.com/user-attachments/assets/08f2fe31-11b9-4ec4-84bb-42252d97b3c5" />

### Non-PoE Build (Wiz850io + WIO-SX1262)
<p>
  <img width="49%" alt="Non-PoE Front View" src="https://github.com/user-attachments/assets/a23e4a62-59ba-4bb9-b5eb-09c8e8e9c086" />
  <img width="49%" alt="Non-PoE Back View" src="https://github.com/user-attachments/assets/f7f75654-1eed-4edd-8765-8d5831359eb6" />
</p>

### PoE Build (W6100 + Waveshare LR2021) & Enclosure Testing
<p>
  <img width="49%" alt="PoE Assembly View" src="https://github.com/user-attachments/assets/65516aeb-60a5-4157-99f4-2df2e8e74674" />
  <img width="49%" alt="DIY 3D Print Case Fitting" src="https://github.com/user-attachments/assets/7a0d901a-5b20-48ad-a1c4-46352514423e" />
</p>

### Components & Render References
<p>
  <img width="32%" alt="RPi Pico 2" src="https://github.com/user-attachments/assets/06482550-a9e0-4326-8c30-ac8459f36bcd" />
  <img width="32%" alt="W5500-MINI Layout" src="https://github.com/user-attachments/assets/0314ddc5-dca4-48a9-86b2-3b7e2d5f49ac" />
  <img width="32%" alt="Wiznet W6100 Plus PoE" src="https://github.com/user-attachments/assets/3fb20cb5-b09f-4d09-92a0-f1a1e6372f61" />
</p>

<p>
  <img width="49%" alt="PCB Render Top" src="https://github.com/user-attachments/assets/6eee33f8-fdad-4ac4-8d7e-d5595d56cc8e" />
  <img width="49%" alt="PCB Render Bottom" src="https://github.com/user-attachments/assets/b7764e6e-593f-4f0e-9f17-bc4e8d7f7716" />
</p>

---

## 🔗 Hardware Component Links

| Category | Component Item | Resource Link |
| :--- | :--- | :--- |
| **Modules** | Wiznet WIZ850io | [Product Page](https://wiznet.io/products/ethernet-modules/wiz850io) |
| **LoRa Modules** | Seeed Studio Wio-SX1262 | [Product Page](https://www.seeedstudio.com/Wio-SX1262-Wireless-Module-p-5981.html) |
| | Seeed Studio Wio-LR1121 | [Product Page](https://www.seeedstudio.com/Wio-LR1121-with-IPEX-antenna-connector-p-6479.html) |
| | Waveshare Core1121-XF | [Product Page](https://www.waveshare.com/core1121-xf.htm) |
| | Waveshare Core2021-XF | [Product Page](https://www.waveshare.com/core2021-xf.htm) |
| **Dev Boards** | Wiznet W5500-EVB-Pico2 | [Product Page](https://wiznet.io/products/powered-by-raspberry-pi/w5500-evb-pico2) |
| | Wiznet W6100-EVB-Pico2 | [Product Page](https://wiznet.io/products/evaluation-boards/w6100-evb-pico2) |
| **Power Supply**| Wiznet WizPoE-P1 | [Product Page](https://wiznet.io/products/PoE/wizpoe-p1) |
| **Local Sourcing**| Robotics Za Component | [Product Page](https://www.robotics.org.za/Y2A240A) |
| | Make Net Za Element A | [Product Page](https://make.net.za/product/3me0022/) |
| | Make Net Za Element B | [Product Page](https://make.net.za/product/3me0015/) |

---

## 🤝 Credits & Acknowledgements
Special thanks to **Carlos Valdes** for foundational implementation and breakthrough contributions regarding Meshtastic Wiznet Ethernet stack integration and custom board configuration support.

This development ecosystem directly references and relies upon upstream firmware improvements:
* [Meshtastic Firmware PR #10552](https://github.com/meshtastic/firmware/pull/10552)
* [Meshtastic Firmware PR #10135](https://github.com/meshtastic/firmware/pull/10135)

---

## ⚠️ Disclaimer
> **Warning:** Use of these GERBER design matrices and 3D printing structural configurations is entirely at your own risk. The project developers accept no liability for hardware damage, malfunctions, or safety hazards resulting from replication.

---

## ☕ Support My Work
If this open hardware project brings utility to your configurations, consider supporting my design pipeline!

[![Buy Me A Coffee](https://shields.io)](https://buymeacoffee.com/mark.birss)
