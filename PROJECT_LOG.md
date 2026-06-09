# PROJECT_LOG.md

**Status:** In progress
**Last updated:** 2025-06-09

---

## Project: Shroom Box Automation

### Current Stage
S3 — Stack setup (InfluxDB + Grafana + ESPHome). Pipeline verified on test sensor.

### Done
- [x] S0: GitHub registered (dan-lebedev), Git configured on MacBook M1
- [x] S1: Repo `shroom-box-automation` created, folder structure, README.md
- [x] S2: BOM documented, T/RH probe identified (same model previously used, SHT3x/SHT4x I²C, works with ESPHome SHT library)
- [x] S3 (partial): ESPHome installed, working, test devices added
- [x] S3 (partial): InfluxDB + Grafana installed as HAOS Add-ons
- [x] S3 (partial): Full pipeline verified — ESPHome → HA → InfluxDB → Grafana (test sensor)
- [x] Humidifier auto-resume after power cycle confirmed
- [x] GitHub Issue created: "Add wiring diagram after sensors arrive"

### Next Steps
- [ ] Order T/RH probe from AliExpress
- [ ] S4: ESPHome config for ESP32 + sensors in shroom box (can start YAML draft before hardware arrives)
- [ ] S5: HA automations (fan by CO₂, humidifier by RH)
- [ ] S6: Grafana dashboard
- [ ] S7: Growing cycle, data collection
- [ ] S8: Final report in README — photos, graphs, harvest results

### Hardware Decisions
- **T/RH sensor:** industrial probe in metal housing with filter cap (SHT3x/SHT4x, I²C). Built-in condensate protection. Proven working with ESPHome SHT library.
- **CO₂ sensor:** NDIR Zigbee — integrated via Zigbee2MQTT, bypasses ESP32.
- **Humidification:** active — ultrasonic reptile humidifier with hose. Controlled via Zigbee smart plug. Auto-resume confirmed.
- **Fan:** existing 12V + PWM dimmer + Zigbee plug for AC power.
- **Light sensor (BH1750):** skipped, not critical for oyster mushrooms.
- **BOM:** `hardware/BOM.md`
- **Physical box description:** `docs/box-description.md`
- **Wiring diagram:** to be created after sensors arrive (GitHub Issue open).

---

## Hardware Inventory (general)
- MacBook M1 — workstation
- Lenovo ThinkPad T460 (8GB / 250GB SSD) — HAOS host, all services
- ESP32, D1 Mini, several Arduinos
- SHT45, MLX90614 (reserved for future projects)
- TRIAC module (reserved for future projects)
- Zigbee coordinator + smart plugs in HA
- Ultrasonic reptile humidifiers
