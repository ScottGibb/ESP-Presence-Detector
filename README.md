# ESP Presence Detector

A USB-powered presence detector running ESPHome for use with Home Assistant.
It combines an AM312 PIR sensor and a NORPS-12 light sensor to report motion
and ambient light levels for automations such as lighting control.

The hardware uses a Wemos NodeMCU ESP8266. This repository contains the
[KiCad 10 schematic project](esp-presence-detector.kicad_pro).

| Connection                 | Wiring                                |
| -------------------------- | ------------------------------------- |
| J1: AM312 female header    | 1: 3.3 V, 2: OUT → D5/GPIO14, 3: GND  |
| J2: NORPS-12 female header | 1: 3.3 V, 2: A0; 10 kΩ from A0 to GND |

Use the module's scaled **A0**, not its raw ADC pin. Check AM312 orientation
before insertion. Both sensors use 3.3 V; power the controller through USB.

Firmware lives in [Home-Lab-Containers](https://github.com/ScottGibb/Home-Lab-Containers):
[shared detector](https://github.com/ScottGibb/Home-Lab-Containers/blob/main/PiHome/IOT/ESPHome/detector.yaml),
[hallway](https://github.com/ScottGibb/Home-Lab-Containers/blob/main/PiHome/IOT/ESPHome/hallway.yaml),
and [bedroom](https://github.com/ScottGibb/Home-Lab-Containers/blob/main/PiHome/IOT/ESPHome/bedroom.yaml).

The schematic is tested in CI and released using Release Please.

## Useful links

- [NORPS-12 LDR — Farnell UK](https://uk.farnell.com/advanced-photonix/norps-12/light-dependent-resistor-1mohm/dp/327700)
- [AM312 PIR sensor — Kunkune UK](https://kunkune.co.uk/shop/arduino-sensors/am312-mini-ir-infrared-pir-body-motion-human-sensor/)
