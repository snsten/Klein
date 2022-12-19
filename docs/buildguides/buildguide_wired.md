# Klein Wired Build Guide

---

## Table of contents

- [Overview](#overview)
- [Version Info](#version-info)
- [Parts List](#parts-list)
- [Tools Required](#tools-required)
- [Tutorials](#tutorials)
- [Build Steps](#build-steps)
  - [Diodes](#diodes)
  - [Switch Sockets](#switch-sockets)
  - [Microcontroller](#microcontroller)
  - [TRRS](#TRRS)
- [Optional](#optional)
  - [Rotary Encoders](#rotary-encoder)
  - [OLED](#oled)
  - [Trackpad](#trackpad)
  - [Reset Switch](#reset-switch)
- [Assembly](#assembly)
  - [SwitchPlate](#switchplate)
  - [Case assembly](#case-assembly)
  - [Firmware](#firmware)
- [TODO](#todo)

---

## Overview

PCB Layout and orientation

### Front / Right Side of PCB

![Klein Front ](/docs/images/buildguide/KLEIN.v1.0.F.png)

### Back / Left Side of PCB

![Klein Back ](/docs/images/buildguide/KLEIN.v1.0.B.png)

## Version Info

- Wired version works with Pro Micro and KB2040.
- Should work with other RP2040 boards with minor modifications to firmware.
- The KB2040 firmware doesn't support Audio Buzzer.

## Parts List

See [BOM](https://github.com/snsten/Klein/tree/main/BOM) directory

## Tools Required

- Soldering Station / Iron
- Electrical Wire Nipper (Useful to cut diode/resistor legs)
- Precision Tweezer like [these](https://en.goot.jp/products/detail/ts_15) (For SMD diode/switches placement)
- Masking Tape to hold components in place while soldering
- Optional Flux for Trackpad connector

## Tutorials

There are lot of soldering tutorials available online.
For SMD parts I recommend [this](https://www.youtube.com/watch?v=hoLf8gvvXXU).

For socketing of microcontroller see the guides at [40percent.club](https://www.40percent.club/p/socketing-pro-micro.html) or [splitkb docs](https://docs.splitkb.com/hc/en-us/articles/360011263059).

For prepration of Trackpad see this guide at [ Keycapsss](https://github.com/Keycapsss/cirque-trackpad) or [beekeeb](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/).

---

## Build Steps

### Diodes

Diode are placed on the same side of PCB as hotswap sockets.

Throughole or SMD type diodes can be used. Diodes are polarized so keep the direction in mind.

|                 Diode symbols                 |                               Diode symbols on IBOM and the PCB                                |       SMD Diode in SOD 123 package       |              Through Hole Diode               |
| :-------------------------------------------: | :--------------------------------------------------------------------------------------------: | :--------------------------------------: | :-------------------------------------------: |
| ![](/docs/images/buildguide/DIODE-Signal.jpg) | ![](/docs/images/buildguide/KLEIN.v1.0.F_DIODE.png) ![](/docs/images/buildguide/PCB_Diode.JPG) | ![](/docs/images/buildguide/SOD-123.png) | ![](/docs/images/buildguide/1N4148-Diode.jpg) |

Using the line match the symbol with the actual diode before soldering.

|            Tin the Diode Pads             |      Reheat the pads to solder the Diodes       |
| :---------------------------------------: | :---------------------------------------------: |
| ![](/docs/images/buildguide/DiodeTin.JPG) | ![](/docs/images/buildguide/DiodePlacement.JPG) |

---

### Switch Sockets

Either MX, Choc or both compatible sockets can be used.
You can tin the pads with solder and then reheat to connect the sockets.
Or you can heat the socket, pad directly and solder.

|            Tin the Socket Pads            |  Reheat the pads to solder the Sockets  |
| :---------------------------------------: | :-------------------------------------: |
| ![](/docs/images/buildguide/DiodeTin.JPG) | ![](/docs/images/buildguide/Socket.JPG) |

---

### Microcontroller

- It is recommended to socket your microcontroller.
- The microcontroller position for Pro Micro is marked on the PCB as enclosed box.

  | Prepare the IC socket by cutting top part  |   Use Masking Tape to fix the socket in Place   |         Solder all the pins of the socket         |
  | :----------------------------------------: | :---------------------------------------------: | :-----------------------------------------------: |
  | ![](/docs/images/buildguide/IC_Socket.JPG) | ![](/docs/images/buildguide/IC_Socket_Mask.JPG) | ![](/docs/images/buildguide/IC_Socket_Solder.JPG) |

- Do the same for left side keeping the PIN orientation in check.

---

### TRRS

Note: To connect the two halves use 4-pole TRRS and not the 3-pole TRS cable. TRS cable is not supported and could damage the keyboard.

|            Bridge the TRRS Jumper            | Using tweezer bend the TRRS Jack pins as the second jack as shown in image |
| :------------------------------------------: | :------------------------------------------------------------------------: |
| ![](/docs/images/buildguide/TRRS_Jumper.JPG) |                   ![](/docs/images/buildguide/TRRS.JPG)                    |

TRRS Jack used is a surface mounted component but we will solder it as through hole.

| Place the TRRS Jack matching pins on the PCB |  Use Masking Tape to fix the jack in place  |        Solder the 4 pins of the jack         |
| :------------------------------------------: | :-----------------------------------------: | :------------------------------------------: |
| ![](/docs/images/buildguide/TRRS_Placed.JPG) | ![](/docs/images/buildguide/TRRS_Taped.JPG) | ![](/docs/images/buildguide/TRRS_Solder.JPG) |

- Do the same for left side keeping the PIN orientation in check.

---

## Optional

### Rotary Encoders

If you use MX or Choc choose rotary encoder based on the height:

- For MX with MT3/SA profile you can use the encoder specified in BOM which has an actuator length of 20mm.
- For Choc or MX with medium/low profile keycaps something like EC11N1524402 or similar which have actuator length of 15mm will be better.
- EC12 can also be used without the switch functionality.

This is personal preference so any option is fine.

|           Prepare the Encoder            |           Carefully place the Encoder           | Solder the 2 big mounting pins first then the rest of pins |
| :--------------------------------------: | :---------------------------------------------: | :--------------------------------------------------------: |
| ![](/docs/images/buildguide/Encoder.JPG) | ![](/docs/images/buildguide/Encoder_Seated.JPG) |      ![](/docs/images/buildguide/Encoder_Solder.JPG)       |

---

### OLED

Note: OLED has some clearance issue with pro micro sockets. You can check by placing the sockets and OLED before soldering to confirm. Will be fixed in next revision.

It is required to bridge the Jumpers if you want to use the Oled display.

Bridge the 4 jumper labelled "Jumper for L/R" for Left and Right hand respectively at the position in shown in image. [](https://htmlpreview.github.io/?https://github.com/snsten/Klein/blob/main/BOM/ibom.html)

![Jumpers](/docs/images/buildguide/KLEIN.v1.0.F_JUMPERS.png)

---

### Trackpad

Not the easiest part to solder, try to use <= 0.5 mm solder wire along with a pointed tip or small chiesel tip for drag soldering.
Use lots of flux and avoid bridging between pins.

Use a multimeter to check if all connections are working and there is no short between adjacent pins.

#### Trackpad Modification

- Desolder/Remove R1 as it is required for I2C communiaction.
- If you are using Pro Micro remove R7 and R8 as well. If your microcontroller(like KB2040) can provide 3.3V then it is not required.
- Alternatively you can cut off these resistor with electric nippers.
- Be careful not to remove adjacent components.

  | Trackpad resistors to remove. Image from guide by [ Keycapsss](https://github.com/Keycapsss/cirque-trackpad). |
  | :-----------------------------------------------------------------------------------------------------------: |
  |       ![](https://raw.githubusercontent.com/Keycapsss/cirque-trackpad/master/img/resistor-i2c-5v-1.jpg)       |

  Add two pull up resistor of 4.7K ohms, orientation doesn't matter with resistors.

  |     Add two 4.7K resistor at position shown in IBOM     |                  Two 4.7K resistor soldered on PCB |
  | :-----------------------------------------------------: | -------------------------------------------------: |
  | ![](/docs/images/buildguide/Trackpad_Resistor_IBOM.JPG) | ![](/docs/images/buildguide/Trackpad_Resistor.JPG) |

#### Soldering the FPC connector.

| Tin the pads of FPC connector J1 on PCB  | Use tape to fix the FPC connector and solder each pin | The ribbon cable can be connected by pulling the notch |          Close it by pushing the notch           |
| :--------------------------------------: | :---------------------------------------------------: | :----------------------------------------------------: | :----------------------------------------------: |
| ![](/docs/images/buildguide/FPC_Tin.JPG) | ![](/docs/images/buildguide/FPC_Connector_Solder.JPG) |  ![](/docs/images/buildguide/Trackpad_Connection.JPG)  | ![](/docs/images/buildguide/FPC_Conn_Closed.JPG) |

#### Trackpad Assembly

| Use Double Sided Tape on the lower half of the Trackpad | Carefully place the Trackpad in the assembly using double sided tape | Connect the ribbon cable from previos step with the assembly |
| :-----------------------------------------------------: | :------------------------------------------------------------------: | :----------------------------------------------------------: |
|   ![](/docs/images/buildguide/Trackpad_Assembly.JPG)    |           ![](/docs/images/buildguide/Trackpad_Taped.JPG)            |       ![](/docs/images/buildguide/Trackpad_Ribbon.JPG)       |

| Trackpad Assembly will fit on PCB using 4x M3 10mm Standoff and 3x M3 5mm screws |      Use M3 standoff in 4 corners as shown below       | Place the trackpad mount on top of standoff and use screws to fix it |
| :------------------------------------------------------------------------------: | :----------------------------------------------------: | :------------------------------------------------------------------: |
|                 ![](/docs/images/buildguide/Trackpad_Mount.JPG)                  | ![](/docs/images/buildguide/Trackpad_Mount_Placed.JPG) |       ![](/docs/images/buildguide/Trackpad_Mount_Screwed.JPG)        |

Fourth screw is not required as it will interfere with trackpad scroll action.

---

### Reset Switch

Tin the pads with some solder and the solder the Reset Switch by the side pads first and then the main connections using generous amounts of flux.

---

## Assembly

### Switchplate, Switches and Keycaps

Switchplates are avialable in case directory in [repo](https://github.com/snsten/Klein/tree/main/Case).

Insert few switches in switchplate then gently place it on top of PCB aligning with the hotswap sockets.

Place rest of the switches one by one on switchplate without applying too much force.

After all the switches are placed you can place the keycaps on top of them.

### Case assembly

Case files are available [here](https://github.com/snsten/Klein/tree/main/Case).

### Firmware

The firmware is available [here](https://github.com/snsten/Klein-qmk).

---

## TODO

&#9744; Add detailed parts list

&#9744; Add images for rest of the steps
