# Klein Keyboard

Klein keyboard is a 36 keys, columnar staggered, split keyboard named after [Felix Klein](https://en.wikipedia.org/wiki/Felix_Klein)

![Klein ](/docs/images/1.JPG)

---

## Features

- Column Staggered
- Bluetooth compatible with power switch
- Seeed Studio XIAO-BLE / Pro Micro / nice!nano\* / KB2040 / RP2040(boards with Pro Micro pinout) compatible
- Hotswap MX and Choc switches support
- Trackpad support with FPC cable and direct wiring
- Reversible SMD and through hole diode footprint

> \* nice!nano firmware not available at the moment.

## Versions

Supports multiple options of micro controller and sensors.

| Features Supported                       | Microcontroller | Firmware available                         | Wired | Wireless |
| ---------------------------------------- | --------------- | ------------------------------------------ | ----- | -------- |
| Encoder or OLED                          | XIAO-BLE        | [Yes](https://github.com/snsten/Klein-zmk) |       | Yes      |
| Encoder, OLED, TouchPad, Buzzer, Haptics | Pro Micro       | [Yes](https://github.com/snsten/Klein-qmk) | Yes   |          |
| Encoder, OLED, TouchPad, Buzzer, Haptics | KB2040/RP2040   | [Yes](https://github.com/snsten/Klein-qmk) | Yes   |          |
| Encoder and OLED                         | nice!nano       | No (Planned)                               |       | Yes      |

Broadly divided in two types:

### Wireless

- Can be made with Seeed Studio XIAO-BLE
- Supports either rotary encoder or OLED
- Battery connectors JST and THT

Wireless touchpad is currently not supported in ZMK.

### Wired

- With any Pro Micro based boards
  - Can support encoders, OLED, Touchpad, Buzzer and Haptics

---

### Keyboard Images

PCB with both Choc and MX switches
![Klein Choc Switches](/docs/images/Choc_switch.JPG)

Low Profile Choc version
![Klein MX Choc Switches](/docs/images/ChocBuild.JPG)

MX version
![Klein MX Choc Switches](/docs/images/MXBuild.JPG)

---

## Repo Layout and Files

```
.
├── BOM
│   ├── BOM-3235-SEEED.csv         <- BOM
│   └── ibom.html
├── Case
│   └── *.stl                      <- Case stl Files
│   └── Prototype                  <- FreeCad project files (Not tested)
│       └── SwitchPlateFR4         <- SwitchPlate PCB files (Not tested)
├── docs
│   └── images
├── Logo
├── PCB
└── README.md
```

## BOM

It is available in BOM directory as csv file and [interactive HTML BOM](https://htmlpreview.github.io/?https://github.com/snsten/Klein/blob/main/BOM/ibom.html)

## Build Guide

- Wired build [guide](https://github.com/snsten/Klein/blob/main/docs/buildguides/buildguide_wired.md)
- Wireless build [guide](https://github.com/snsten/Klein/blob/main/docs/buildguides/buildguide_wireless.md)

## Todo

- Add Build Guide
- Add Touchpad related 3D Models
- Software support for Touchpad/OLED

## Firmware

- [ZMK shield](https://github.com/snsten/Klein-zmk) for Klein with rotary encoder support.
- [QMK Firmware](https://github.com/snsten/Klein-qmk) for Pro Micro with touchpad support.

## Refrences

These projects inspired and helped in making Klein:

- [Lily58](https://github.com/kata0510/Lily58) (Hotswap Footprints)
- [Dilemma](https://github.com/Bastardkb/dilemma) (Trackpad Mount, Design)
- [KLOR](https://github.com/GEIGEIGEIST/KLOR) (Haptics Footprints, Design)
- [Claw44](https://github.com/yfuku/claw44) (Design)
