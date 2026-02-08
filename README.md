# 🎙️ CODTECH Internship – Task 4

## Speech Recognition Based Device Control System Using Arduino

### Internship Program: **CODTECH**

**Task:** Build a basic speech recognition system for command-based control of devices using an embedded board
**Instructions:** Speech Recognition System
**Deliverables:** System Design, Source Code, and Working Demo

---

## 📌 Project Description

This project demonstrates a **basic speech recognition system** using an **Arduino Uno**.
Voice commands are converted into **text commands** using a speech-to-text application and sent to the Arduino via **Serial/Bluetooth communication**.

Based on the received commands, the Arduino controls multiple devices such as a **light** and a **fan**.

The project fulfills all requirements specified in **CODTECH Internship Task-4**.

---

## 🎯 Objectives

* Implement speech-based command control
* Interface Arduino with serial/speech input
* Control multiple devices using voice commands
* Demonstrate embedded system automation using speech recognition

---

## 🔧 Hardware Components

| Component                   | Quantity    |
| --------------------------- | ----------- |
| Arduino Uno                 | 1           |
| Relay Module (2-Channel)    | 1           |
| Light (Bulb / LED for demo) | 1           |
| Fan (Motor / LED for demo)  | 1           |
| Jumper Wires                | As required |
| Breadboard                  | 1           |
| Smartphone (Speech App)     | 1           |

---

## 🔌 Circuit Connections

### Device Connections

* **Light Relay IN** → Arduino Pin **8**
* **Fan Relay IN** → Arduino Pin **9**
* **Relay VCC** → 5V
* **Relay GND** → GND

*(Serial communication used for speech command input)*

---

## 🧠 Working Principle

* User speaks a command such as **“light on”** or **“fan off”**
* Speech-to-text app converts voice to text
* Text command is sent to Arduino via Serial
* Arduino processes the command
* Corresponding device is switched ON or OFF

---

## 💻 Arduino Source Code

```cpp
String command;

int light = 8;   
int fan = 9;     

void setup() {
  pinMode(light, OUTPUT);
  pinMode(fan, OUTPUT);

  Serial.begin(9600);
  Serial.println("Speech Recognition System Started");
  Serial.println("Commands:");
  Serial.println("light on / light off");
  Serial.println("fan on / fan off");
}

void loop() {
  if (Serial.available()) {
    command = Serial.readString();
    command.trim();

    if (command == "light on") {
      digitalWrite(light, HIGH);
      Serial.println("Light ON");
    }
    else if (command == "light off") {
      digitalWrite(light, LOW);
      Serial.println("Light OFF");
    }
    else if (command == "fan on") {
      digitalWrite(fan, HIGH);
      Serial.println("Fan ON");
    }
    else if (command == "fan off") {
      digitalWrite(fan, LOW);
      Serial.println("Fan OFF");
    }
    else {
      Serial.println("Invalid Command");
    }
  }
}
```

---

## 🔌 System Design / Circuit Diagram

![Circuit Diagram](https://github.com/radhikasatavkar12-tech/Task4/blob/main/task%204.png)

---

## 📟 Output Demonstration

### Serial Monitor Output

```
Speech Recognition System Started
Commands:
light on / light off
fan on / fan off
Light ON
Fan OFF
```

* Light turns ON/OFF using voice command
* Fan turns ON/OFF using voice command

---

## 📟 Output Demonstration

![Working Demo](https://github.com/radhikasatavkar12-tech/Task4/blob/main/task%204%20output.png)

---

## ✅ Task Completion Checklist

✔ Speech recognition implemented
✔ Command-based device control
✔ Multiple devices controlled
✔ System design completed
✔ Working demo verified

---

## 🏁 Conclusion

This project successfully demonstrates a **speech recognition-based control system** using Arduino.
It enables hands-free operation of devices and showcases the integration of speech recognition with embedded systems, fulfilling all requirements of **CODTECH Internship Task-4**.
say the word 👍
