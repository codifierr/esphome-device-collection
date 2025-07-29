# Water Tank Controllers

This directory contains ESPHome configurations for water tank monitoring and control systems.

## Available Configurations

### OHT Water Level Controller (`OHT-controller.yaml`)

- Advanced water tank automation for Overhead Tank (OHT)
- Scheduled pump runs (morning/evening)
- Dry run protection and automatic recovery
- Zero distance safety and auto-restart
- Manual scheduled run trigger
- MQTT and Home Assistant integration
- Highly customizable via substitutions
- Real-time water level and percentage sensors
- Detailed status and protection reporting

**Hardware Required:**

- ESP32 (esp32dev board recommended)
- Ultrasonic sensor (HC-SR04 or compatible)
- Relay module for pump control
- Water pump

**Key Features:**

- Scheduled runs at configurable times (default: 11:00 AM, 3:00 PM)
- Dry run protection: stops pump if water flow is insufficient
- Zero distance detection: restarts device if sensor fails
- Manual scheduled run via switch
- MQTT birth/will messages for device status
- Home Assistant API with encryption
- Customizable debounce, thresholds, and timings

**Configurable Parameters (substitutions):**

- `tank_height`: Tank height in cm
- `water_stop_distance`: Distance to stop pump (tank full)
- `water_level_low`: Distance to start pump (low level)
- `max_range`: Maximum sensor range
- `scheduled_run_duration`: Duration of scheduled run (seconds)
- `morning_run_hour`/`minute`: Morning run time
- `evening_run_hour`/`minute`: Evening run time
- `dry_run_check_delay`/`interval`/`min_water_level_increase`: Dry run protection settings
- And more (see YAML for full list)

**How to Use:**

1. Copy `OHT-controller.yaml` to your ESPHome config directory
2. Update `secrets.yaml` with your WiFi, MQTT, and API credentials
3. Adjust substitutions at the top of the YAML for your tank and schedule
4. Wire the ultrasonic sensor and relay as per the pin assignments
5. Compile and upload to your ESP32 device
6. Integrate with Home Assistant or MQTT as needed

**Customization:**

- Change scheduled run times by editing `morning_run_hour`, `evening_run_hour`, etc.
- Adjust dry run protection for your pump and tank size
- Use Home Assistant or MQTT to monitor status and control

## Installation

1. Copy `OHT-controller.yaml` to your ESPHome directory
2. Update `secrets.yaml` with your specific values
3. Modify device-specific parameters in the YAML file
4. Compile and upload to your ESP device

## Wiring Diagrams

See the `wiring/` directory for detailed connection diagrams for each configuration.

## Safety Notes

⚠️ **Important Safety Guidelines:**

- Always use proper electrical isolation when working with water and electricity
- Implement dry-run protection to prevent pump damage
- Use waterproof enclosures for electronics
- Test all safety features before deployment
