
# EP05 — PWM Basics

เรียนรู้พื้นฐานของ PWM ใน Arduino Uno และ Embedded Systems

![Thumbnail](images/thumbnail-ep5.png)

---

# PWM คืออะไร?

PWM ย่อมาจาก: Pulse Width Modulation คือ การสร้างสัญญาณ Digital ที่เปิดและปิดเร็วมาก เพื่อจำลองค่า Analog

แม้ Arduino Uno จะไม่มี DAC จริง แต่ PWM สามารถทำให้:
- LED ดูเหมือนหรี่แสงได้
- มอเตอร์หมุนเร็วช้าต่างกันได้
- ควบคุมกำลังไฟฟ้าได้

---

# แนวคิดสำคัญ

PWM ไม่ได้เปลี่ยนแรงดันจริง แต่เปลี่ยน: ระยะเวลา HIGH และ LOW

เช่น:
- HIGH นาน → พลังงานมาก
- LOW นาน → พลังงานน้อย

---

# Topics

- PWM Basics
- analogWrite()
- Duty Cycle
- LED Brightness Control
- PWM Frequency
- Embedded PWM Concepts

---

# ทำไม PWM ถึงสำคัญ?

PWM ถูกใช้แทบทุกระบบใน Embedded Systems เช่น:
- LED Dimmer
- Motor Speed Control
- Fan Control
- Servo Motor
- Power Electronics
- Industrial Automation
- Embedded Control Systems

---

# Hardware

| Component | Quantity |
|---|---|
| Arduino Uno | 1 |
| LED | 1 |
| Resistor 220Ω | 1 |
| Breadboard | 1 |

---

# PWM Pins ใน Arduino Uno

PWM Pins: 3, 5, 6, 9, 10, 11 บนบอร์ดจะมีสัญลักษณ์: `~` กำกับไว้

---

# Code Example 1 — Basic PWM

ตัวอย่างนี้ควบคุมความสว่าง LED

```cpp
const int ledPin = 9;

void setup(){
  pinMode(ledPin, OUTPUT);
}

void loop(){
  analogWrite(ledPin, 50);
}
```

---

# analogWrite() คืออะไร?

```cpp
analogWrite(pin, value);
```

ใช้สร้าง PWM Signal ค่า: `0 - 255` โดย:
- 0 = ดับ
- 255 = สว่างสุด

---

# Duty Cycle คืออะไร?

Duty Cycle คือ:

เปอร์เซ็นต์เวลาที่สัญญาณเป็น HIGH

ตัวอย่าง:
- 50% = HIGH ครึ่งหนึ่ง
- 75% = HIGH นานกว่า LOW
- 10% = HIGH สั้นมาก

---

# Visualization

![duty cycle](images/duty_cycle.png)

---

# Code Example 2 — Fade LED

ตัวอย่างนี้ค่อย ๆ เพิ่มและลดความสว่าง LED

```cpp
const int ledPin = 9;
int brightness = 0;
int fadeAmount = 5;

void setup(){
  pinMode(ledPin, OUTPUT);
}

void loop(){
  analogWrite(ledPin, brightness);
  brightness = brightness + fadeAmount;
  if (brightness <= 0 || brightness >= 255){
    fadeAmount = -fadeAmount;
  }
  delay(30);
}
```

---

# ทำไม PWM สำคัญกับ Embedded Systems?

PWM คือพื้นฐานของ:
- Motor Driver
- Inverter
- Servo Control
- BLDC Control
- Industrial Automation
- Power Electronics

<br>

แม้แต่ระบบ:
- EV
- Solar Inverter
- Industrial Motor

ก็ใช้ PWM

---

# Concepts Learned

- PWM Basics
- analogWrite()
- Duty Cycle
- LED Brightness Control
- Embedded PWM Concepts

---

# Real-World Applications

- LED Dimmer
- Motor Speed Control
- Fan Controller
- Servo Control
- Industrial Automation
- Power Control

---

# Next Episode

➡ EP06 — ADC Basics

---

# GitHub Repository

https://github.com/KOPE-SOLUTION/arduino-uno-embedded-roadmap
