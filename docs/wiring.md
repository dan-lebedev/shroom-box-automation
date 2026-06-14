# Shroom Box Automation — Wiring

## ESP32 Pinout Plan

| Device | ESP32 Pin | Signal |
|---|---:|---|
| SHT41 Probe | 3V3 | VCC |
| SHT41 Probe | GND | GND |
| SHT41 Probe | GPIO21 | SDA |
| SHT41 Probe | GPIO22 | SCL |
| BH1750 / GY-302 | 3V3 | VCC |
| BH1750 / GY-302 | GND | GND |
| BH1750 / GY-302 | GPIO25 | SDA |
| BH1750 / GY-302 | GPIO26 | SCL |

## Wiring Diagram

```mermaid
flowchart TB
    ESP["ESP32 Dev Board"]

    subgraph SHT["SHT41 T/RH Probe"]
        SHTV["VCC"]
        SHTG["GND"]
        SHTSDA["SDA"]
        SHTSCL["SCL"]
    end

    subgraph BH["BH1750 / GY-302 Light Sensor"]
        BHV["VCC"]
        BHG["GND"]
        BHSDA["SDA"]
        BHSCL["SCL"]
    end

    ESP3V3A["ESP32 3V3"] --> SHTV
    ESPGNDA["ESP32 GND"] --> SHTG
    ESP21["ESP32 GPIO21"] --> SHTSDA
    ESP22["ESP32 GPIO22"] --> SHTSCL

    ESP3V3B["ESP32 3V3"] --> BHV
    ESPGNDB["ESP32 GND"] --> BHG
    ESP25["ESP32 GPIO25"] --> BHSDA
    ESP26["ESP32 GPIO26"] --> BHSCL
```

## I2C Bus Layout

```mermaid
flowchart LR
    ESP["ESP32"]

    subgraph BUS1["I2C Bus: SHT41"]
        SDA1["SDA GPIO21"]
        SCL1["SCL GPIO22"]
        SHT41["SHT41 Probe<br/>Address 0x44"]
    end

    subgraph BUS2["I2C Bus: BH1750"]
        SDA2["SDA GPIO25"]
        SCL2["SCL GPIO26"]
        BH1750["BH1750 / GY-302<br/>Address 0x23"]
    end

    ESP --> SDA1
    ESP --> SCL1
    SDA1 --> SHT41
    SCL1 --> SHT41

    ESP --> SDA2
    ESP --> SCL2
    SDA2 --> BH1750
    SCL2 --> BH1750
```

## Physical Notes

- Both sensors should be powered from 3.3V.
- Avoid placing the SHT41 probe directly in the humidifier mist stream.
- Place the SHT41 probe in the air volume, shielded from direct droplets.
- Place the BH1750 so it sees the box light, but is protected from condensation.
- Use short Dupont wires where possible.
- If readings become unstable, reduce I2C frequency or improve wiring.
