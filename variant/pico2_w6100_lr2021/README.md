# Raspberry Pi Pico 2 + W6100 + WS_LR2021 — Meshtastic Variant

Meshtastic support for a **Raspberry Pi Pico 2** (RP2350, 2 MB flash) with an external **W61500** Ethernet module and an **WS_LR2021** LoRa module.

---

## Required Hardware

| Component | Model               | Notes                                    |
| --------- | ------------------- | ---------------------------------------- |
| MCU       | Raspberry Pi Pico 2 | RP2350 @ 150 MHz, 512 KB RAM, 4 MB flash |
| Ethernet  | W5500 module        | Any WIZnet W5500 breakout board          |
| LoRa      | WAVESHARE LR2021    | LR2021 (XTAL) + 22 dBm, 868/915 MHz          |

---

## Pinout

### System pins (Pico 2, fixed)

| GPIO | Function                                |
| ---- | --------------------------------------- |
| GP24 | VBUS sense — HIGH when USB is connected |
| GP25 | User LED (heartbeat)                    |
| GP29 | ADC3 — VSYS/3, measures supply voltage  |

### W5500 Ethernet (SPI0)

| W5500 signal | Pico 2 GPIO |
| ------------ | ----------- |
| MISO         | GP16        |
| CS / SCS     | GP17        |
| SCK          | GP18        |
| MOSI         | GP19        |
| RST          | GP20        |
| INT          | — (nc)      |
| VCC          | 3.3V        |
| GND          | GND         |

> SPI0 is reserved for the W5500.

### E22-900M30S LoRa (SPI1)

| E22 signal | Pico 2 GPIO | Notes                                      |
| ---------- | ----------- | ------------------------------------------ |
| SCK        | GP10        | SPI1 clock                                 |
| MOSI       | GP11        | SPI1 TX                                    |
| MISO       | GP12        | SPI1 RX                                    |
| NSS / CS   | GP13        | Chip select                                |
| RESET      | GP15        | Active LOW reset                           |
| DIO1       | GP14        | IRQ interrupt                              |
| BUSY       | GP2         | Module busy indicator                      |
| RXEN       | GP3         | LNA enable — held HIGH permanently         |
| TXEN       | ← DIO2      | See wiring note below                      |
| VCC        | 3.3V        | Add a 100 µF capacitor close to the module |
| GND        | GND         | —                                          |

> See `wiring.svg` in this directory for the full connection diagram.

## Build

```bash
pio run -e pico2_w6100_lr2021
```

### Flash — BOOTSEL mode

1. Hold the **BOOTSEL** button on the Pico 2.
2. Connect USB to the PC — it appears as a `RPI-RP2` storage drive.
3. Copy the `.uf2` file:

```text
.pio/build/pico2_w6100_lr2021/firmware-pico2_w6100_lr2021-*.uf2
```

Or directly with picotool:

```bash
pio run -e pico2_w6100_lr2021 -t upload
```

---

## Network usage

This board uses Ethernet (no Wi-Fi). From the Meshtastic app:

- **Enable Ethernet** under `Config → Network → Ethernet Enabled`
- **DHCP** by default; static IP can also be configured

Services available once connected:

| Service | Details                     |
| ------- | --------------------------- |
| NTP     | Time synchronization        |
| MQTT    | Messages to external broker |
| API     | TCP socket on port 4403     |
| Syslog  | Remote logging (optional)   |

---

## Technical notes

### Ethernet

- Library: `arduino-libraries/Ethernet@^2.0.2` (supports W6100).
- SPI0 is explicitly initialized with pins GP16/18/19 before `Ethernet.init()`.
- DHCP timeout is set to 10 s (instead of the default 60 s) to avoid blocking LoRa startup.

### HW_VENDOR

Mapped to `meshtastic_HardwareModel_PRIVATE_HW` — no dedicated model exists in the Meshtastic protobuf for this hardware combination yet.

---

## Memory usage (reference build)

| Resource | Used   | Total   | %     |
| -------- | ------ | ------- | ----- |
| RAM      | 94 KB  | 512 KB  | 18%   |
| Flash    | 964 KB | 3.58 MB | 26.3% |
