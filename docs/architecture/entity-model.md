# Entity Model

## Purpose

This document defines the Home Assistant entities exposed by the automation system.

The entity model acts as the stable interface between:

- ESPHome firmware
- Home Assistant
- Grafana dashboards
- Automation logic

Hardware implementations may change over time without affecting entity names or semantics.

---

# Environmental Sensors

## Air Temperature

| Property | Value |
|----------|-------|
| Entity | `sensor.air_temperature` |
| Source | SHT41 |
| Unit | °C |
| Device Class | `temperature` |
| State Class | `measurement` |
| Read Only | Yes |

### Description

Ambient air temperature inside the grow chamber.

---

## Relative Humidity

| Property | Value |
|----------|-------|
| Entity | `sensor.air_humidity` |
| Source | SHT41 |
| Unit | % |
| Device Class | `humidity` |
| State Class | `measurement` |
| Read Only | Yes |

### Description

Ambient relative humidity inside the grow chamber.

---

## Carbon Dioxide

| Property | Value |
|----------|-------|
| Entity | `sensor.air_co2` |
| Source | SCD41 |
| Unit | ppm |
| Device Class | `carbon_dioxide` |
| State Class | `measurement` |
| Read Only | Yes |

### Description

Carbon dioxide concentration measured in the grow chamber.

---

## Light Level

| Property | Value |
|----------|-------|
| Entity | `sensor.light_level` |
| Source | BH1750 |
| Unit | lx |
| Device Class | `illuminance` |
| State Class | `measurement` |
| Read Only | Yes |

### Description

Ambient illuminance measured at canopy level.

---

## Substrate Temperature

| Property | Value |
|----------|-------|
| Entity | `sensor.water_temperature` |
| Source | DS18B20 |
| Unit | °C |
| Device Class | `temperature` |
| State Class | `measurement` |
| Read Only | Yes |

### Description

Temperature inside the mushroom substrate.

---


# Diagnostic Sensors

## Wi-Fi Signal

```
sensor.wifi_signal
```

## ESP Uptime

```
sensor.uptime
```

## Restart Count

```
sensor.restart_count
```

## Firmware Version

```
sensor.firmware_version
```