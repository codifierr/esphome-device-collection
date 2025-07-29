# Wiring Diagrams

This directory contains wiring diagrams and connection guides for all device configurations.

## Available Diagrams

### Water Tank Controllers

- `../water-tank-controllers/wiring.md` - Water tank controller wiring details

### Climate Sensors

- `../climate-sensors/wiring.md` - DHT climate sensor wiring details

### Relay Controllers

- `../relay-controllers/wiring.md` - Relay controller wiring details

## Safety Guidelines

⚠️ **Always follow these safety rules:**

1. **Power off** all devices before making connections
2. **Double-check** polarity for power connections
3. **Use appropriate wire gauges** for current requirements
4. **Implement proper fusing** and protection
5. **Follow local electrical codes**
6. **Test with low voltage** before connecting to mains

## General Guidelines

### Power Supply

- ESP32: 3.3V logic, can accept 5V on VIN
- ESP8266: 3.3V logic, can accept 5V on VIN
- Sensors: Check individual requirements (3.3V or 5V)

### GPIO Considerations

- Input pins: Use pull-up/pull-down resistors as needed
- Output pins: Consider current limitations
- I2C: Use pull-up resistors (4.7kΩ typical) if used
- Interrupt pins: Choose carefully for best performance

### Common Components

#### Pull-up Resistors

- Value: 4.7kΩ to 10kΩ
- Use for: DHT sensors, button inputs, some sensors

#### Bypass Capacitors

- Value: 100nF ceramic + 10µF electrolytic
- Place close to IC power pins

#### Protection

- Fuses for power circuits
- Diodes for relay coil protection
- Optoisolators for high voltage switching
