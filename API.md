# API Documentation

## Overview

StormWarn uses free, no-authentication-required APIs for all weather data.

## Weather Data API

### Open-Meteo Forecast API

**Endpoint:** `https://api.open-meteo.com/v1/forecast`

**Parameters:**
- `latitude` - Location latitude (required)
- `longitude` - Location longitude (required)
- `current` - Current weather variables (comma-separated)
- `hourly` - Hourly forecast variables (comma-separated)
- `daily` - Daily forecast variables (comma-separated)
- `timezone` - Timezone for timestamps (default: auto)
- `forecast_days` - Number of forecast days (default: 7, max: 16)

**Current Weather Variables Used:**
- `temperature_2m` - Temperature at 2 meters (°C)
- `relative_humidity_2m` - Relative humidity (%)
- `apparent_temperature` - Feels like temperature (°C)
- `weather_code` - WMO weather code
- `wind_speed_10m` - Wind speed at 10m (km/h)
- `wind_direction_10m` - Wind direction (degrees)
- `pressure_msl` - Sea level pressure (hPa)

**Daily Variables Used:**
- `weather_code` - Daily weather code
- `temperature_2m_max` - Maximum temperature (°C)
- `temperature_2m_min` - Minimum temperature (°C)
- `precipitation_sum` - Total precipitation (mm)
- `precipitation_probability_max` - Max precipitation probability (%)
- `wind_speed_10m_max` - Maximum wind speed (km/h)

**Example Request:**
```
https://api.open-meteo.com/v1/forecast?latitude=-33.9249&longitude=18.4241&current=temperature_2m,relative_humidity_2m,apparent_temperature,weather_code,wind_speed_10m,wind_direction_10m,pressure_msl&hourly=precipitation_probability&daily=weather_code,temperature_2m_max,temperature_2m_min,precipitation_sum,precipitation_probability_max,wind_speed_10m_max&timezone=auto&forecast_days=14
```

**Response Format:**
```json
{
  "current": {
    "time": "2024-12-27T15:00",
    "temperature_2m": 28.5,
    "relative_humidity_2m": 65,
    "apparent_temperature": 30.2,
    "weather_code": 0,
    "wind_speed_10m": 15.3,
    "wind_direction_10m": 45,
    "pressure_msl": 1013.2
  },
  "hourly": {
    "time": [...],
    "precipitation_probability": [...]
  },
  "daily": {
    "time": [...],
    "weather_code": [...],
    "temperature_2m_max": [...],
    "temperature_2m_min": [...],
    "precipitation_sum": [...],
    "precipitation_probability_max": [...],
    "wind_speed_10m_max": [...]
  }
}
```

## Geocoding API

### Open-Meteo Geocoding API

**Endpoint:** `https://geocoding-api.open-meteo.com/v1/search`

**Parameters:**
- `name` - Location name to search (required)
- `count` - Number of results (default: 10)
- `language` - Result language (default: en)
- `format` - Response format (default: json)

**Example Request:**
```
https://geocoding-api.open-meteo.com/v1/search?name=Cape%20Town&count=5&language=en&format=json
```

**Response Format:**
```json
{
  "results": [
    {
      "id": 3369157,
      "name": "Cape Town",
      "latitude": -33.92584,
      "longitude": 18.42322,
      "country": "South Africa",
      "admin1": "Western Cape"
    }
  ]
}
```

### BigDataCloud Reverse Geocoding

**Endpoint:** `https://api.bigdatacloud.net/data/reverse-geocode-client`

**Parameters:**
- `latitude` - Location latitude (required)
- `longitude` - Location longitude (required)
- `localityLanguage` - Language for results (default: en)

**Example Request:**
```
https://api.bigdatacloud.net/data/reverse-geocode-client?latitude=-33.9249&longitude=18.4241&localityLanguage=en
```

**Response Format:**
```json
{
  "city": "Cape Town",
  "locality": "Cape Town",
  "principalSubdivision": "Western Cape",
  "countryName": "South Africa"
}
```

## Weather Codes

WMO Weather Interpretation Codes used by Open-Meteo:

| Code | Description |
|------|-------------|
| 0 | Clear sky |
| 1 | Mainly clear |
| 2 | Partly cloudy |
| 3 | Overcast |
| 45 | Fog |
| 48 | Depositing rime fog |
| 51 | Light drizzle |
| 53 | Moderate drizzle |
| 55 | Dense drizzle |
| 61 | Slight rain |
| 63 | Moderate rain |
| 65 | Heavy rain |
| 71 | Slight snow fall |
| 73 | Moderate snow fall |
| 75 | Heavy snow fall |
| 80 | Slight rain showers |
| 81 | Moderate rain showers |
| 82 | Violent rain showers |
| 95 | Thunderstorm |
| 96 | Thunderstorm with slight hail |
| 99 | Thunderstorm with heavy hail |

## Rate Limits

### Open-Meteo
- **Rate Limit:** ~10,000 requests per day for free tier
- **Recommendation:** Cache responses when possible
- **No API Key Required**

### BigDataCloud
- **Rate Limit:** Generous free tier
- **No API Key Required**

## Error Handling

All APIs may return errors. Common error responses:

**Network Error:**
```javascript
try {
  const response = await fetch(url);
  if (!response.ok) {
    throw new Error(`API error: ${response.status}`);
  }
} catch (error) {
  console.error('Failed to fetch:', error);
}
```

**No Results:**
```json
{
  "results": []
}
```

## CORS

All APIs used support CORS and can be called directly from the browser.

## Attribution

When using these APIs, please:
- ✅ Follow their terms of service
- ✅ Don't abuse rate limits
- ✅ Consider their premium tiers for high-volume use
- ✅ Credit data sources in your app

## References

- [Open-Meteo Documentation](https://open-meteo.com/en/docs)
- [Open-Meteo Geocoding](https://open-meteo.com/en/docs/geocoding-api)
- [BigDataCloud Docs](https://www.bigdatacloud.com/docs)
