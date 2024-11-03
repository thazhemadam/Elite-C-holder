# splinterface

splinterface is an MCU holder, intended for use in both standalone and split builds.

## MCU Support

The following footprints are supported by the holder.

* [Elite-C footprint](https://deskthority.net/wiki/Elite-C)
* [nice!nano footprint](https://nicekeyboards.com/docs/nice-nano/pinout-schematic/#pinout)
* [Supermini nrf52840 footprint](https://github.com/joric/nrfmicro/wiki/Alternatives#supermini-nrf52840)

## Features

* [VIK](https://github.com/sadekbaroudi/vik) compliant
* Support for wireless and wired builds (see an example compatibility matrix [below](#compatibility-matrix-with-bastardkb-boards))
* Full-duplex communications support
* Dedicated pin for handedness (optional)
* Dedicated pin for RGB (optional)
* Criss-crossable pins for serial communication

### Wired Builds

* TRRS jack for split communications
* USBLC6-2P6 for ESD protection

### Wireless Builds

* JST-PH connector for connecting a battery
* EG1271 Slide Switches for power switch

## Compatibility Matrix with BastardKB Boards

|                | RGB | Wireless | RGB + Wireless [^1] |
|----------------|:---:|:--------:|:-------------------:|
| Skeletyl       | ✅   | ✅        | ✅                 |
| Charybdis Nano | ✅   | ✅        | ✅                 |
| TBK Mini       | ✅   | ✅ [^2]   | ✅ [^2][^3]        |
| Charybdis Mini | ✅   | ✅ [^2]   | ✅ [^2][^3]        |
| Scylla         | ✅   | ✅ [^3]   | ❌                 |
| Charybdis      | ✅   | ✅ [^3]   | ❌                 |

* Ribbon cable pinout (for the key matrix) compatible with BastardKB's [Dactyl](https://bastardkb.com/dactyls/) and [Charybdis](https://bastardkb.com/charybdis/) series' PCBs.
* Mounting holes are compatible with BastardKB's [Dactyl](https://bastardkb.com/dactyls/) and [Charybdis](https://bastardkb.com/charybdis/) series' cases.

## VIK Certification Card

| Category                | Response           |
| ----------------------- |:------------------:|
| FPC connector           | ✅                 |
| Breakout pins           | ❌                 |
| Supplies: SPI           | ✅                 |
| Supplies: I2C           | ✅                 |
| I2C on main PCB         | ❌                 |
| I2C pull ups            | N/A                |
| Supplies: RGB           | ✅                 |
| Supplies: Extra GPIO 1  | Analog/Digital     |
| Supplies: Extra GPIO 2  | Analog/Digital     |

## License

This work is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.

[^1]: Do you even really want to have RGB with a wireless build? Do you, *really*? For obvious battery-related reasons, this is not a recommended build configuration.
[^2]: Requires the `RGB_OR_WL_COL` jumper to be manually soldered appropriately.
[^3]: Requires the `split_hand_or_row` jumper to be manually soldered appropriately. This will reappropriate the dedicated handedness pin. In this case, the handedness will have to be defined in the firmware.
