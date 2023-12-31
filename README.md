# GR1
Tran Thi Lan Anh 20215180
# Introduction for ESP 32
![ESP32 supermini](https://github.com/lanhhtran/GR1/assets/117920786/23f3ab52-4368-4660-9157-a7627f85872f)

ESP32 is a low-cost System on Chip (SoC) Microcontroller from Espressif Systems, the developers of the famous ESP8266 SoC. It is a successor to ESP8266 SoC and comes in both single-core and dual-core variations of the Tensilica's 32-bit Xtensa LX6 Microprocessor with integrated Wi-Fi and Bluetooth.

**This source code allows you to make the ESP32 flashing lights, vibrating the motor and act as a Bluetooth Mouse and keyboard**
# Hello world
This code simply puts the HIGH and LOW values on pin 2 respectively, and the light will flash according to the signal.
```cpp
/**
 * This example flashing led by esp32
 */
void setup() {
    pinMode(2, OUTPUT);
}
void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(2,HIGH);
  delay(1000);
  digitalWrite(2,LOW);
   delay(1000);
 }
```

![led](https://github.com/lanhhtran/GR1/assets/117920786/57444b8c-7938-4ff9-af70-113bd5e123a5)
# Bluetooth Mouse
This code allows you to make the ESP32 act as a Bluetooth Mouse and control what it does. E.g. move the mouse, scroll, make a click etc
```cpp
/**
 * This example turns the ESP32 into a Bluetooth LE mouse that scrolls down every 2 seconds.
 */
#include <BleMouse.h>

BleMouse bleMouse;

void setup() {
  Serial.begin(115200);
  Serial.println("Starting BLE work!");
  bleMouse.begin();
}

void loop() {
  if(bleMouse.isConnected()) {
    Serial.println("Scroll Down");
    bleMouse.move(0,0,-1);
  }
  delay(2000);
}
```
![mouse](https://github.com/lanhhtran/GR1/assets/117920786/cb7c3c04-086c-44d5-9826-209994fce075)
# Vibration motor
To vibrate the motor, we simply apply 1/0 voltage to one pin.
```cpp
void setup() {
  // put your setup code here, to run once:
  pinMode(2, OUTPUT);
}
void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(2, HIGH);
  delay(2000);
  digitalWrite(2, LOW);
  delay(600);
  digitalWrite(2, HIGH);
  delay(2000);
  digitalWrite(2, LOW);
  delay(600);

  delay(5000);
}
```
![vibr](https://github.com/lanhhtran/GR1/assets/117920786/fd279ca3-4b45-44be-9892-6e8773253c75)
