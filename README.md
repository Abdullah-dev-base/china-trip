# China Trip Planner

A planner for our Shanghai and Chongqing trip. It's a single page with no build step and no backend.

## Features

- **Plan:** set the dates for each city and the days are created for you. Add stops (food, cafés, sights, activities, shopping, nights out, transport, hotel) with times, places, notes and a budget. Each stop gets a photo and Amap and Google Maps links. A side panel holds your dates, totals, a currency converter and the share and backup tools.
- **Map:** every place from the guides plus your own stops, with photos in the pins.
- **Guides:** Shanghai and Chongqing with photos: places to visit, food to try, cafés and cool spots, live and typical weather, fun facts and funny stuff. Tap a photo for details.
- **China 101:** the basics (payments, internet, transport, emergency numbers), phrases you can show full screen, do's and don'ts, interesting and funny facts.
- **Lists:** souvenirs to buy (with photos) and a before-we-fly checklist.
- **Share:** "Share with my partner" creates a link that has the whole plan inside it.
- **Calendar:** download a `.ics` file with every stop at the right China time.
- **Light and dark mode.**

Your plan is saved in your browser's local storage. Nothing is sent to a server. To move it between devices, use the share link or Backup and Restore.

## Services used

All free, with no API keys:

- [Wikipedia](https://www.wikipedia.org) API for photos (free-licensed lead images from Wikimedia Commons)
- [OpenStreetMap](https://www.openstreetmap.org) and [CARTO](https://carto.com) map tiles, shown with [Leaflet](https://leafletjs.com)
- [Open-Meteo](https://open-meteo.com) for weather
- [ExchangeRate-API](https://www.exchangerate-api.com) open endpoint for CNY, SAR and USD rates

## Run locally

Open `index.html` in a browser, or serve the folder with any static server:

```sh
python3 -m http.server
```
