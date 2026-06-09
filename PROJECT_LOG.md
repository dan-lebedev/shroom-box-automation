# PROJECT_LOG.md

## Статус: В процессе
Последнее обновление: 2025-06-09

---

## Проект 1: Shroom Box Automation

### Статус: S3 завершён — стек работает на тестовом датчике. Следующий шаг: S2 (закупка SHT41).

### Что сделано
- [x] S0: GitHub зарегистрирован (dan-lebedev), Git настроен на MacBook M1
- [x] S1: Репозиторий shroom-box-automation создан, структура папок, README.md
- [x] S3: ESPHome + InfluxDB + Grafana установлены и связаны. Цепочка ESPHome → HA → InfluxDB → Grafana работает на тестовом датчике (temp_jar_3_temperature).

### В процессе
- [ ] S2: Закупить SHT41 на Али + корпус/защита от конденсата
- [ ] S4: ESPHome конфиг для боевого сенсора в шрумбоксе
- [ ] S5: HA automations (вентиляция по CO2, увлажнение)
- [ ] S6: Grafana dashboard (полный, не одна панель)

### Известные риски
- Add-on InfluxDB2 от Dattel — community, малая база пользователей
- Fallback если не заработает: официальный InfluxDB 1.x add-on


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
