# EP01 — GPIO Input and Output

Learn the fundamentals of digital input and output using Arduino Uno.

---

## Topics
- digitalWrite()
- digitalRead()
- pinMode()
- INPUT_PULLUP
- Push Button
- LED Control

---

## Hardware

| Component     | Quantity |
| ------------- | -------- |
| Arduino Uno   | 1        |
| LED           | 1        |
| Resistor 220Ω | 1        |
| Push Button   | 1        |


---

## Wiring

Comming soon...

---

## Arduino Code

```c++
const int ledPin = 13;
const int buttonPin = 2;

void setup(){
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin, INPUT_PULLUP);
}

void loop(){
    if (digitalRead(buttonPin) == LOW)
    {
        digitalWrite(ledPin, HIGH);
    }
    else
    {
        digitalWrite(ledPin, LOW);
    }
}
```

---

## Concepts Learned
- GPIO
- Digital Input
- Digital Output
- Internal Pull-up
- Active LOW Logic