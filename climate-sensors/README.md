# Climate Sensors

This directory contains ESPHome configurations for climate monitoring devices.

## Available Configurations

### DHT Climate Sensor (`dht-climate-sensor.yaml`)

- Temperature and humidity monitoring using DHT sensor (DHT11/DHT22)
- ESP8266 (NodeMCU v2) based implementation
- Home Assistant and MQTT integration
- Secure OTA and API access
- WiFi signal monitoring
- Human-readable uptime reporting
- Real-time temperature and humidity sensors
- Status and version sensors for diagnostics

**Hardware Required:**

- ESP8266 (NodeMCU v2 board recommended)
- DHT11 or DHT22 sensor
- Pull-up resistor (4.7kΩ)

**Key Features:**

- Temperature and humidity readings via DHT sensor
- MQTT birth/will messages for device status
- Home Assistant API with encryption
- Human-readable uptime sensor
- WiFi and device info sensors

**How to Use:**

1. Copy `dht-climate-sensor.yaml` to your ESPHome config directory
2. Update `secrets.yaml` with your WiFi, MQTT, and API credentials
3. Set the correct GPIO pin for your DHT sensor (default: GPIO14)
4. Wire the sensor and pull-up resistor as per the pin assignments
5. Compile and upload to your ESP8266 device
6. Integrate with Home Assistant or MQTT as needed

**Customization:**

- Change sensor pin and type in the YAML
- Adjust update intervals and accuracy as needed
- Use Home Assistant or MQTT to monitor status and sensor data

## Features

- Real-time monitoring
- Calibration support
- Alerting capabilities
- Energy efficient operation
- Wireless connectivity

## Installation

1. Choose your configuration file
2. Update hardware pins in the YAML file
3. Modify sensor calibration values if needed
4. Upload to your ESP device

## Wiring

### DHT22 Sensor

- VCC → 3.3V
- GND → GND
- DATA → GPIO pin (configurable)
- Pull-up resistor between VCC and DATA

### BME280 Sensor (I2C)

- VCC → 3.3V
- GND → GND
- SDA → GPIO21 (ESP32) / GPIO4 (ESP8266)
- SCL → GPIO22 (ESP32) / GPIO5 (ESP8266)
