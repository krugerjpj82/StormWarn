# ⚠️ StormWarn

**Real-time weather warnings and forecasts for South Africa**

A clean, fast, and reliable weather app providing current conditions, intelligent warnings, and 10-day forecasts with a focus on severe weather alerts.

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen)](https://stormwarn.manus.space)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

![StormWarn Screenshot](screenshot.png)

## ✨ Features

### 🌤️ **Current Weather**
- Real-time temperature and conditions
- Wind speed and direction
- Humidity and pressure
- "Feels like" temperature
- Precipitation probability
- Weather condition icons

### ⚠️ **Intelligent Weather Warnings**
- **10-level warning system** (SAWS-aligned)
- Color-coded severity (Red/Orange/Yellow)
- Detailed safety instructions
- Multi-hazard detection:
  - Wind warnings (40-75+ km/h)
  - Heat warnings (35-43+ °C)
  - Cold warnings (-10 to 5°C)
  - Thunderstorm alerts
  - Fire danger warnings
  - Fog, snow, and ice alerts

### 📅 **10-Day Forecast**
- Daily high/low temperatures
- Weather conditions with icons
- Precipitation probability
- Wind speed alerts
- Easy-to-scan vertical layout

### 🔍 **Location Features**
- Automatic geolocation
- Search any location worldwide
- Save favorite locations
- Default to Cape Town, South Africa
- Persistent saved locations

### 📱 **Share Weather**
- One-click WhatsApp sharing
- Formatted messages with warnings
- Official WhatsApp logo integration
- Share current conditions or alerts

## 🚀 Quick Start

### Option 1: GitHub Pages (Recommended)

1. Fork this repository
2. Go to Settings → Pages
3. Select main branch as source
4. Your app will be live at `https://yourusername.github.io/stormwarn`

### Option 2: Local Development

```bash
# Clone the repository
git clone https://github.com/yourusername/stormwarn.git
cd stormwarn

# Open in browser
open index.html
```

That's it! No build process, no dependencies, no configuration needed.

## 📖 Usage

### Basic Usage
1. Allow location access (or it defaults to Cape Town)
2. View current weather and warnings
3. Scroll down for 10-day forecast
4. Click WhatsApp button to share

### Search Locations
1. Type location name in search bar
2. Select from dropdown results
3. Click "⭐ Save Location" to remember it

### Saved Locations
- Click any saved location chip to switch
- Click × to remove a location
- Locations persist in browser storage

## 🏗️ Technical Details

### Built With
- **Pure HTML/CSS/JavaScript** - No frameworks or build tools
- **Open-Meteo API** - Free weather data (no API key required)
- **Geocoding API** - Location search and reverse geocoding
- **localStorage** - Persistent saved locations

### Browser Support
- ✅ Chrome/Edge (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Mobile browsers (iOS/Android)

### Performance
- 📦 Single HTML file (~25KB)
- ⚡ Fast load time (<1 second)
- 🌐 Works offline after first load
- 💾 Minimal data usage

### APIs Used

**Open-Meteo Weather API**
- Endpoint: `https://api.open-meteo.com/v1/forecast`
- Free, no API key required
- Global coverage
- Real-time data

**BigDataCloud Reverse Geocoding**
- Endpoint: `https://api.bigdatacloud.net/data/reverse-geocode-client`
- Free, no API key required
- Location name resolution

**Open-Meteo Geocoding**
- Endpoint: `https://geocoding-api.open-meteo.com/v1/search`
- Free, no API key required
- Location search

## ⚙️ Configuration

### Change Default Location

Edit line ~450 in `index.html`:

```javascript
// Change these coordinates to your preferred default location
fetchWeather(-33.9249, 18.4241); // Cape Town coordinates
```

### Customize Warning Thresholds

Edit the `generateWarnings()` function (~100-250) to adjust when warnings trigger:

```javascript
// Example: Change wind warning threshold
if (current.wind_speed_10m >= 50) { // Default is 50 km/h
    // Your custom threshold
}
```

## 📱 Deploy to Production

### Deploy to Netlify
1. Drop `index.html` into [Netlify Drop](https://app.netlify.com/drop)
2. Done! Your app is live.

### Deploy to Vercel
```bash
vercel deploy
```

### Deploy to GitHub Pages
1. Push to GitHub
2. Enable GitHub Pages in Settings
3. Select main branch

## 🤝 Contributing

Contributions are welcome! Here's how:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Keep it simple - single HTML file
- No build process required
- Test on mobile devices
- Follow existing code style
- Add comments for complex logic

## 🐛 Known Issues

- SAWS RSS feed may be blocked by CORS (local warnings work as fallback)
- Geolocation may be slow on first request (10-second timeout)
- Some browsers block WhatsApp sharing (use native share instead)

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Weather data from [Open-Meteo](https://open-meteo.com/)
- Warning system aligned with [SAWS](https://www.weathersa.co.za/) standards
- Icons from Unicode emoji standard
- WhatsApp logo from official brand assets

## 📧 Contact

**StormWarn** - [GitHub Profile](https://github.com/krugerjpj82)

Project Link:  https://krugerjpj82.github.io/StormWarn/


---

**Made with ❤️ in South Africa**

Stay safe, stay informed! 🌤️⚠️
