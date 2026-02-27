# ⚙️ Backend: Arduino Control Logic

This directory contains the firmware for the **Arduino Uno**. The code is designed to interface with an HC-05 Bluetooth module to receive serial commands from the mobile app and trigger the corresponding relay channels.

---

## 🛠 Logic Breakdown
The code utilizes `Serial.readString()` to interpret commands sent from the MIT App Inventor frontend. It supports both **voice commands** (full strings like "fan on") and **button commands** (single characters like "A").

### Command Mapping Table:
| Device | ON Command | OFF Command | Arduino Pin |
| :--- | :--- | :--- | :--- |
| 🌀 **Fan** | "fan on" / "A" | "fan off" / "a" | Pin 2 |
| 💡 **Bulb** | "bulb on" / "B" | "bulb off" / "b" | Pin 3 |
| 📺 **TV** | "TV on" / "C" | "TV off" / "c" | Pin 4 |
| ❄️ **AC** | "AC on" / "D" | "AC off" / "d" | Pin 5 |
| 🏠 **All** | "all on" / "E" | "all off" / "e" | All Pins |

---

## 🚀 How to Upload
1.  Open the `backend/main.ino` file in the **Arduino IDE**.
2.  **IMPORTANT:** Disconnect the `RX` and `TX` wires from your Bluetooth module before uploading (otherwise, the upload will fail).
3.  Select **Arduino Uno** and your **Port**.
4.  Click **Upload**.
5.  Reconnect the Bluetooth wires and power the system.



---

## 🧩 Key Features in this Code
* **Fault Tolerance:** Includes checks for common typos (e.g., "fan of" vs "fan off") to ensure the voice recognition works smoothly.
* **Bulk Control:** The "All ON/OFF" command allows for quick home automation scenes.
* **Serial Debugging:** The code prints the received value to the Serial Monitor at **9600 baud**, making it easy to troubleshoot connection issues.

---

## 🔗 Project Links
* **Interactive Circuit:** [View on Cirkit Designer](https://app.cirkitdesigner.com/project/b47e554e-9783-483c-a491-85ef9027f9ea)
* **Frontend Source:** Check the `/frontend` directory for the `.aia` file.
