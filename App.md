# 📱 Diigital Home - Mobile Interface

This section of the repository contains the frontend application files, user interface design, and block-based logic for the **Diigital Home** IoT system.

---

## 📄 App Overview
The **Diigital Home** app serves as a remote control for household appliances. It was developed as a school IoT project to demonstrate how mobile devices can communicate with microcontrollers via Bluetooth Low Energy (BLE) or Classic Bluetooth.

### Key Features:
* **Device Pairing:** Seamless Bluetooth connection management.
* **Appliance Control:** Toggle switches for fans, lights, and other IoT devices.
* **Visual Feedback:** Real-time status updates showing if devices are ON or OFF.
* **Custom UI:** Hand-picked icons for a modern "Smart Home" feel.
### Visuals:

![IMG-20260218-WA0000](https://github.com/user-attachments/assets/cad058eb-d071-45e1-a352-f7d3c4499921)


![IMG-20260218-WA0001](https://github.com/user-attachments/assets/071f3c56-6f69-4ab2-8b04-d482a8c2a0a2)


---

## 🧩 Logic Architecture (Blocks)

Since MIT App Inventor uses visual blocks, here is an explanation of the core logic:

### 1. Bluetooth Connection Logic
When the "Connect" button is pressed, the app scans for the **HC-05/06 module** address defined in the code. Upon successful connection, the status label changes to "Connected".



### 2. Data Transmission
Each button in the app is programmed to send a specific **Serial String**. 
* **Button ON:** Sends "1"
* **Button OFF:** Sends "0"



---

## 🚀 How to Import & Edit
1.  Navigate to the `/Diigital_Home.aia` folder in this repo.
2.  Download the `Diigital_Home.aia` file.
3.  Go to [MIT App Inventor](http://ai2.appinventor.mit.edu/).
4.  Select `Projects` > `Import project (.aia) from my computer`.

---

## 🔗 Interactive Links
* **Circuit Design:** [View the Hardware Model here](https://app.cirkitdesigner.com/project/b47e554e-9783-483c-a491-85ef9027f9ea)

---
*Developed as a School IoT Project by Abrar Muhammad*
