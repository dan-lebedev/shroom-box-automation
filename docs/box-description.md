# Shroom Box — Physical Description

## Purpose
Controlled environment chamber for oyster mushroom (Pleurotus ostreatus) cultivation.
Maintains high humidity, fresh air exchange, and stable temperature during colonization and fruiting.

## Dimensions
Plastic container, 150 L.

## Components (already built)
- **Container:** 150 L plastic box
- **Ventilation:** 12V DC 120×120 mm fan (3.6W), PWM-dimmable
- **Humidification:** ultrasonic reptile humidifier with hose, external, controlled via Zigbee smart plug
- **Passive humidity buffer:** mesh mat + water layer at bottom
- **Cable gland:** PG9 for sensor cable pass-through

## Environment Targets
| Parameter | Colonization | Fruiting |
|---|---|---|
| Temperature | 20–24 °C | 18–22 °C |
| Humidity | 85–95 % RH | 85–95 % RH |
| CO₂ | tolerated high | < 800 ppm |
| Fresh air exchange | minimal | frequent |

## Sensors
- **T/RH:** industrial probe (SHT3x/SHT4x, I²C) inside the box, on cable
- **CO₂:** NDIR Zigbee sensor inside the box

## Actuators (controlled via Home Assistant)
- Fan (Zigbee plug + PWM dimmer): triggered by CO₂ threshold
- Humidifier (Zigbee plug): triggered by RH threshold

## Notes
- Industrial T/RH probe has built-in filter cap → no extra condensate protection needed
- Humidifier auto-resumes after power cycle → safe to control via smart plug
