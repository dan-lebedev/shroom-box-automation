# Shroom Box Automation System Specification

## 1. Purpose

This document defines the engineering requirements for the Shroom Box Automation system.

It serves as the authoritative specification describing the required behavior, operational objectives, and validation criteria of the system.

Implementation details are intentionally excluded. The specification defines what the system shall achieve rather than how it is implemented.

---

## 2. Scope

The system shall monitor and maintain environmental conditions required for oyster mushroom fruiting while continuously recording operational data for engineering analysis and compliance reporting.

The specification covers environmental monitoring, automated control, operational reliability, and historical data collection.

Cultivation procedures and hardware implementation details are outside the scope of this document.

---

## 3. System Objectives

The system shall satisfy the following primary objectives:

1. Maintain stable environmental conditions suitable for oyster mushroom fruiting.

2. Collect sufficient environmental and operational data to demonstrate that configured environmental targets were maintained.

3. Continue operating safely and predictably under expected failure conditions.

4. Produce engineering-quality historical data suitable for validation, troubleshooting, and future system improvements.

---

## 4. Environmental Parameters

The system shall monitor the following environmental parameters throughout the cultivation cycle:

- Air temperature
- Relative humidity
- Carbon dioxide (CO₂) concentration
- Light intensity
- Substrate temperature

The system shall actively control:

- Humidification
- Fresh air exchange
- Lighting

The system shall support different environmental operating profiles for each cultivation stage, including substrate colonization, primordia initiation, and fruiting.

Target values, acceptable tolerances, and operating schedules shall be configurable without changing the system design.

---

## 5. Functional Requirements

The system shall:

- Continuously monitor all defined environmental parameters.
- Record historical measurements for every monitored parameter.
- Automatically regulate environmental conditions using the available control equipment.
- Support stage-specific environmental operating profiles.
- Generate alarms when environmental conditions exceed configured limits or when system components become unavailable.
- Record the operational state of all environmental control equipment.
- Continue collecting environmental data whenever partial system failures occur.
- Preserve historical records suitable for operational analysis, troubleshooting, and performance evaluation.

---

## 6. Reliability Requirements

The system shall be designed to continue operating during non-critical component failures.

The system shall:

- Continue environmental monitoring even if one or more actuators become unavailable.
- Detect sensor communication failures.
- Detect unavailable environmental control devices.
- Generate alarms for detected failures.
- Resume normal operation automatically after failed components recover.
- Prevent uncontrolled operation caused by sensor communication loss.

The failure of a single sensor shall not prevent collection of measurements from remaining sensors.

---

## 7. Safety Requirements

The system shall prevent operating conditions that may damage equipment or cultivation materials.

The system shall:

- Detect environmental values outside the supported measurement range.
- Detect invalid sensor readings.
- Prevent conflicting actuator states where applicable.
- Preserve manual control capability during automatic system failures.
- Require explicit confirmation before destructive maintenance operations.

---

## 8. Maintainability Requirements

The system shall be maintainable without requiring software redesign.

The system shall:

- Allow replacement of sensors without affecting unrelated system components.
- Allow addition of new environmental sensors.
- Allow addition of new environmental control devices.
- Support configuration changes without modifying application logic.
- Keep configuration separate from implementation.

---

## 9. Monitoring and Observability Requirements

The system shall provide sufficient operational visibility for troubleshooting and performance analysis.

The system shall:

- Record environmental measurements.
- Record actuator state changes.
- Record alarms and warnings.
- Record system availability events.
- Record configuration changes.
- Support long-term historical analysis of cultivation cycles.

---

## 10. Data Management Requirements

The system shall preserve operational data required for analysis of cultivation performance.

Historical records shall include:

- Environmental measurements.
- Actuator states.
- Alarm events.
- System status events.

Recorded data shall support comparison of multiple cultivation cycles.

---
## 11. Constraints

The implementation shall be based on the following technologies:

- Home Assistant OS
- ESPHome
- InfluxDB
- Grafana

The system shall target small-scale controlled environment agriculture using commodity hardware whenever practical.

---

## 12. Acceptance Criteria

The implementation shall be considered complete when it demonstrates the ability to:

- Monitor all required environmental parameters.
- Automatically maintain configured environmental conditions.
- Record operational history.
- Generate alarms for abnormal conditions.
- Support multiple cultivation stages.
- Recover automatically from recoverable failures.