# GR1
Tran Thi Lan Anh 20215180
# Introduction for ESP 32
![ESP32 supermini](https://github.com/lanhhtran/GR1/assets/117920786/23f3ab52-4368-4660-9157-a7627f85872f)

The ESP32 is a series of chip microcontrollers developed by Espressif.
# ESP32
This source code allows you to make the ESP32 flashing lights, vibrating the motor and act as a Bluetooth Mouse and keyboard
# Example
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
