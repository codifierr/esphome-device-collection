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
   mqtt_broker: "192.168.1.100"
   # ... etc
   ```

## 📂 Device Categories

### 💧 [Water Tank Controllers](./water-tank-controllers/)
- **Basic Tank Controller** - Simple water level monitoring
- **Advanced with Scheduling** - Automated pump control with dry-run protection
- **Multi-Tank Setup** - Monitor multiple tanks

### 🌡️ [Climate Sensors](./climate-sensors/)
- **DHT11/DHT22** - Temperature and humidity monitoring
- **Advanced Climate Station** - Multiple sensors with data logging

### 🔌 [Relay Controllers](./relay-controllers/)
- **Single Relay** - Basic on/off control
- **Smart Switch** - Advanced switching with scheduling

## 🔧 Hardware Requirements

| Device Type | MCU | Sensors | Additional |
|-------------|-----|---------|------------|
| Tank Controller | ESP32 | HC-SR04 | Relay Module |
| Climate Sensor | ESP8266/ESP32 | DHT11/DHT22 | - |
| Relay Controller | ESP8266/ESP32 | - | Relay Board |

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
1. Choose your device configuration
2. Copy the YAML file to your ESPHome directory
3. Update the `secrets.yaml` file
4. Modify device-specific parameters
5. Compile and upload

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
