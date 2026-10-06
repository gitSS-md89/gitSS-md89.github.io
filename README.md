# Vataavaran

Vataavaran is a dependency-free static weather site. The complete app is in
`index.html`; it can be deployed as-is to any static host or copied into an
existing web project as a standalone route.

## Run locally

Open `index.html` in a browser, or serve this folder with any local static file
server. Live weather and city search require an internet connection.

## Add to another site

Copy the `vataavaran/` folder into the target repository and publish it as a
static route, for example `/weather/`. To embed it inside an existing page, use:

```html
<iframe
  src="/weather/"
  title="Vataavaran weather"
  loading="lazy"
  style="width: 100%; min-height: 900px; border: 0"
></iframe>
```

The app uses Open-Meteo for weather, air quality and city geocoding, and
Zippopotam.us for Indian PIN-code lookup. These browser requests need network
access. If the air-quality service is unavailable, its panel shows the service
error while the weather forecast remains available. Device location is optional
and requires the browser's permission (and HTTPS or localhost when hosted).

The voice assistant uses the browser's Web Speech APIs for microphone speech
recognition and spoken weather briefs. Browser support varies; Chrome and Edge
on a secure origin (HTTPS or localhost) are recommended. Microphone permission
is requested by the browser when you start voice input. Say a place name (for
example, “weather in Tokyo”) to look it up; when no place is spoken, Vataavaran
requests device location and falls back to the currently selected place if that
permission is unavailable. The voice reply covers current observations,
today's highs/lows, sunrise/sunset, rain and commute risk, the available 7-day
forecast and the honest monthly forecast window.

Rain, air-quality and severe-weather notifications are optional. They require
notification permission and the app to remain open; alerts are deduplicated by
location, local date and hazard. These are model-based indicators for pollution,
dust, thunderstorms, heavy rain, high winds and extreme heat/cold—not official
emergency warnings. The site does not connect to government disaster-warning
or earthquake feeds; follow local authorities for emergency information.

The air-quality panel shows modelled US and European AQI values and available
pollutant readings. The local environmental impact rating is a heuristic based
on AQI and weather hazards, not a personal carbon-footprint score. The Climate
Clock is an illustrative estimate based on a 235 GtCO₂ budget at 1 January
2025 and constant annual emissions of 42.4 GtCO₂; it is not an official
countdown or a precise deadline. Its assumptions are shown in the app.
