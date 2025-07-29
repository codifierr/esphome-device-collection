# Relay Controller Wiring Guide

This guide describes the wiring for the relay controller implementations using the **5V ESP8266 WiFi Relay Module**:

- `single-relay-controller.yaml`
- `temperature-controlled-relay.yaml`

## Components

- 5V ESP8266 WiFi Relay Module (esp01_1m board recommended)
- Relay module (integrated with ESP8266)
- Dallas/DS18B20 temperature sensor (for temperature-controlled relay)
- Fan or other load

## Module Overview

The 5V ESP8266 WiFi Relay Module combines an ESP8266 (usually ESP-01) and a relay on a single board. It provides:

- Dedicated socket for ESP-01
- Relay control via GPIO0
- 5V input for both ESP8266 and relay
- Terminals for relay NO/COM/NC

## Wiring Diagram

### ESP8266 Pin Assignments

- **Relay Control:** GPIO0 (default for module)
- **Dallas/DS18B20 Data:** GPIO2 (for temperature-controlled relay; connect to ESP-01 header pin 2)

### 5V ESP8266 WiFi Relay Module

- **IN (Relay Control):** GPIO0 (ESP8266)
- **VCC:** 5V (module power input)
- **GND:** GND (module power input)
- **NO/COM/NC:** Connect to fan or load power circuit (as per relay specs)

### Dallas/DS18B20 Temperature Sensor (for temperature-controlled relay)

- **VCC:** 3.3V or 5V (from external supply or module, check sensor specs)
- **GND:** GND
- **DATA:** GPIO2 (ESP8266)
- **Pull-up resistor:** 4.7kΩ between DATA and VCC

### Fan or Load

- Connect the load's power line through the relay's NO/COM terminals
- Ensure proper isolation and fusing for mains-powered loads

## Power Supply

- Use a reliable 5V power supply for the relay module and ESP8266
- Ensure the relay is rated for the load's voltage/current

## Safety Tips

- Always power off before wiring
- Double-check connections and polarity
- Use waterproof enclosures for outdoor installations
- Implement proper fusing and electrical isolation
- Test with low voltage before connecting to mains

## Example Wiring Table

| Component         | ESP8266 Pin | Module Terminal | Notes                       |
|------------------|-------------|-----------------|-----------------------------|
| Relay IN         | GPIO0       | IN              | Relay control signal        |
| Relay VCC        | 5V          | VCC             | Power for module/relay      |
| Relay GND        | GND         | GND             | Ground                      |
| Dallas DATA      | GPIO2       | -               | Temperature sensor data     |
| Dallas VCC       | 3.3V/5V     | -               | Power for sensor            |
| Dallas GND       | GND         | -               | Ground                      |
| Fan/Load Power   | -           | NO/COM          | Controlled by relay         |

**Note:** For temperature-controlled relay, connect the Dallas sensor to the ESP-01 header pins (GPIO2, VCC, GND) using jumper wires. Ensure the pull-up resistor is present.

Refer to the main README for configuration and safety guidelines.
