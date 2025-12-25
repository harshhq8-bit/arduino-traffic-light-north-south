# 🚦 Arduino Traffic Light System (North–South)

This project demonstrates a **North–South traffic light control system** using **Arduino**.
It simulates real-world traffic signal behavior using **Red, Yellow, and Green LEDs** for
both directions.

---

## 🔧 Components Used
- Arduino Uno  
- Breadboard  
- Red, Yellow, Green LEDs (2 sets)  
- 220Ω Resistors  
- Jumper wires  
- USB cable  

---

## ⚙️ Working Principle
The Arduino controls the traffic lights using **digital output pins** and **time delays**.
Only one direction receives a green signal at a time while the other remains red, ensuring
safe and orderly traffic flow.

---

## 🔌 Circuit Connections
Refer to the `connections.md` file for detailed wiring information.

---

## 💻 Arduino Code
```cpp
int northRed = 2;
int northYellow = 3;
int northGreen = 4;

int southRed = 5;
int southYellow = 6;
int southGreen = 7;

void setup() {
  pinMode(northRed, OUTPUT);
  pinMode(northYellow, OUTPUT);
  pinMode(northGreen, OUTPUT);

  pinMode(southRed, OUTPUT);
  pinMode(southYellow, OUTPUT);
  pinMode(southGreen, OUTPUT);
}

void loop() {
  digitalWrite(northGreen, HIGH);
  digitalWrite(southRed, HIGH);
  delay(5000);

  digitalWrite(northGreen, LOW);
  digitalWrite(northYellow, HIGH);
  delay(2000);

  digitalWrite(northYellow, LOW);
  digitalWrite(northRed, HIGH);
  digitalWrite(southRed, LOW);
  digitalWrite(southGreen, HIGH);
  delay(5000);

  digitalWrite(southGreen, LOW);
  digitalWrite(southYellow, HIGH);
  delay(2000);

  digitalWrite(southYellow, LOW);
  digitalWrite(southRed, HIGH);
  digitalWrite(northRed, LOW);
}
