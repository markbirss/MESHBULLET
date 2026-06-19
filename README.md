# MESHBULLET

PoE and non-PoE Meshtastic version
* Raspberry Pi Pico RP2350 powered
* 3D print enclosure

Instructions:

Gather Parts for 
non-PoE version -

* RP2350 board
* Wis85Dio ( W5500 )
* LoRa Radio Module ( available choices are Seeed WIO-SX1262 / WIO-LR1121 only as the WS-LR1121/WS-LR2021 footpint will be used by the W5500 Wis85Dio ) 
* PCB
* 2.54 Headers
* B-7000 Glue
* Solder LoRa Module onto PCB
* Solder Wis85Dio into PCB
* Solder header to pico while inserted into PCB, then solder header to PCB ( refer to pictures below for header orientation )

PoE version - 

* Wiznet W6100-EVB-Pico2 / W5100S-EVB-Pico2
* LoRa Radio Module ( available choices are Seeed WIO-SX1262 / WIO-LR1121 or Waveshare WS-LR1121 / WS-LR2021 - uses same pcb footprint )
* PCB
* 2.54 Headers
* B-7000 Glue
* Solder LoRa Module onto PCB
* Solder Wiznet PoE module into the Wisnet EVB allow a tiny gap between the Wiznet EVB and Wisnet PoE board
* Solder header to Wiznet EVB while inserted into PCB, then solder header to PCB ( refer to pictures below for header orientation )


<img width="4000" height="1848" alt="20260619_112228" src="https://github.com/user-attachments/assets/08f2fe31-11b9-4ec4-84bb-42252d97b3c5" />



* Send PCB Gerber for PCB manufacture ( JLCPCB allow 5 pcs mimimum )

* 3D print parts

* Glue into place the RJ45 end of into the RJ45 Lan Cap

* Flash board with firmware ( still to release or merge this DIY varaint )

* Aseemble SMA connectors, uFl pigtails and glue together parts

Use B-7000 glue ( needs about 2 days to cure well )


Pictures

non PoE Version (wiz850io)  with wio-sx1262

<img width="1848" height="4000" alt="20260615_182515" src="https://github.com/user-attachments/assets/a23e4a62-59ba-4bb9-b5eb-09c8e8e9c086" />

<img width="1848" height="4000" alt="20260615_182526" src="https://github.com/user-attachments/assets/f7f75654-1eed-4edd-8765-8d5831359eb6" />


PoE version Wiznet ( W61100 + Waveshare LR2021 )

<img width="1848" height="4000" alt="20260615_182603" src="https://github.com/user-attachments/assets/65516aeb-60a5-4157-99f4-2df2e8e74674" />



Parts


<img width="500" height="500" alt="3490_RPi_Pico2_board_D_webp-107716-500x500" src="https://github.com/user-attachments/assets/06482550-a9e0-4326-8c30-ac8459f36bcd" />

<img width="345" height="247" alt="W5500-MINI - Layout01" src="https://github.com/user-attachments/assets/0314ddc5-dca4-48a9-86b2-3b7e2d5f49ac" />

<img width="666" height="445" alt="wiznet_W6100_plus_poe" src="https://github.com/user-attachments/assets/3fb20cb5-b09f-4d09-92a0-f1a1e6372f61" />


<img width="337" height="107" alt="Photo-View_2026-05-14" src="https://github.com/user-attachments/assets/6eee33f8-fdad-4ac4-8d7e-d5595d56cc8e" />

<img width="317" height="107" alt="Photo-View_2026-05-14 (1)" src="https://github.com/user-attachments/assets/b7764e6e-593f-4f0e-9f17-bc4e8d7f7716" />

Testing DIY 3d Print Case

<img width="1071" height="970" alt="image" src="https://github.com/user-attachments/assets/7a0d901a-5b20-48ad-a1c4-46352514423e" />

Links

https://wiznet.io/products/ethernet-modules/wiz850io

https://www.seeedstudio.com/Wio-SX1262-Wireless-Module-p-5981.html

https://www.seeedstudio.com/Wio-LR1121-with-IPEX-antenna-connector-p-6479.html

https://www.waveshare.com/core1121-xf.htm

https://www.waveshare.com/core2021-xf.htm

https://wiznet.io/products/powered-by-raspberry-pi/w5500-evb-pico2

https://wiznet.io/products/evaluation-boards/w6100-evb-pico2

https://wiznet.io/products/PoE/wizpoe-p1

https://www.robotics.org.za/Y2A240A

https://make.net.za/product/3me0022/

https://make.net.za/product/3me0015/

Credits

Carlos Valdes for work with regard to Meshtastic Wiznet Ethernet and board support

Based on existing related work by Carlos Valdes

https://github.com/meshtastic/firmware/pull/10552

https://github.com/meshtastic/firmware/pull/10135


# **JLBPCB Gerber view (online)**
https://jlcpcb.com/RGE

# **DISCLAIMER**

# Use of these GERBER, 3D Parts are at your own risk

Support my work and consider **buying  me a coffee**

https://buymeacoffee.com/mark.birss
