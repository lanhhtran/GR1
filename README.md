# GR1
Tran Thi Lan Anh 20215180
# Introduction for ESP 32
![esp32 supermini](https://www.google.com/search?q=%E1%BA%A3nh+esp32+supermini&tbm=isch&ved=2ahUKEwi5q_P145aDAxUBW_UHHZIhAOcQ2-cCegQIABAA&oq=%E1%BA%A3nh+esp32+supermini&gs_lcp=CgNpbWcQA1AAWK8eYK8haABwAHgAgAHiAYgBvgiSAQU1LjMuMZgBAKABAaoBC2d3cy13aXotaW1nwAEB&sclient=img&ei=8BJ_ZbnzGIG21e8PksOAuA4&bih=695&biw=1536#vhid=skdxO2iv0bh7aM&vssid=3981:om38CsxA6hp5PM)
# ESP32
This source code allows you to make the ESP32 flashing lights, vibrating the motor and act as a Bluetooth Mouse and keyboard
# Example
```
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
```
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
