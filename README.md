# GR1
Tran Thi Lan Anh 20215180
# Introduction for ESP 32
![ESP32 supermini](https://github.com/lanhhtran/GR1/assets/117920786/23f3ab52-4368-4660-9157-a7627f85872f)
The ESP32 is a series of chip microcontrollers developed by Espressif.
Why are they so popular? Mainly because of the following features:
Low-cost: you can get an ESP32 starting at $6, which makes it easily accessible to the
general public;
• Low-power: the ESP32 consumes very little power compared with other micro-
controllers, and it supports low-power mode states like deep sleep to save power;
• Wi-Fi capabilities: the ESP32 can easily connect to a Wi-Fi network to connect
to the internet (station mode), or create its own Wi-Fi wireless network (access
point mode) so other devices can connect to it—this is essential for IoT and Home
Automation projects—you can have multiple devices communicating with each
other using their Wi-Fi capabilities;
• Bluetooth: the ESP32 supports Bluetooth classic and Bluetooth Low Energy (BLE)—which
is useful for a wide variety of IoT applications;
• Dual-core: most ESP32 are dual-core— they come with 2 Xtensa 32-bit LX6 mi-
croprocessors: core 0 and core 1.
• Rich peripheral input/output interface—the ESP32 supports a wide variety of
input (read data from the outside world) and output (to send commands/signals
to the outside world) peripherals like capacitive touch, ADCs, DACs, UART, SPI,
I2C, PWM, and much more.
• Compatible with the Arduino “programming language”: those that are already
familiar with programming the Arduino board, you’ll be happy to know that
they can program the ESP32 in the Arduino style.
• Compatible with MicroPython: you can program the ESP32 with MicroPython
firmware, which is a re-implementation of Python 3 targeted for microcontrollers
and embedded systems
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
