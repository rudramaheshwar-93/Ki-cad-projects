# Voltage Regulator PCB (5V to 3.3V)

## 📌 Overview
A compact 2-layer PCB designed to regulate a 5V input supply down to a
stable 3.3V output using an LDO (Low Dropout) voltage regulator.
Designed for use in embedded systems and IoT applications where 3.3V
logic level components like ESP32, STM32, and nRF24L01 require a clean,
stable power supply.

## ⚡ Key Specifications
- Input Voltage: 5V (USB or external supply)
- Output Voltage: 3.3V regulated
- Regulator Type: LDO (Low Dropout)
- Maximum Output Current: 800mA
- Layers: 2-layer PCB
- PCB Size: compact form factor
- Designed using: KiCad 7.0

## 🖼️ PCB Preview
<!-- Add your 3D render screenshot here -->
![PCB Front](images/pcb_front.png)

## 📂 Repository Structure
​```
voltage-regulator-pcb/
├── voltage_regulator.kicad_pcb   → PCB layout file
├── voltage_regulator.kicad_sch   → Schematic file
├── voltage_regulator.kicad_pro   → Project file
├── gerber/                       → Manufacturing files
│   ├── voltage_regulator-F_Cu.gbr
│   ├── voltage_regulator-B_Cu.gbr
│   ├── voltage_regulator-Edge_Cuts.gbr
│   └── voltage_regulator-job.gbrjob
└── README.md
​```

## 🔧 Components Used
| Component | Value | Purpose |
|---|---|---|
| U1 | AMS1117-3.3 / LM1117 | LDO Voltage Regulator |
| C1 | 10µF Electrolytic | Input Decoupling Capacitor |
| C2 | 10µF Electrolytic | Output Decoupling Capacitor |
| C3 | 100nF Ceramic | High Frequency Bypass |
| LED1 | Green LED | Power Indicator |
| R1 | 1kΩ | LED Current Limiting Resistor |
| J1 | 2-pin Connector | Input (5V) |
| J2 | 2-pin Connector | Output (3.3V) |

## 🔌 How It Works
1. 5V input is fed through J1 connector
2. Input decoupling capacitor C1 filters supply noise
3. LDO regulator drops voltage from 5V to stable 3.3V
4. Output capacitor C2 ensures stability and reduces ripple
5. Green LED indicates the board is powered and outputting correctly
6. Clean 3.3V output is available at J2 connector

## 📐 Design Decisions
- Used AMS1117-3.3 LDO for its wide availability and low dropout voltage
- Added both electrolytic and ceramic capacitors for broadband noise filtering
- Power indicator LED helps verify output during testing without a multimeter
- Wide power traces (0.5mm+) to handle up to 800mA current safely

## 🏭 Manufacturing
Gerber files in `/gerber` folder are tested and verified with zero
DRC errors. Ready to order directly from:
- JLCPCB — jlcpcb.com
- PCBWay — pcbway.com

## 🛠️ Tools Used
- KiCad 7.0 — PCB design and schematic capture
- LTspice — Pre-layout voltage regulation simulation

## 👤 Author
Chappidi Rudra Maheshwar Reddy
GitHub: github.com/rudramaheshwar-93
