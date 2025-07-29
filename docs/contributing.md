# Contributing to ESPHome Device Collection

Thank you for your interest in contributing to the ESPHome Device Collection! This document provides guidelines for contributing to this project.

## How to Contribute

### 1. Reporting Issues

- Use the GitHub issue tracker to report bugs
- Include detailed information about your setup
- Provide error logs and configuration details
- Include your ESPHome version and hardware details

### 2. Suggesting Features

- Check existing issues and discussions first
- Use the feature request template
- Provide clear use cases and benefits
- Include mockups or examples if applicable

### 3. Contributing Code

#### Device Configurations

When adding new device configurations:

1. **Create a new directory** for device category if it doesn't exist
2. **Follow naming conventions**: `device-type-variant.yaml`
3. **Include comprehensive documentation**
4. **Test thoroughly** before submitting
5. **Add wiring diagrams** if possible

#### Documentation

- Update README files for new categories
- Include hardware requirements
- Provide clear installation instructions
- Add safety warnings where appropriate

## Code Standards

### YAML Configuration Standards

```yaml
# Use consistent indentation (2 spaces)
esphome:
  name: device-name
  friendly_name: "Device Friendly Name"

# Include proper comments
sensor:
  # Temperature sensor using DHT22
  - platform: dht
    pin: GPIO4
    model: DHT22
```

### Documentation Standards

- Use clear, concise language
- Include all necessary hardware information
- Provide step-by-step instructions
- Add troubleshooting sections
- Include safety warnings

### Naming Conventions

- **Files**: Use kebab-case (`water-tank-controller.yaml`)
- **Entities**: Use descriptive names (`"Water Tank Level"`)
- **IDs**: Use snake_case (`tank_level_sensor`)

## Testing Requirements

Before submitting:

1. **Compile successfully** with ESPHome
2. **Test on actual hardware** when possible
3. **Verify all features** work as documented
4. **Check for resource conflicts** (pin assignments, etc.)
5. **Validate with Home Assistant** integration

## Submission Process

### Pull Request Guidelines

1. **Fork the repository** and create a feature branch
2. **Make atomic commits** with clear messages
3. **Update documentation** as needed
4. **Test your changes** thoroughly
5. **Submit a pull request** with detailed description

### PR Description Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] New device configuration
- [ ] Bug fix
- [ ] Documentation update
- [ ] Feature enhancement

## Hardware Tested
- ESP32/ESP8266 model
- Sensor/component models
- ESPHome version

## Testing Checklist
- [ ] Configuration compiles successfully
- [ ] Tested on actual hardware
- [ ] Documentation updated
- [ ] All features work as expected
```

## Review Process

1. **Automated checks** will run on your PR
2. **Maintainer review** for code quality and standards
3. **Community feedback** may be requested
4. **Testing verification** on similar hardware
5. **Merge** after approval

## Device Categories

### Current Categories

- Water Tank Controllers
- Climate Sensors
- Relay Controllers

### Adding New Categories

When proposing new categories:

1. Ensure sufficient demand/interest
2. Create comprehensive documentation
3. Include multiple device variants
4. Provide clear hardware requirements

## Safety Guidelines

### Electrical Safety

- Always include appropriate warnings
- Specify voltage/current requirements
- Recommend proper fusing/protection
- Suggest professional installation for mains voltage

### Code Safety

- Implement fail-safe mechanisms
- Include timeout protections
- Add input validation
- Document safety features

## Community Guidelines

### Code of Conduct

- Be respectful and inclusive
- Help newcomers learn
- Provide constructive feedback
- Focus on technical merit

### Communication

- Use clear, professional language
- Be patient with questions
- Share knowledge freely
- Acknowledge contributions

## Getting Help

- **GitHub Discussions**: General questions and ideas
- **Issues**: Bug reports and feature requests
- **ESPHome Discord**: Real-time community support
- **Home Assistant Community**: Integration questions

## Recognition

Contributors will be:

- Listed in project contributors
- Acknowledged in release notes
- Credited in device documentation
- Invited to join the maintainer team (for significant contributions)

Thank you for contributing to the ESPHome Device Collection! 🚀
