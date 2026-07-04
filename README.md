# 🛰️ MESHBULLET

[![Meshtastic](https://shields.io)](https://github.com)
[![Platform](https://shields.io)](https://raspberrypi.com)
[![PoE Support](https://shields.io)](#)

An advanced, high-efficiency Meshtastic node featuring Power-over-Ethernet (PoE) or standalone layout configurations. Supports complete Over-The-Air (OTA) updates directly via SPI-based Ethernet interfaces and includes a specialized, modular cylindrical 3D-printable enclosure system.

---

## 📌 Features

*   **Core Processing:** Powered by the cutting-edge Raspberry Pi Pico RP2350 microcontroller architecture.
*   **Wired Data Routing:** High-performance hardware SPI interface utilizing Wiznet Ethernet controller modules for stable infrastructure backhaul.
*   **RF Engine Layer:** Universal layout architecture supporting multi-footprint SPI LoRa radio components (SX1262 / LR1121 / LR2011 configurations).
*   **Enclosure Engineering:** Completely optimized, multi-part interlocking cylindrical 3D-printable stack housing.

---

## 📂 Repository Structure & Target Configuration

To compile the firmware for this hardware stack, your local build environment must contain the custom variant files mapped inside the correct target path configuration directories.

### Directory Layout
```text
firmware/
├── variants/
│   └── meshbullet/
│       ├── variant.h          # Hardware SPI pin remappings and macro overrides
│       ├── variant.cpp        # Low-level initialization routines for WIZnet/LoRa
│       └── platformio.ini     # Compilation definitions and target dependencies
```

### Compiler Target Definitions
When building the firmware via PlatformIO, ensure your environments block references the custom hardware configurations outlined below:

| Macro Definition | Configured Assignment | Target Hardware Purpose |
| :--- | :--- | :--- |
| `ARCH_RP2350` | `1` | Targets the Raspberry Pi Pico 2 architecture |
| `ETHERNET_SPI_CS` | `GPIO_PIN_X` | Hardware mapping for the WIZnet Chip Select line |
| `LORA_SPI_CS` | `GPIO_PIN_Y` | Independent SPI Chip Select for the transceiver module |
| `USE_WIZNET_ETHERNET` | `1` | Forces compilation of the wired OTA stack |

---

## 🛠️ General Instructions

### Prerequisites
1.  **PCB Fabrication:** Upload the provided PCB Gerber files directly to an aggregation production house (e.g., [JLCPCB](https://jlcpcb.com) — 5 pieces minimum batch).
2.  **3D Printing Execution:** Slice and print all structural assembly assets using stable thermal filaments (PETG/ASA recommended for outdoor nodes).
3.  **Firmware Provisioning:** Copy the contents of the `variants/meshbullet/` folder into your compilation directory and specify the target profile when executing the build environment script.

### Assembly & Structural Splicing Steps
*   **RJ45 Interface Cap:** Securely seat the RJ45 mag-jack terminal housing into the dedicated printed 3D LAN cap recess using industrial B-7000 adhesive. Ensure a square, perfect 90-degree installation alignment. Let it sit for **2 full days** to allow complete polymer curing.
*   **RF / Antennal Rigging:** Route your ultra-flexible u.Fl to SMA pigtail extensions through the mounting paths, mount the bulkhead structural ring tightly, and set the exterior SMA threads before locking down the modular stack plates.

---

## 🔌 Hardware Variants & Bill of Materials (BOM)

### 1. Non-PoE Infrastructure Setup
*   **Main Processing Core:** Raspberry Pi Pico 2 (RP2350)
*   **Wired Ethernet ASIC:** Wiznet WIZ850io (W5500 Engine)
*   **LoRa Module Allocations:** Seeed Studio Wio-SX1262 or Wio-LR1121 form factors only.
    > [!IMPORTANT]
    > Due to strict physical trace overlap constraints with the wide W5500 WIZ850io footprint layout, Waveshare WS-LR1121 and WS-LR2021 component outlines cannot be co-populated on the Non-PoE PCB variant.
*   **Chassis & Connections:** MESHBULLET Non-PoE specialized PCB, matching 2.54mm square male/female header strips, and B-7000 adhesive.
*   **Recommended Soldering Sequence:**
    1. Flat-mount and solder the primary surface LoRa module to its landing array.
    2. Solder the secondary WIZ850io structural frame down directly onto its pin fields.
    3. Install the alignment pin headers into the parent board, drop the Raspberry Pi Pico 2 on top to guarantee precise axial alignment, solder the header rows to the Pico pads first, then complete connection points on the bottom side of the PCB.

### 2. PoE (Power-over-Ethernet) Integrated Setup
*   **Combined Processing/Ethernet Core:** Wiznet W6100-EVB-Pico2 or W5100S-EVB-Pico2 evaluation platform.
*   **LoRa Module Allocations:** Shared universal hardware footprint accepting Seeed Studio Wio-SX1262 / Wio-LR1121 or Waveshare WS-LR1121 / WS-LR2021 components.
*   **Chassis & Connections:** MESHBULLET PoE specialized breakout base PCB, 2.54mm header blocks, and B-7000 structural glue.
*   **Recommended Soldering Sequence:**
    1. Surface-solder your selected surface-mount LoRa transceiver module down to the landing layout pads.
    2. Mount and solder the dedicated Wiznet PoE power module addon directly onto the host Wiznet EVB-Pico2 board assembly. Leave a sub-millimeter visual air gap to prevent thermal bridging between planes.
    3. Drop standard headers into the base footprint, lower your modular EVB board assembly over the pin rows to anchor layout alignment, solder out the top interface pads, and then secure the base joints underneath.

---

## 📸 Media Gallery

### Structural Assemblies & Enclosure Internals

| Hardware Profile View | LoRa Transceiver Alignment |
| :---: | :---: |
| <img src="https://github.com" width="100%"/> | <img src="https://github.com" width="100%"/> |

### Sub-Assembly Profiles & Enclosure Testing

| W5500/Wio Base Trace | Cylindrical Enclosure Fitting |
| :---: | :---: |
| <img src="https://github.com" width="100%"/> | <img src="https://github.com" width="100%"/> |

### 3D CAD Explo Layouts & Reference Models

| Modular Enclosure Array | RP2350 Microcontroller |
| :---: | :---: |
| <img src="https://github.com" width="100%"/> | <img src="https://github.com" width="100%"/> |

| HanRun Mag-Jack Pinout | PoE Modulated Evaluation Deck |
| :---: | :---: |
| <img src="https://github.com" width="100%"/> | <img src="https://github.com" width="100%"/> |

### PCB Routing Visualizations

| Bare Board Render (Top View) | Bare Board Render (Bottom View) |
| :---: | :---: |
| <img src="https://github.com" width="100%"/> | <img src="https://github.com" width="100%"/> |

---

## 🔗 Hardware Component Links

| Category | Component Item | Resource Link |
| :--- | :--- | :--- |
| **Modules** | Wiznet WIZ850io | [Product Page](https://wiznet.io) |
| **LoRa Modules** | Seeed Studio Wio-SX1262 | [Product Page](https://seeedstudio.com) |
| | Seeed Studio Wio-LR1121 | [Product Page](https://seeedstudio.com) |
| | Waveshare Core1121-XF | [Product Page](https://waveshare.com) |
| | Waveshare Core2021-XF | [Product Page](https://waveshare.com) |
| **Dev Boards** | Wiznet W5500-EVB-Pico2 | [Product Page](https://wiznet.io) |
| | Wiznet W6100-EVB-Pico2 | [Product Page](https://wiznet.io) |
| **Power Supply**| Wiznet WizPoE-P1 | [Product Page](https://wiznet.io) |
| **Local Sourcing**| Robotics Za Component | [Product Page](https://robotics.org.za) |
| | Make Net Za Element A | [Product Page](https://make.net.za) |
| | Make Net Za Element B | [Product Page](https://make.net.za) |

---

## 🤝 Credits & Acknowledgements

Special thanks to:
*   The **MESHTASTIC** core project developer community for baseline firmware layers: [https://github.com](https://github.com).
*   **Carlos Valdes** for creating foundational architectural paths, code modifications for the integrated Wiznet hardware Ethernet layer, custom OTA codebases over wired interfaces, and localized board settings targets.

This open physical hardware development tracking framework references, utilizes, and implements features tracking code updates via upstream project merges:
*   [Meshtastic Firmware PR #10552](https://github.com/firmware/pull/10552)
*   [Meshtastic Firmware PR #10135](https://github.com/firmware/pull/10135)
*   [Meshtastic Firmware PR #10136](https://github.com/firmware/pull/10136)

---

## ⚠️ Disclaimer

> [!WARNING]
> Use of these layout design materials, raw Gerber PCB manufacturing maps, firmware instructions, and custom 3D structural housing printing profiles is completely at your own risk. The developer environment contributors accept no legal liability or responsibility for physical component damage, systemic firmware failures, short-circuits, or fire hazards during replication.

---

## ☕ Support My Work

