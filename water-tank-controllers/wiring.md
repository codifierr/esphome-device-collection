# OHT Water Tank Controller Wiring Guide

This guide describes the wiring for the OHT water tank controller (`OHT-controller.yaml`).

## Components

- ESP32 (esp32dev board recommended)
- Ultrasonic sensor (HC-SR04 or compatible)
- Relay module
- Water pump

## Wiring Diagram

### ESP32 Pin Assignments

- **Ultrasonic Sensor Trigger:** GPIO26
- **Ultrasonic Sensor Echo:** GPIO25
- **Relay Control:** GPIO33

### Ultrasonic Sensor (HC-SR04)

- **VCC:** 5V (from ESP32)
- **GND:** GND (from ESP32)
- **Trig:** GPIO26 (ESP32)
- **Echo:** GPIO25 (ESP32)

### Relay Module

- **IN:** GPIO33 (ESP32)
- **VCC:** 5V (from ESP32)
- **GND:** GND (from ESP32)
- **NO/COM:** Connect to water pump power circuit (as per relay specs)

### Water Pump

- Connect the pump's power line through the relay's NO/COM terminals
- Ensure proper isolation and fusing for mains-powered pumps

## Power Supply

- Use a reliable 5V power supply for ESP32 and relay
- Ensure the relay module is rated for the pump's voltage/current

## Safety Tips

- Always power off before wiring
- Double-check connections and polarity
- Use waterproof enclosures for outdoor installations
- Implement proper fusing and electrical isolation
- Test with low voltage before connecting to mains

## Example Wiring Table

| Component         | ESP32 Pin | Notes                       |
|------------------|-----------|-----------------------------|
| Ultrasonic Trig  | GPIO26    | HC-SR04 Trigger             |
| Ultrasonic Echo  | GPIO25    | HC-SR04 Echo                |
| Relay IN         | GPIO33    | Relay control signal        |
| Relay VCC        | 5V        | Power for relay             |
| Relay GND        | GND       | Ground                      |
| Pump Power       | Relay NO/COM | Controlled by relay      |

Refer to the main README for configuration and safety guidelines.
