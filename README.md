# Klein Keyboard

Klein keyboard is a 36 keys, columnar staggered, split keyboard named after [Felix Klein](https://en.wikipedia.org/wiki/Felix_Klein)

![Klein ](/docs/images/1.JPG)

---

## Features

- Column Staggered
- Bluetooth compatible with power switch
- Seeed Studio XIAO / Pro Micro / nice!nano / kb2040 compatible
- Hotswap MX and Choc switches support
- Trackpad support with JST cable and direct wiring
- SMD and through hole diode footprint

## Versions

Supports multiple options of micro controller and sensors. Broadly divided in two types:

### Wireless

- Can be made with Seeed Studio XIAO-BLE
- Supports either rotary encoder or OLED/Touchpad
- Battery connectors JST and THT

### Wired

- Can use Seeed Studio XIAO-RP2040
  - Supports either rotary encoder or OLED/Touchpad
- With any pro micro based boards
  - Can support encoders, OLED/Touchpad, Buzzer and Haptics

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
├── Case                           <- Case stl Files
├── docs
│   └── images
├── Logo
├── PCB
│   ├── Gerbers
│   │   └── ProtoGerbers.zip       <- PCB Files
└── README.md
```

## BOM

It is available in BOM directory as csv file and [interactive HTML BOM](https://htmlpreview.github.io/?https://github.com/snsten/Klein/blob/main/BOM/ibom.html)

## PCB

The gerbers file are in the PCB/Gerbers Directory

## Todo

- Add Build Guide
- Add Touchpad related 3D Models
- Software support for Touchpad/OLED

## Firmware

- [ZMK shield](https://github.com/snsten/Klein-zmk) for Klein with rotary encoder support. Keymap is just for test modify accordingly.

## Refrences

These projects inspired and helped in making Klein:

- [Lily58](https://github.com/kata0510/Lily58) (Hotswap Footprints)
- [Dilemma](https://github.com/Bastardkb/dilemma) (Trackpad Mount, Design)
- [KLOR](https://github.com/GEIGEIGEIST/KLOR) (Haptics Footprints, Design)
- [Claw44](https://github.com/yfuku/claw44) (Design)
