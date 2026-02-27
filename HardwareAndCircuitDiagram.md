# 🔌 Hardware Architecture & Circuit Design

This document provides a detailed technical breakdown of the hardware layer for the **Diigital Home** IoT system. The design focuses on safe AC load switching using an Arduino-based control circuit.

---

## 🛠 Component Specifications

| Component | Specification | Role |
| :--- | :--- | :--- |
| **Microcontroller** | Arduino Uno R3 | Central logic processing |
| **Communication** | HC-05 Bluetooth Module | Wireless data bridge (Serial) |
| **Actuator** | 5V Single-Channel Relay | High-voltage electronic switch |
| **Voltage Divider** | 1kΩ & 2kΩ Resistors | Logic level shifting (5V to 3.3V) |
| **Power Supply** | 9V 1A DC Adapter | Dedicated power for stable relay switching |

---

## 📐 Circuit Schematic

The following diagram illustrates how the components are interconnected. 


## 🎮 Interactive Simulation & Model

I have designed a professional interactive model of the **Diigital Home** circuit. You can view the full wiring, component list, and signal flow by clicking the link below:

**🔗 [View Interactive Circuit Design on Cirkit Designer](https://app.cirkitdesigner.com/project/b47e554e-9783-483c-a491-85ef9027f9ea)**

### 🔄 How to use the Interactive Model:
1. **Click the link** above to open the Cirkit Designer web interface.
2. **Explore the Wiring**: Hover over the wires to see how the Arduino pins (0, 1, and 2) are connected to the Bluetooth and Relay modules.
3. **Component Specs**: You can see the specific values for the resistors (1kΩ and 2kΩ) used in the logic level shifter.

---

### 📸 Project Interaction Overview
Below is a visual representation of how the app communicates with the hardware you see in the link above:

---<img width="3000" height="2192" alt="circuit_image" src="https://github.com/user-attachments/assets/491187cf-13c4-40a4-bd9f-8edfeb37da1d" />

* **App Side**: The MIT App Inventor frontend sends Serial data strings.
* **Hardware Side**: The Arduino interprets the data and triggers the Relay based on the circuit logic.

### 🧪 Simulation Environment
If you want to test the logic virtually:
* **Circuit Simulator**: You can find the interactive wiring model on [Tinkercad Circuits](https://www.tinkercad.com/).
* **App Logic**: View the `screenshots/` folder in this repository to see the interactive Block logic that handles the Bluetooth connection status.

> **Tip:** Look for the blinking LED on the HC-05 module; it indicates whether the "Diigital Home" app has successfully established a handshake with your hardware!

## ⚡ Detailed Connection Mapping

### 1. The Control Interface (Bluetooth)
The **HC-05 module** acts as the ear of the project, listening for commands from the MIT App Inventor frontend.
* **VCC/GND**: Connected to the Arduino 5V and GND rails.
* **TX (Module) → RX (Arduino Pin 0)**: Sends the character data received from your phone to the Arduino.
* **RX (Module) ← TX (Arduino Pin 1)**: This connection requires a **Voltage Divider**. Since the HC-05 logic operates at 3.3V and the Arduino at 5V, we use resistors to prevent burning out the module's receiver.

### 2. The Switching Logic (Relay)
The **Relay** acts as the bridge between your safe 5V circuit and the dangerous 220V/110V home appliances.
* **Signal (IN)**: Connected to **Digital Pin 2**. 
* **Operation**: When the Arduino sends a `HIGH` signal, the internal electromagnet pulls the switch closed, completing the AC circuit.

### 3. The Power Load (IoT Device)
* **COM (Common)**: Connected to the **Live** wire of your AC power source.
* **NO (Normally Open)**: Connected to the **Fan/Light** input. 
* *Note: By using the NO terminal, the appliance stays OFF by default if the Arduino loses power.*

---

## 🛡 Engineering Safety Principles

### Galvanic Isolation
By using a relay, the high-voltage AC side is **optically or magnetically isolated** from the DC microcontroller. This ensures that even if a power surge occurs on the AC line, your Arduino and Bluetooth module remain protected.



### Logic Level Shifting
The inclusion of a 1kΩ/2kΩ resistor network on the Bluetooth RX line is a professional standard. It ensures the signal stays within the **3.3V CMOS threshold**, extending the lifespan of your communication hardware.

---

## 📝 Setup & Installation

1.  **Logic Wiring**: Complete all breadboard connections for the Bluetooth and Relay modules.
2.  **Code Upload**: Upload your `.ino` sketch to the Arduino. **Important:** Disconnect the RX/TX pins of the Bluetooth module during upload to avoid serial conflicts.
3.  **Dry Run**: Power the Arduino and use the **Diigital Home** app. Listen for a "click" from the relay to confirm the logic is working.
4.  **High Voltage Wiring**: Only after the dry run, connect your appliance to the relay terminals. 

> **⚠️ SAFETY WARNING:** This project involves AC Mains electricity. Always ensure the power is unplugged while wiring the relay terminals. Use a non-conductive enclosure to house the final circuit.
