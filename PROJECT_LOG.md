# PROJECT_LOG.md

**Status:** In progress
**Last updated:** 2025-06-14

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
- [x] Security: secrets.yaml setup, .gitignore configured
- [x] Order T/RH probe + GY-302  from AliExpress
- [x] S4 (partial): ESPHome config drafted — shroom-box-esp32.yaml (SHT41 + BH1750), pending hardware arrival
- [x] Architecture diagram added: `docs/architecture.md`
- [x] Wiring diagram draft added: `docs/wiring.md`
- [x] ESP32 wiring plan updated: separate I²C buses for SHT41 and BH1750
- [x] S5: HA automation drafts complete — shroom_fan.yaml + shroom_humidifier.yaml
  - Fan control: CO2 thresholds 900/1200 ppm with hysteresis
  - Humidifier control: RH thresholds 85/93% with hysteresis
  - Failsafe logic for both sensors (unavailable → safe state + notification)
  - TODO: replace PLACEHOLDER entity_ids when Zigbee plugs connected
  - TODO: verify sensor.shroom_box_esp32_humidity after ESP32 hardware arrives
- [x] S6: Grafana dashboard draft complete — temp/humidity/CO2/light/dew point/absolute humidity/substrate temp panels. DS18B20 panels present as placeholders. All sensors entities present as placeholders.



### S4 progress (firmware draft ready, hardware pending)
- ESPHome config drafted and reviewed: shroom-box-esp32.yaml
- Sensors: SHT41 (I2C bus_sht GPIO21/22), BH1750 (I2C bus_light GPIO25/26),
  DS18B20 substrate (1-Wire GPIO4, needs 4.7kΩ pull-up), NDIR CO2
- Derived: dew point + absolute humidity (Alduchov-Eskridge Magnus)
- Production features: safe mode, NaN watchdog (3-strike reboot),
  runtime humidity thresholds, diagnostics
- TODO on first flash: capture DS18B20 address from logs, fill into config
- TODO: verify GPIO25/26 free on actual board
- Required secrets: shroom_esp32_api_key, shroom_esp32_ota_password,
  wifi_ssid, wifi_password, shroom_esp32_ap_password


### Next Steps
- [ ] S4: ESPHome config for ESP32 + sensors in shroom box 
- [ ] S5: HA automations (fan by CO₂, humidifier by RH)
- [ ] S6: Grafana dashboard
- [ ] S7: Growing cycle, data collection
- [ ] S8: Final report in README — photos, graphs, harvest results

### Hardware Decisions
- **T/RH sensor:** industrial probe in metal housing with filter cap (SHT41, I²C). Built-in condensate protection. Proven working with ESPHome SHT library.
- **T soil sensor:** DS18B20 (1-Wire)
- **CO₂ sensor:** SCD41 (I2C)
- **Humidification:** active — mechanically controlled ultrasonic reptile humidifier with hose. Controlled via SSR-25 DA.
- **Fan:** existing 12V + IRF520 MOSFET
- **Light sensor:** BH1750 (GY-302 module, I²C on dedicated bus GPIO25/GPIO26) — photoperiod compliance logging
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
