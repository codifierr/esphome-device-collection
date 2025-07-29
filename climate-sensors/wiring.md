# DHT Climate Sensor Wiring Guide

This guide describes the wiring for the DHT climate sensor implementation (`dht-climate-sensor.yaml`).

## Components
- ESP8266 (NodeMCU v2 board recommended)
- DHT11 or DHT22 sensor
- 4.7kΩ pull-up resistor
- Jumper wires

## Wiring Diagram

### ESP8266 Pin Assignments
- **DHT DATA:** GPIO14 (default in YAML, configurable)

### DHT Sensor
- **VCC:** 3.3V (NodeMCU)
- **GND:** GND
- **DATA:** GPIO14 (NodeMCU)
- **Pull-up resistor:** 4.7kΩ between DATA and VCC

### Example Wiring Table
| Component      | ESP8266 Pin | Notes                        |
|---------------|-------------|------------------------------|
| DHT DATA      | GPIO14      | Sensor data pin              |
| DHT VCC       | 3.3V        | Power for sensor             |
| DHT GND       | GND         | Ground                       |
| Pull-up Resistor | -        | 4.7kΩ between DATA and VCC   |

## Power Supply
- Use the onboard micro-USB 5V supply for NodeMCU
- Sensor powered from NodeMCU 3.3V pin

## Safety Tips
- Power off before wiring
- Double-check pin assignments
- Use proper resistor value for reliable readings
- Avoid long wires for DATA to reduce signal issues

Refer to the main README for configuration and safety guidelines.
