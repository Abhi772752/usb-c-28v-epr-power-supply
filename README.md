# USB-C PD 3.1 Advanced Power Supply (5V–28V EPR)

> **Designed in EasyEDA Pro (`.epro2`)** | 4-Layer Controlled Stackup | High Power Density

---

## 📌 Project Overview
An open-hardware **USB-C Extended Power Range (EPR)** sink power supply capable of negotiating output power rails (**5V, 9V, 12V, 20V, and 28V**) from any compliant USB PD 3.1 source. 

Output rails are selected via a 3-bit binary hardware switch using an onboard **DSHP03TS-S 3-position SMD DIP switch** interfaced directly with the USB PD Sink Controller configuration pins.

---

## ⚡ Technical Specifications
* **Input Interface:** USB Type-C (PD 3.1 / EPR Supported)
* **Output Voltages:** 5V, 9V, 12V, 20V, 28V (Up to 140W Peak Capability)
* **Hardware Interface:** DSHP03TS-S 3-Position SMD DIP Switch
* **EDA Tool:** EasyEDA Pro 2.x (`.epro2` project file)
* **PCB Form Factor:** 4-Layer FR-4 (1.6 mm nominal thickness)

---

## 📐 4-Layer PCB Stackup Details
Designed on a controlled-impedance dielectric structure to ensure proper return paths and thermal management:

| Layer | Type | Thickness (mm) | Description / Notes |
| :--- | :--- | :--- | :--- |
| **Top Layer** | Copper | 0.035 mm (1 oz) | Main high-current power path, DSHP03TS-S switch, components |
| *Dielectric 1* | Prepreg | 0.210 mm | Tight coupling gap to reference ground |
| **Inner Layer 1** | Copper | 0.015 mm (0.5 oz) | Continuous Ground (GND) Reference Plane |
| *Core* | Core | 1.065 mm | Structural dielectric core isolation |
| **Inner Layer 2** | Copper | 0.015 mm (0.5 oz) | Sub-regulated logic/power planes |
| *Dielectric 3* | Prepreg | 0.210 mm | Isolation prepreg |
| **Bottom Layer** | Copper | 0.035 mm (1 oz) | Thermal via matrix, secondary routing, ground pour |

---

## 🎛️ DSHP03TS-S Switch Decoding Logic
The 3-bit state of the DIP switch sets the configuration pins on the USB PD controller to request the desired Power Data Object (PDO):

| SW1 | SW2 | SW3 | Negotiated Output Voltage |
| :---: | :---: | :---: | :---: |
| OFF | OFF | ON | **5V** |
| OFF | ON  | OFF | **9V** |
| OFF | ON  | ON | **12V** |
| ON  | OFF | OFF | **20V** |
| ON  | OFF | ON | **28V (EPR)** |
