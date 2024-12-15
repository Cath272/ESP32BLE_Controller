## Introduction

ESP32BLE_Controller is a ESP32 based project that aimes to make an affortable controller.

The project idea came around when i wanted to incorporate pcb design with a esp32 microcontroller.
The controller uses the [ESP32 XINPUT library](https://github.com/Mystfit/ESP32-BLE-CompositeHID) and can be used on any Bluetooth device that can accept xinput devices.

## General description

The player turns on the controller and connects it to a pc/phone and it just works as a XINPUT device and can control any game/sofware that implements the xinput API

### Block diagram
![image](https://github.com/user-attachments/assets/97f3f00f-d9cd-474c-944b-84ce67c850cb)


## Hardware Design

### ESP32 Wroom Module
  This project is based on the ESP32-WROOM-32 Module that incorporates an Espressif ESP32 Dual Core 32bit microcontroller with 4MB of Flash Storage, an crystal oscilator, decoupling capacitors and an 2.4Ghz Antena for Wi-Fi and Bluetooth.
  I have chosen this module beacause of it's ease of use, the familiarity i have with it and it low price (around 2.5EUR).  
  
### USB C 14pin port
  USB port for programing and for providing 5V power. It uses 2 5.1K resistors on the CC lines so it can use USB PD and request 5V from it. (Aka use a Type C to Type C cable)
### TPS63020 - High Efficiency Single Inductor Buck-Boost Converter
  Buck Boost Converter that converts 5V from USB to the 3.3V used by the Wroom Module and the CH343p Ic. It also needs an 1.5uH Inductor and filtering caps on the input and output. I chose this Ic because of its High Efficiency. 

### CH343P USB to High-Speed Serial Chip
  USB to High Speed Serial Ic for programming the ESP32. It is made by WCH and i mainly chose it beacause of its small form QFN package and its low price. 

### 10 Buttons
  10 SMD Buttons connected to GPIOs of the ESP32. 
### 2 BC817 Transistors
  2 Transistors used for the auto programming circuit
  
### 2 LEDS (RED for Power and BLUE IO2 configurable)
  
### Schematic:
![image](https://github.com/user-attachments/assets/a4106942-4592-48a9-bb1f-f15289bb0bf0)

### Bill of materials 
| Component           |         Image                                                                                         |         Model  |           Pcs | Price           | Link          |
| -------------       |                                                                                        -------------  | -------------  | ------------- | --------------- | ------------- |
| ESP32 Wroom Module  |  ![199600425](https://github.com/user-attachments/assets/52b7885a-9f79-485b-bd1f-54983a96c8ea)        | ESP32-WROOM-32 | 1             | 2.5EUR          |   [Aliexpress](https://www.aliexpress.com/item/1005006579469362.html?spm=a2g0o.order_list.order_list_main.5.1cc41802YGhEhy)  |
| USB C 16pin port    | ![Untitled](https://github.com/user-attachments/assets/9962f6f7-9011-42e6-a1d0-4a7132164872)          | USB C 16 PIN   | 1             | 4.85EUR/100Pcs, 0.05EUR/Pcs | [Aliexpress](https://www.aliexpress.com/item/1005006072023656.html?spm=a2g0o.order_list.order_list_main.27.1cc41802YGhEhy) |
|Buck Boost Coverter  | ![Screenshot ](https://github.com/user-attachments/assets/268663cf-1794-42c4-8324-cbcd939803ec)       |   TPS63020     | 1             |0.35EUR          | [Aliexpress](https://www.aliexpress.com/item/1005006228616468.html?spm=a2g0o.order_list.order_list_main.76.1cc41802YGhEhy) |
|USB To Serial        | ![images](https://github.com/user-attachments/assets/ea21eece-a85f-4848-8467-17d25432dda0)            | CH343P         | 1             | 0.8EUR          | [Aliexpress](https://www.aliexpress.com/item/1005006879961854.html?spm=a2g0o.order_list.order_list_main.81.1cc41802YGhEhy) |       
|Buttons              | ![ Closed](https://github.com/user-attachments/assets/0d621e56-ae50-4061-b46b-14ff2eb89069)           | Metal Dome 3.7*3.7*0.35mm | 10 | 1.5EUR          | [Aliexpress](https://www.aliexpress.com/item/4001125555481.html?spm=a2g0o.order_list.order_list_main.90.1cc41802YGhEhy) |
|NPN Transistor       | ![ 502](https://github.com/user-attachments/assets/af2ec429-4179-42b6-89f4-525b2ef06154)              |   BC817        | 2             | 0.015EUR/Pcs    | [Aliexpress](https://www.aliexpress.com/item/4001032215515.html?spm=a2g0o.order_list.order_list_main.138.1cc41802YGhEhy) |


Other Components are from Components Sample Books that include many values of [Resistors](https://www.aliexpress.com/item/1005006169072137.html?spm=a2g0o.order_list.order_list_main.185.1cc41802YGhEhy), [LEDs](https://www.aliexpress.com/item/1005003580299883.html?spm=a2g0o.order_list.order_list_main.174.1cc41802YGhEhy) and [Capacitors](https://www.aliexpress.com/item/1005005456060166.html?spm=a2g0o.order_list.order_list_main.178.1cc41802YGhEhy) that i bought before.


###PCB

The PCB was created by me, using KICAD 8.0

Front:
![image](https://github.com/user-attachments/assets/a0660dbb-f35f-414c-917e-92d4e413bb73)
![image](https://github.com/user-attachments/assets/7c42c54c-1630-48a3-a9dd-593a00689644)

Back:
![image](https://github.com/user-attachments/assets/36146674-4566-495c-a062-3a94a8811b2f)
![image](https://github.com/user-attachments/assets/088a4dfe-75ec-4bb1-b42e-e56ef21fef04)



## Software Design

#TO DO 

## Results


## Resources
[ESP32 XINPUT library](https://github.com/Mystfit/ESP32-BLE-CompositeHID)

