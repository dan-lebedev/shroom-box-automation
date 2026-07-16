# Sensors

## Purpose

This document describes the hardware sensors used by the project.

Specifications are taken from the official manufacturer datasheets.

---

# SHT41

Manufacturer: Sensirion

## Function

Digital temperature and relative humidity sensor.

| Parameter | Value |
|-----------|-------|
| Interface | I²C |
| I²C Address | 0x44 |
| Supply Voltage | 1.08–3.6 V |
| Temperature Range | −40…125 °C |
| Temperature Accuracy | ±0.2 °C (typ.) |
| Humidity Range | 0–100 %RH |
| Humidity Accuracy | ±1.8 %RH (25–75 %RH), ±2 %RH typical over full range |
| Resolution | 16-bit internal |
| Typical Measurement Time | ≈8 ms (high precision) |

### Usage

Measures ambient temperature and relative humidity inside the grow chamber.

---

# SCD41

Manufacturer: Sensirion

## Function

Photoacoustic CO₂ sensor with integrated temperature and humidity measurement.

| Parameter | Value |
|-----------|-------|
| Interface | I²C |
| Default Address | 0x62 |
| Supply Voltage | 2.4–5.5 V |
| CO₂ Range | 400–5000 ppm |
| CO₂ Accuracy | ±(40 ppm + 5% of reading) |
| Temperature Accuracy | ±0.8 °C |
| Humidity Accuracy | ±6 %RH |
| Measurement Interval | 5 s (periodic mode) |

### Usage

Measures carbon dioxide concentration for ventilation control.

Temperature and humidity values are available but are not used as the primary environmental measurements because the dedicated SHT41 provides higher accuracy.

---

# BH1750

Manufacturer: ROHM Semiconductor

## Function

Digital ambient light sensor.

| Parameter | Value |
|-----------|-------|
| Interface | I²C |
| Default Address | 0x23 |
| Alternate Address | 0x5C |
| Supply Voltage | 2.4–3.6 V (sensor IC) |
| Measurement Range | 1–65535 lx |
| Resolution | 1 lx (High Resolution Mode) |
| Typical Measurement Time | 120 ms |

### Usage

Measures ambient illuminance inside the grow chamber.

---

# DS18B20

Manufacturer: Analog Devices (formerly Maxim Integrated)

## Function

Digital waterproof temperature sensor.

| Parameter | Value |
|-----------|-------|
| Interface | 1-Wire |
| Supply Voltage | 3.0–5.5 V |
| Temperature Range | −55…125 °C |
| Accuracy | ±0.5 °C (−10…85 °C) |
| Resolution | 9–12 bit (configurable) |
| Conversion Time | Up to 750 ms (12-bit) |

### Usage

Measures temperature inside the mushroom substrate..

---

# Design Notes

- SHT41 is the primary source for air temperature and humidity.
- SCD41 is used exclusively for CO₂ measurement.
- BH1750 measures illuminance for lighting monitoring.
- DS18B20 measures nutrient solution temperature.
- Each sensor is exposed as a dedicated Home Assistant entity.