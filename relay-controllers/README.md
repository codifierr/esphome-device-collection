# Relay Controllers

This directory contains ESPHome configurations for relay-based switching and control systems.

## Available Configurations

### 1. Single Relay Controller (`single-relay-controller.yaml`)

- Basic on/off control for single relay
- Manual and automated switching
- Home Assistant integration
- Web interface control

**Hardware Required:**

- ESP32 or ESP8266
- Single relay module
- Load to control (lights, fans, etc.)

### 2. Temperature Controlled Relay (`temperature-controlled-relay.yaml`)

- Automatic relay control based on temperature sensor (Dallas/DS18B20)
- Fan or load switches ON above 44°C, OFF below 41.5°C (customizable)
- Home Assistant and MQTT integration
- Uptime reporting in human-readable format
- WiFi signal monitoring
- Secure OTA and API access
- Status and version sensors for diagnostics

**Hardware Required:**

- ESP8266 (esp01_1m board recommended)
- Dallas/DS18B20 temperature sensor (with correct address)
- Relay module (for fan or load control)
- Fan or other load

**Key Features:**

- Temperature-based relay automation (thresholds adjustable in YAML)
- MQTT birth/will messages for device status
- Home Assistant API with encryption
- Human-readable uptime sensor
- WiFi and device info sensors

**How to Use:**

1. Copy `temperature-controlled-relay.yaml` to your ESPHome config directory
2. Update `secrets.yaml` with your WiFi, MQTT, and API credentials
3. Set the correct Dallas sensor address in the YAML
4. Wire the relay and sensor as per the pin assignments
5. Compile and upload to your ESP8266 device
6. Integrate with Home Assistant or MQTT as needed

**Customization:**

- Change temperature thresholds in the `on_value_range` section
- Adjust pin assignments for your hardware
- Use Home Assistant or MQTT to monitor status and control

## Safety Guidelines

⚠️ **Important Safety Notes:**

- Always follow local electrical codes
- Use appropriate relay ratings for your load
- Implement proper electrical isolation
- Test all safety features before deployment
- Use qualified electricians for mains voltage work

## Installation

1. Select the appropriate configuration
2. Verify relay module compatibility
3. Update GPIO pin assignments
4. Configure load-specific parameters
5. Test with low voltage loads first

## Wiring

### Basic Relay Module

- VCC → 3.3V or 5V (check relay requirements)
- GND → GND
- IN → GPIO pin (configurable)
- COM, NO, NC → Load connections

### Safety Considerations

- Use optoisolated relay modules
- Implement proper fusing
- Consider using contactors for high current loads
