# Capacitor Measurement System Using ATmega32

## Author
**Mohamed Sobhy**

---

## 📘 Introduction
This project is designed to measure the capacitance of unknown capacitors using an **ATmega32 microcontroller**. It operates on the principle of charging and discharging the capacitor through a known resistor and measuring the time it takes for the voltage across the capacitor to reach a specified threshold.

---

## 🎯 Objective
To build a cost-effective and accurate **Capacitance Meter** capable of measuring a wide range of capacitor values using simple hardware and embedded C software.

---

## 🧰 Components Used
- **ATmega32 Microcontroller**
- **Resistors**: 10kΩ, 1.8kΩ, 470Ω, 220Ω
- **Capacitors**: 100nF, 1μF, 33pF, etc.
- **ADC (Analog-to-Digital Converter)**
- **LCD Display**: For result display
- **Push Button**
- **LED**: Indicator for charging/discharging status

---

## ⚙️ Methodology
The principle is based on the exponential charging and discharging behavior of capacitors in an RC (Resistor-Capacitor) circuit. The microcontroller applies a known voltage across the RC circuit and starts a timer. The time taken for the capacitor voltage to reach a threshold is used to calculate the capacitance.

---

## 💻 Software Implementation
The firmware is written in **C**, originally developed in Atmel Studio for **ATmega8**, and later adapted to **ATmega32**. Below are the main steps:

1. Develop and test initial code on **Atmega8** using **Atmel Studio**.
2. Simulate the Atmega8 circuit and behavior using **Proteus**.
3. Migrate to **Atmega32** by modifying I/O peripherals in the schematic.
4. Convert the project to **CodeVisionAVR**, rewriting assembly functions in pure embedded C.
5. Adjust ISR syntax and include proper **ATmega32 libraries**.
6. Test the final Atmega32 version using **CodeVision** and **Proteus simulation**.

---

## 📊 Results
The system was successfully tested with a variety of known capacitors. Measured values were reasonably accurate, with small errors due to hardware limitations and environmental conditions.

---

## ✅ Conclusion
This project successfully demonstrates the implementation of a **digital capacitance meter** using ATmega32. It highlights a practical application of embedded systems in real-world electronics measurement tasks.

---
### Hardware Adjustments to make it read up too 100F:
1. **Use Very Large Resistors (High R values)**:
   - Keeps charging time within measurable range.
   - Watch for slow voltage rise, noise, and instability.
   - Use precision resistors for accuracy.

2. **Longer Timer Ranges / Slower Clock**:
   - Use slower clocks or external timers for long durations.

3. **Protection Circuits**:
   - Add current-limiting resistors and use MOSFETs/relays to prevent inrush current damage.

4. **Power Supply Considerations**:
   - Ensure power supply can handle the energy stored in supercapacitors.

### Software Adjustments:
- Allow for **longer measurement timeouts**.
- Periodically sample capacitor voltage with **ADC**.
- Wait for threshold (e.g., 63.2% of Vcc).
- Use **averaging or filtering** to reduce measurement noise.

---

## 📂 Repository Contents
- `main.c`: Code written in **CodeVisionAVR** for ATmega32
- `simulation.pdsprj`: **Proteus** simulation of the circuit
- `report.pdf`: Full report describing the system, design, and results

---
