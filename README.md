# Shroom Box Automation 🍄

Automation system for oyster mushroom (*Pleurotus ostreatus*) cultivation in a controlled environment box.

**Status:** 🟡 In development

## Goal

Build an engineering showcase of a small-scale controlled environment agriculture (CEA) system: sensors → data pipeline → automation → dashboards.

This is a portfolio project demonstrating automation engineering for agritech, not a growing tutorial.

## Architecture

​```mermaid
graph TD
    A[ESP32 + SHT31 + NDIR CO2] -->|ESPHome / WiFi| B[Home Assistant OS]
    B --> C[Zigbee smart plugs: humidifier, fan]
    B --> D[(InfluxDB)]
    D --> E[Grafana dashboards]
​```

## Hardware

Main components:

- ESP32 dev board
- SHT31 — temperature & humidity sensor (I2C)
- NDIR CO2 sensor
- Zigbee smart plugs for humidifier and exhaust fan
- Home Assistant OS on ThinkPad T460

See [hardware/BOM.md](hardware/BOM.md) for the full bill of materials.

## Repository structure

- `docs/` — architecture notes, photos, growing log
- `hardware/` — BOM, wiring diagrams
- `esphome/` — ESP32 firmware configs
- `homeassistant/` — automations and integrations
- `grafana/` — dashboard JSON exports
- `scripts/` — helper scripts

## Roadmap

- [x] S0: Tooling setup
- [x] S1: Repository structure
- [ ] S2: Hardware BOM finalized
- [ ] S3: InfluxDB + Grafana + ESPHome add-ons in HAOS
- [ ] S4: ESP32 firmware with sensors
- [ ] S5: HA automations (CO2 ventilation, humidity control)
- [ ] S6: Grafana dashboard
- [ ] S7: Growing cycle + data collection
- [ ] S8: Final report

## License

MIT
