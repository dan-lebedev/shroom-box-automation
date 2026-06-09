# PROJECT_LOG.md

## Статус: В процессе
Последнее обновление: 2025-06-09

---

## Проект 1: Shroom Box Automation

### Статус: S3 — настройка стека (InfluxDB + Grafana)

### Что сделано
- [x] S0: GitHub зарегистрирован (dan-lebedev), Git настроен на MacBook M1
- [x] S1: Репозиторий shroom-box-automation создан, структура папок, README.md
- [x] S3 (частично): ESPHome установлен, работает, есть девайсы
- [x] S3 (частично): InfluxDB + Grafana установлены как Add-ons в HAOS

### В процессе
- [ ] InfluxDB: первичная настройка (Organization, Bucket, Token)
- [ ] Grafana: подключить к InfluxDB
- [ ] HA Integration: настроить отправку данных в InfluxDB

### Hardware Decisions
- Sensor: SHT41 (выбран вместо SHT31/DHT22)
- Placement: защита от конденсата обязательна (shielding + правильное расположение)

---

## Проект 2: Grow Tent Automation

### Статус: Не начат (ждёт завершения Shroom Box)

---

## Железо (общее)
- MacBook M1 — рабочая машина
- Lenovo ThinkPad T460 (8GB/250GB) — HAOS, все сервисы
- ESP32, D1 Mini, Arduino
- SHT45, MLX90614, NDIR CO2
- TRIAC модуль (AC димминг)
- Zigbee координатор + розетки в HA
- 2x LED 120W с физическими диммерами
- Grow tent 60x40x140 см
