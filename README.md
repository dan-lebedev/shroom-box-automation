# Shroom Box Automation

Automated environment control for oyster mushroom cultivation.
Engineering portfolio project — focus on sensors, data pipeline, and automation.

## Stack
- **Hardware:** ESP32, industrial T/RH probe (SHT3x/SHT4x I²C), NDIR CO₂ Zigbee sensor, ultrasonic humidifier, 12V PWM fan
- **Firmware:** ESPHome
- **Control:** Home Assistant (HAOS) + Zigbee2MQTT
- **Data:** InfluxDB + Grafana

## Goals
- Stable VPD / humidity / CO₂ control during fruiting cycle
- Full data pipeline: sensor → ESPHome → HA → InfluxDB → Grafana
- Documented hardware, wiring, and automations
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
