# HW-401A
Portable Handheld Lithium Battery Spot Welding Machine

------

In case someone buys this device and it is defective, this repository has some information.

This device was purchased on the [AliExpress](https://www.aliexpress.com/item/1005005807287144.html) website, but was received defective.
- A 1uF capacitor was missing (VCAP) and the USB connector was inoperative.
- - When plugging in the charger, no LEDs lit up. After changing the USB connector, a red LED lit up.
- - When pressing the power button, only 1 blue LED lit up, but the LED turned off when the button was released. After soldering the 1uF capacitor, other LEDs remained lit.
- The battery must be charged to test. A 470 Ohm resistor can be used to test, (touch each resistor terminal to each electrode), on an oscilloscope it is possible to see the pulse occur (but perhaps just an LED with a 470 Ohm resistor in series can be used to observe the operation).

The STM8S003F3P6 MCU firmware is not accessible (it is read protected, see tips [here](https://github.com/rtek1000/W1209-firmware-modified/tree/master/W1219)) but an alternative firmware can be made easily.

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/STM8S003F3P6.jpeg)

For tips on creating firmware, see this [project](https://github.com/rtek1000/W1209-firmware-modified) for the W1209 board.

The MCU monitors the state of the electrodes, which have a pull-down resistor. When a short circuit occurs in the electrodes, a pulse is triggered (each pulse can be from 20ms to 60ms, in steps of 10ms for each LED). The battery is monitored through voltage, see image below with voltage indications.

The charger is a TP4056 IC, the battery appears to have no protection, be careful not to allow a short circuit to occur on the battery poles.

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/Image1.png)

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/Image2.png)

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/Board2.jpg)

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/Board1.jpg)

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/LEDs.jpg)

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/Charger.jpg)

![img](https://raw.githubusercontent.com/rtek1000/HW-401A/main/Doc/Defects.jpg)

Note: This info is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
