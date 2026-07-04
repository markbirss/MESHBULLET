## 📌 Supported Hardware Variants

This project supports specific hardware configurations optimized for either indoor or outdoor deployment.

### 🏠 Indoor Variant
* **Model:** `pico2_w5500_wio_sx1262`
* **Core:** Raspberry Pi Pico 2
* **Connectivity:** W5500 Ethernet
* **Wireless:** Wio / SX1262 LoRa module

### 🌳 Outdoor Variant
* **Model:** `pico2_w6100_lr2021`
* **Core:** Raspberry Pi Pico 2
* **Connectivity:** W6100 Ethernet (IPv6 ready)
* **Wireless:** LR2021 LoRa module

# Arduino Ethernet Library Comparison: Standard vs. WIZnet W6100 Fork

[![Arduino Core](https://shields.io)](https://github.com)
[![WIZnet Fork](https://shields.io)](https://github.com)
[![Protocol](https://shields.io)](#)

A comprehensive guide explaining the architectural, protocol, and hardware differences between the official **Standard Arduino Ethernet Library** and the specialized **WIZnet W6100 IPv6 Fork**.

---

## 📌 Architectural & Hardware Overview

When scaling IoT hardware deployments, selecting the correct network stack library impacts memory usage, protocol compliance, and hardware compatibility. Below is a breakdown of the hardware ecosystems supported by these respective codebases.

### 🔌 Hardware Profiles

