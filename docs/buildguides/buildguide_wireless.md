# Klein Wireless Build Guide

---

## Table of contents

- [Overview](#overview)
- [Version Info](#version-info)
- [Parts List](#parts-list)
- [Tools Required](#tools-required)
- [Tutorials](#tutorials)
- [Build Steps](#build-steps)
  - [Diodes](#diy-version)
  - [Switch Sockets](#switch-sockets)
  - [Battery](#battery)
  - [Microcontroller](#microcontroller)
  - [Optional](#optional)
    - [Power Switch](#power-switch)
    - [Reset Switch](#reset-switch)
    - [Jumpers](#jumpers)
    - [Rotary Encoders](#rotary-encoder)
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

- Currently the wireless version is tested with XIAO-BLE only.
- Should work with nice!nano but haven't tested and implemented in ZMK yet.
- The wireless version doesn't support Trackpad, Haptics or Buzzer.

## Parts List

See [BOM](https://github.com/snsten/Klein/tree/main/BOM) directory

## Tools Required

- Soldering Station / Iron
- Electrical Wire Nipper (Useful to cut diode/resistor legs)
- Precision Tweezer like [these](https://en.goot.jp/products/detail/ts_15) (For SMD diode/switches placement)
- Masking Tape to hold components in place while soldering

## Tutorials

There are lot of soldering tutorials available online. For SMD parts I recommend [this](https://www.youtube.com/watch?v=hoLf8gvvXXU).

For socketing of microcontroller see the guides at [40percent.club](https://www.40percent.club/p/socketing-pro-micro.html) or [splitkb docs](https://docs.splitkb.com/hc/en-us/articles/360011263059).

---

## Build Steps

### Diodes

Diode should be placed on the same side of PCB as switches and opposite side of hotswap sockets.

Throughole or SMD type diodes can be used. Diodes are polarized so keep the direction in mind.

![Types of Diode](/docs/images/buildguide/DiodeAlign.png)

Using the line match the symbol with the actual diode before soldering.

![DIODE SYMBOL](/docs/images/buildguide/KLEIN.v1.0.F_DIODE.png)

### Switch Sockets

Either MX, Choc or both compatible sockets can be used.
You can tin the pads with solder and then reheat to connect the sockets.
Or you can heat the socket, pad directly and solder.

### Battery

The battery can be any 3.7V lipo like [these](https://www.lipobattery.us/tag/thickness-3mm/) keeping dimension and capacity in mind.

- Don't get anything with depth 4mm or above as they will be hard to fit.
- Tested with battery dimensions 26x10x3.5 mm and 200mAh capacity which fit below pcb or microcontroller.

You can connect battery directly to the +/- terminal on XIAO-BLE +/- pad, this method will bypass the switch.

or

Solder the female JST plug at position B1 see in [ibom](https://htmlpreview.github.io/?https://github.com/snsten/Klein/blob/main/BOM/ibom.html) on the PCB.

- Attach the Battery using JST connector.

### Microcontroller

- It is recommended to socket your microcontroller.
- The microcontroller position for XIAO is marked by the inverted triangle on PCB.

  ![XIAO SYMBOL](/docs/images/buildguide/KLEIN.v1.0.F_XIAO_ALIGN.png)

- For battery connection you need to solder wire from +PAD on XIAO-BLE to any of the 2 BAT+ pins marked with red box shown below.

  ![XIAO-PCB-Connection](/docs/images/buildguide/XIAO-PCB-Connection.png)

- Do the same for left side keeping the PIN orientation in check.

### Optional

#### Power Switch

Tin the pads with some solder and then solder the Power Switch by the side pads first and then the main connections using generous amounts of flux.

#### Reset Switch

Reset switch is for only Pro Micro footprint boards. If you want to make it work with XIAO another connection like the BAT+ has to be made from XIAO reset pad to RESET PINS on pro micro footprint.

Tin the pads with some solder and the solder the Reset Switch by the side pads first and then the main connections using generous amounts of flux.

#### Jumpers

Jumpers is required if you want to use

- Rotary encoder then bridge 2 ENC jumper at postion JP9, JP10 see [ibom](https://htmlpreview.github.io/?https://github.com/snsten/Klein/blob/main/BOM/ibom.html).
- Oled display then bridge 4 jumper for L/R at position see [ibom](https://htmlpreview.github.io/?https://github.com/snsten/Klein/blob/main/BOM/ibom.html).

![Jumpers](/docs/images/buildguide/KLEIN.v1.0.F_JUMPERS.png)

**Note: Only bridge one of these two at a time**, they share same pins route which will change based on closed jumper.

#### Rotary Encoders

If you use MX or Choc choose rotary encoder based on the height:

- For MX with MT3/SA profile you can use the encoder specified in BOM which has an actuator length of 20mm.
- For Choc or MX with medium/low profile keycaps something like EC11N1524402 or similar which have actuator length of 15mm will be better.

This is personal preference so any option is fine.

### Switchplate, Switches and Keycaps

Switchplates are avialable in case directory in [repo](https://github.com/snsten/Klein/tree/main/Case).

Insert few switches in switchplate then gently place it on top of PCB aligning with the hotswap sockets.

Place rest of the switches one by one on switchplate without applying too much force.

After all the switches are placed you can place the keycaps on top of them.

### Case assembly

Case files are available [here](https://github.com/snsten/Klein/tree/main/Case).

### Firmware

The firmware is available [here](https://github.com/snsten/Klein-zmk). Fork the repo and download the firmware zip file from Actions tab in Github.

---

## TODO

&#9744; Add detailed parts list

&#9744; Add images for rest of the steps

&#9744; Add instructions for nice!nano
