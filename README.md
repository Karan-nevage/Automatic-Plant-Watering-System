# 🌱 Automatic Plant Watering System

An Arduino-based smart irrigation system that automates plant watering using a soil moisture sensor and a submersible pump. Designed to reduce manual effort and ensure optimal hydration for plants.

---

## 📦 Components Used

| No. | Component                  | Quantity | Unit Price (INR) | Total (INR) |
|-----|----------------------------|----------|------------------|-------------|
| 1   | Arduino Uno                | 1        | 1000             | 1000        |
| 2   | Moisture Sensor            | 1        | 70               | 70          |
| 3   | 1-Channel Relay Module     | 1        | 50               | 50          |
| 4   | Submersible Pump           | 1        | 70               | 70          |
| 5   | SPDT On-Off Switch         | 1        | 15               | 15          |
| 6   | Jumper Wires               | 30       | 1.5              | 45          |
| 7   | Pipe                       | 1        | 20               | 20          |
| 8   | Container                  | 1        | 30               | 30          |
| 9   | Pots                       | 2        | 100              | 200         |
| 10  | Adapter (6V)               | 1        | 100              | 100         |
| 11  | Connecting Wire            | 1        | 20               | 20          |
|     | **Total**                 |          |                  | **1620**    |

---

## 🛠️ System Overview

- **Microcontroller**: Arduino Uno (ATmega328P)
- **Sensor**: Soil Moisture Sensor
- **Actuator**: Submersible Water Pump
- **Control Logic**: Relay module triggered by moisture readings
- **Power Supply**: 6V DC Adapter

---

## ⚙️ How It Works

1. The soil moisture sensor continuously monitors the soil's water level.
2. If the moisture level drops below a threshold, the Arduino activates the relay.
3. The relay powers the submersible pump, watering the plant.
4. Once adequate moisture is detected, the pump is turned off.

---

## 🔧 Circuit Diagram

![Circuit Diagram](Circuit%20Diagram.jpg)

---

## 💻 Arduino Code

```cpp
int water;

void setup() {
  pinMode(3, OUTPUT); // Relay control
  pinMode(6, INPUT);  // Soil moisture sensor input
}

void loop() {
  water = digitalRead(6);
  if (water == HIGH) {
    digitalWrite(3, LOW); // Stop watering
  } else {
    digitalWrite(3, HIGH); // Start watering
  }
  delay(1000);
}
