# Shroom Box Automation

Automated environment control for oyster mushroom cultivation.
Engineering portfolio project — focus on sensors, data pipeline, and automation.

## Stack
- **Hardware:** ESP32, SHT41, SCD41, BH1750, DS18B20, relay modules, ultrasonic humidifier, exhaust fan
- **Firmware:** ESPHome
- **Control:** Home Assistant (HAOS)
- **Data:** InfluxDB + Grafana

## Goals
- Stable humidity and CO₂ control during the fruiting cycle
- Full data pipeline: sensors → ESPHome → Home Assistant → InfluxDB → Grafana
- Documented hardware, wiring, firmware, and automations
- Reproducible setup

## Repo Structure

shroom-box-automation/
├── README.md
├── PROJECT_LOG.md
├── docs/
│   └── box-description.md
├── esphome/
├── grafana/
├── hardware/
│   ├── BOM.md
│   └── wiring.md (TBD)
└── homeassistant/


## Status
See [PROJECT_LOG.md](./PROJECT_LOG.md) for current stage and progress.

## Author
Dan Lebedev — BA/PM/automation engineer, building toward agritech / controlled environment agriculture roles.
