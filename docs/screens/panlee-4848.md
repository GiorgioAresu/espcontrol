---
title: "Panlee 4848 GC9503V Home Assistant Setup"
description:
  EspControl on the Panlee 480 × 480 square touchscreen with ESP32-S3, GC9503V display controller, and FT63x6 touch.
---

# 4-inch Panlee 4848 (GC9503V)

The Panlee 4848 profile targets a **480 × 480 square touchscreen** built around an **ESP32-S3**, the **GC9503V** MIPI RGB display controller and an **FT63x6** capacitive touchscreen. It provides a 3 × 3 home grid with **9 card slots** and supports **2 shared image cards** across the home page and subpages.

This profile uses the GC9503V-enabled `mipi_rgb` component from the [`GiorgioAresu/esphome` `gc9503v` branch](https://github.com/GiorgioAresu/esphome/tree/gc9503v). That external component is declared by the firmware configuration.

## Card Grid

<!--@include: ../generated/screens/panlee-4848-grid.md-->

Camera and Media Cover Art cards share the two image slots across all pages. Camera cards display still snapshots, not live video.

## Install

Use a USB data cable to connect the panel, then install the firmware using the device profile below.

<!--@include: ../generated/screens/panlee-4848-install.md-->

For a full walkthrough including WiFi setup and Home Assistant pairing, see the [Install guide](/getting-started/install).

## ESPHome Manual Setup

```yaml
substitutions:
  name: "panlee-panel"
  friendly_name: "Panlee Panel"

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

packages:
  setup:
    url: https://github.com/jtenniswood/espcontrol/
    file: devices/panlee-esp32-s3-4848/packages.yaml
    refresh: 1s
```

## Hardware Pinout

| Function | GPIO |
|---|---:|
| Display SPI clock | 45 |
| Display SPI MOSI | 48 |
| Backlight PWM | 5 |
| I²C SDA | 15 |
| I²C SCL | 6 |
| Touch interrupt | 4 |
