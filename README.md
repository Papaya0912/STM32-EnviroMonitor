# STM32 Environmental Monitoring System (EcoSense)

![C/C++](https://img.shields.io/badge/Language-C-blue.svg)
![Microcontroller](https://img.shields.io/badge/MCU-STM32-orange.svg)
![Framework](https://img.shields.io/badge/Framework-STM32_HAL-green.svg)

## 📌 Overview
An embedded system built on the STM32 microcontroller to monitor real-time environmental parameters. The system measures temperature, humidity, air quality, and light intensity, displaying the data through a multi-interface output (LCD 16x2, 8x8 LED Matrix, and 7-segment display). It also features an interactive menu system and user-configurable warning alarms.

## ✨ Key Features
* **Air Quality Monitoring**: Uses MQ135 sensor to evaluate air quality (Displays "Good" or "Bad").
* **Temperature & Humidity Sensing**: Reads real-time data using the DHT11 sensor.
* **Light Intensity Visualization**: Dynamically maps LDR sensor values to an 8x8 LED Matrix for visual light intensity representation.
* **Multi-Display Output**: Integrates a 16x2 LCD for menus, dual 7-segment displays for humidity, and an LED matrix for light levels.
* **Configurable Alarms**: Hardware interrupts (EXTI) via push buttons allow users to navigate menus and adjust the temperature warning threshold.
* **Safety Alerts**: Triggers an alert (LED/Buzzer) if the temperature exceeds the user-defined threshold or if air quality drops.

## 🛠️ Hardware Requirements
* **MCU**: STM32 Development Board (e.g., STM32F4/F1 series)
* **Sensors**: DHT11 (Temp/Hum), MQ135 (Gas/Air Quality), LDR (Light Dependent Resistor)
* **Displays**: 16x2 LCD, 8x8 LED Matrix, 2-Digit 7-Segment Display
* **Inputs**: 3x Push Buttons

## 🔌 Pin Mapping (Hardware Connections)

| Peripheral | STM32 Pin | Note |
| :--- | :--- | :--- |
| **DHT11** | `PA0` | 1-Wire Data (Custom Bit-banging) |
| **MQ135 (Air)** | `PA1` | ADC1 Channel 1 |
| **LDR (Light)** | `PA2` | ADC1 Channel 2 |
| **Buttons** | `PC13`, `PC14`, `PC15` | EXTI (Interrupts) for Menu/Adjustments |
| **LED Matrix Rows**| `PB0` - `PB7` | Row Control |
| **LED Matrix Cols**| `PA3` - `PA10`| Column Control |
| **7-Segment Data** | `PB0` - `PB9` | Multiplexed Output |
| **7-Seg Control** | `PA11`, `PA12` | Digit Select (Tens/Units) |
| **Alert/Buzzer** | `PA15` | Triggered on high Temp/Bad Air |

## 🚀 Getting Started
1. Clone this repository:
2. Open the project in STM32CubeIDE or Keil uVision.
3. Compile and flash the code to your STM32 board.
4. Ensure hardware connections match the Pin Mapping table above.
