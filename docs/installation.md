# Installation Guide

This guide will walk you through setting up and using the ESPHome Device Collection.

## Prerequisites

### Software Requirements

- **ESPHome**: Version 2023.12.0 or later
- **Python**: 3.8 or later (for ESPHome)
- **Home Assistant** (optional): For integration
- **MQTT Broker** (optional): For standalone operation

### Hardware Requirements

Refer to the specific device documentation for hardware requirements, but generally you'll need:

- ESP32 or ESP8266 microcontroller
- USB cable for programming
- Breadboard or PCB for prototyping
- Sensors and components as specified

## Installation Steps

### 1. Install ESPHome

#### Using pip (recommended)

```bash
pip install esphome
```

#### Using Home Assistant Add-on

1. Go to Home Assistant → Add-ons
2. Search for "ESPHome"
3. Install and start the add-on

#### Using Docker

```bash
docker run --rm -v "${PWD}":/config -it esphome/esphome
```

### 2. Clone the Repository

```bash
git clone https://github.com/codifierr/esphome-device-collection.git
cd esphome-device-collection
```

### 3. Set Up Secrets

```bash
# Copy the template
cp secrets-template.yaml secrets.yaml

# Edit with your values
nano secrets.yaml  # or use your preferred editor
```

### 4. Choose Your Device Configuration

Navigate to the appropriate device category:

- `water-tank-controllers/`
- `climate-sensors/`
- `relay-controllers/`

### 5. Customize Configuration

1. Copy the desired YAML file to your ESPHome config directory
2. Modify device-specific parameters:
   - Device name
   - GPIO pin assignments
   - Sensor calibrations
   - Network settings

### 6. Compile and Upload

```bash
# Compile the firmware
esphome compile your-device.yaml

# Upload to device (first time via USB)
esphome upload your-device.yaml

# For subsequent updates (over-the-air)
esphome upload your-device.yaml --device IP_ADDRESS
```

## Configuration Examples

### Basic Setup

```yaml
esphome:
  name: my-tank-controller
  friendly_name: "My Water Tank"

# Include secrets
<<: !include secrets.yaml

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password
```

### Pin Assignments

Update GPIO pins according to your wiring:

```yaml
sensor:
  - platform: ultrasonic
    trigger_pin: GPIO23  # Change as needed
    echo_pin: GPIO22     # Change as needed
```

## Troubleshooting

### Common Issues

#### 1. Compilation Errors

- Check ESPHome version compatibility
- Verify YAML syntax
- Ensure all required secrets are defined

#### 2. Upload Failures

- Check USB cable and connection
- Verify correct serial port
- Try holding BOOT button during upload

#### 3. WiFi Connection Issues

- Verify WiFi credentials in secrets.yaml
- Check signal strength
- Ensure 2.4GHz network (ESP doesn't support 5GHz)

#### 4. Sensor Reading Issues

- Verify wiring connections
- Check power supply voltage
- Review sensor specifications

### Debug Mode

Enable debug logging for troubleshooting:

```yaml
logger:
  level: DEBUG
```

### Getting Help

1. **Check device-specific documentation**
2. **Review ESPHome logs** for error messages
3. **Verify hardware connections**
4. **Search existing issues** on GitHub
5. **Join the community** discussions

## Integration with Home Assistant

### Automatic Discovery

If you have Home Assistant and ESPHome configured properly, devices should appear automatically in:

- Settings → Devices & Services → ESPHome

### Manual Configuration

Add to Home Assistant `configuration.yaml`:

```yaml
esphome:
  devices:
    - host: devices.local  # Your device hostname
      password: !secret api_password
```

## MQTT Integration

```yaml
mqtt:
  broker: mqttbroker.local
  username: !secret mqtt_username
  password: !secret mqtt_password
### Broker Setup

Configure MQTT in your secrets.yaml:

```yaml
mqtt_broker: "mqttbroker.local"
mqtt_username: "your_username"
mqtt_password: "your_password"
```

### Topics

Devices publish to topics like:

- `homeassistant/sensor/device_name/temperature/state`
- `homeassistant/switch/device_name/pump/state`

## Security Considerations

### Network Security

- Use strong WiFi passwords
- Consider VLANs for IoT devices
- Regular firmware updates

### Device Security

- Change default passwords
- Use API encryption
- Secure physical access

## Maintenance

### Regular Tasks

- Monitor device logs
- Update ESPHome versions
- Check sensor calibrations
- Backup configurations

### Performance Monitoring

- Watch memory usage
- Monitor WiFi signal strength
- Check update frequencies

## Next Steps

1. **Test basic functionality** first
2. **Add advanced features** gradually
3. **Create automation** in Home Assistant
4. **Monitor and maintain** your devices
5. **Contribute improvements** back to the project

For device-specific instructions, refer to the README files in each category directory.
