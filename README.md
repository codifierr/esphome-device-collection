# ESPHome Device Collection 🏠

A comprehensive collection of ESPHome configurations for various IoT devices and home automation projects.

## 🚀 Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/codifierr/esphome-device-collection.git
   cd esphome-device-collection
   ```

2. **Copy secrets template**
   ```bash
   cp secrets-template.yaml secrets.yaml
   ```

3. **Edit your secrets**
   ```yaml
   wifi_ssid: "Your WiFi"
   wifi_password: "password"
   mqtt_broker: "mqttbroker.local"
   # ... etc
   ```

## 📂 Device Categories

### 💧 [Water Tank Controllers](./water-tank-controllers/)
- **OHT Controller** - Ultrasonic water level monitoring and pump control

### 🌡️ [Climate Sensors](./climate-sensors/)
- **DHT11/DHT22 Climate Sensor** - Temperature and humidity monitoring

### 🔌 [Relay Controllers](./relay-controllers/)
- **Single Relay Controller** - Basic on/off control
- **Temperature Controlled Relay** - Relay control based on temperature sensor

## 🔧 Hardware Requirements

| Device Type           | MCU              | Sensors         | Additional         |
|----------------------|------------------|----------------|--------------------|
| OHT Controller       | ESP32            | HC-SR04        | Relay Module, Pump |
| DHT Climate Sensor   | ESP8266 (NodeMCU)| DHT11/DHT22    | 4.7kΩ Resistor     |
| Relay Controller     | ESP8266 (5V WiFi Relay Module) | Dallas/DS18B20 (optional) | Relay Board, Fan/Load |

## 📋 Features

- ✅ **Plug & Play** - Ready-to-use configurations
- ✅ **Well Documented** - Detailed setup instructions
- ✅ **Safety First** - Built-in protection mechanisms
- ✅ **Home Assistant** - Full integration support
- ✅ **MQTT Support** - Standalone operation capability
- ✅ **OTA Updates** - Remote firmware updates

## 🏗️ Installation

### Prerequisites
- [ESPHome](https://esphome.io/guides/installing_esphome.html) installed
- Home Assistant (optional)
- MQTT Broker (optional)

### Steps
1. Choose your device configuration from the relevant category
2. Copy the YAML file to your ESPHome directory
3. Update the `secrets.yaml` file
4. Modify device-specific parameters (pins, sensor types, etc.)
5. Compile and upload to your ESP device

## 📑 Wiring Guides

- See [wiring/README.md](./wiring/README.md) for wiring diagrams and connection details for each device
- Device-specific wiring guides are available in each category's `wiring.md` file

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](./docs/contributing.md) for guidelines.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⭐ Star History

If you find this helpful, please consider giving it a star!

## 📞 Support

- 🐛 [Issues](https://github.com/codifierr/esphome-device-collection/issues)
- 💬 [Discussions](https://github.com/codifierr/esphome-device-collection/discussions)
- 📖 [Documentation](./docs/)
