# Changelog

All notable changes to StormWarn will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2024-12-27

### Added
- **Current Weather Display**
  - Real-time temperature and conditions
  - Wind speed and direction
  - Humidity and pressure
  - Feels-like temperature
  - Precipitation probability
  - Weather condition icons

- **Weather Warning System**
  - 10-level SAWS-aligned warning system
  - Color-coded severity (Red/Orange/Yellow)
  - Multi-hazard detection (wind, heat, cold, storms, fire, fog, snow)
  - Detailed safety instructions
  - Automatic warning generation

- **10-Day Forecast**
  - Daily high/low temperatures
  - Weather conditions with icons
  - Precipitation probability
  - Wind speed warnings
  - Vertical list layout

- **Location Features**
  - Automatic geolocation with Cape Town fallback
  - Search any location worldwide
  - Save favorite locations
  - Persistent localStorage
  - Active location highlighting

- **WhatsApp Sharing**
  - One-click weather sharing
  - Official WhatsApp logo
  - Formatted messages with warnings
  - Includes all current conditions

### Technical
- Single HTML file architecture
- No build process required
- Open-Meteo API integration
- Geocoding API integration
- Responsive design
- Mobile-optimized

### Documentation
- Comprehensive README
- Contributing guidelines
- MIT License
- Changelog
