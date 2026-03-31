# 🎆 Dynamic LED Chaser System (Arduino Uno Implementation)

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=4285f4&height=220&section=header&text=LED%20CHASER%20DYNAMICS&fontSize=50&animation=fadeIn" width="100%" />
</p>

## 📖 Overview & Objectives
This project is an in-depth study of digital output management and timing synchronization on microcontrollers. The goal is to design a system capable of executing **9 complex animation sequences** on a 13-LED linear matrix, ensuring smooth transitions and optimized power management.

---

## 🛠️ Hardware Architecture

### 📋 Pin Configuration Table
| Component | Arduino Pins | Resistor | Logical Function |
| :--- | :--- | :--- | :--- |
| 🔵 **LEDs 1 to 13** | `PIN 1` to `13` | 220 Ω | Visual Actuators (Sequential) |
| ⚡ **Microcontroller** | `Arduino Uno` | — | Central Processing Unit |
| 🔌 **Ground (GND)** | `GND` | — | Common Current Return |

### 🔍 Technical Assembly Analysis

#### ⚡ Why 220Ω Resistors?
Each LED is paired with a resistor to protect the ATmega328P microcontroller:
1. **Port Protection:** Limits the current to approximately **15mA** per pin, staying well below the 40mA safety limit.
2. **Visual Consistency:** Ensures uniform brightness across all 13 LEDs, even during multi-LED patterns.

#### 🏗️ Circuit Structure
The assembly uses a **common ground rail**. All LED cathodes (short legs) are connected to this rail, which leads back to the Arduino **GND** pin. This allows for a clean, organized wire management system for the 13 signal lines.

---

## 🧠 Software Development Logic

The firmware is built with a modular approach, treating the Arduino as an algorithmic sequence generator.

### 1. Technical Initialization (`void setup()`)
The program defines 13 pins as `OUTPUT`. Each port is prepared to deliver 5V to the LEDs. *Note: Pin 1 (TX) is used as a digital output, so serial communication should be avoided during operation.*

### 2. Animation Algorithms (`void loop()`)
The main loop triggers an infinite cycle of 9 specialized functions:
* **Linear Flow:** Sequences `blink_1` to `blink_4` (Simple scanning and ping-pong).
* **Symmetric Patterns:** Sequences `blink_5` to `blink_8` (Convergence, divergence, and bounce).
* **Pulse Mode:** Sequence `blink_9` (Global heartbeat effect).

---

## 🚀 Performance & Safety Analysis
* **Non-concurrency:** Rigorous management of `HIGH` and `LOW` states to prevent power surges.
* **Modularity:** Using a global timing variable `t` allows for real-time adjustment of the overall animation speed.

---

## 🛠️ Getting Started Guide

1. **Wiring:** Reproduce the circuit on a breadboard, connecting LEDs to pins 1 through 13 with resistors.
2. **Setup:** Use the Arduino IDE to verify and compile the `.ino` code.
3. **Flashing:** Connect your board via USB and upload the program.
4. **Test:** Observe the automatic startup sequence.

---

## 👨‍💻 Developer
**Rayane_Dev** 🇲🇦
> "Embedded engineering at the service of intelligent automation."

<p align="center">
  <a href="mailto:rayanedev1@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" /></a>
  &nbsp;
  <a href="https://github.com/your-username"><img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white" /></a>
</p>

---
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=4285f4&height=30&section=footer" width="100%" />
  <br>
  <i>System Status: OPERATIONAL | Animation Logic Verified</i>
</p>
