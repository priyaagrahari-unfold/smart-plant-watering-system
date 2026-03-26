# smart-plant-watering-system
Arduino-based automatic plant watering system using soil moisture sensor
# 🌱 Smart Plant Watering System

An Arduino-based automatic plant watering system that waters plants when soil moisture falls below a threshold.

---

## 🚀 Features
- Automatic watering based on soil moisture
- Saves water and manual effort
- Low-cost and efficient system
- Real-time sensing

---

## 🛠️ Components Used
- Arduino UNO
- Soil Moisture Sensor
- Relay Module
- Water Pump
- Connecting Wires

---

## ⚙️ Working Principle
The soil moisture sensor detects the moisture level of the soil.  
If the soil is dry (below threshold), the Arduino activates the relay module, which turns ON the water pump.  
Once the soil reaches sufficient moisture, the pump turns OFF automatically.

---

## 💻 Arduino Code

```cpp
int sensorPin = A0;
int relayPin = 7;
int moistureValue = 0;
int threshold = 500;

void setup() {
  pinMode(relayPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  moistureValue = analogRead(sensorPin);
  Serial.println(moistureValue);

  if (moistureValue < threshold) {
    digitalWrite(relayPin, HIGH); // Pump ON
  } else {
    digitalWrite(relayPin, LOW); // Pump OFF
  }

  delay(1000);
}
