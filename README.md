# China Trip Planner

A planner for our Shanghai and Chongqing trip. It's a single page with no build step and no backend.

## Features

- **Plan:** set the dates for each city and the days are created for you. Add stops (food, cafés, sights, activities, shopping, nights out, transport, hotel) with times, places, notes and a budget. Each stop gets a photo and Amap and Google Maps links. A side panel holds your dates, totals, a currency converter and the share and backup tools.
- **Map:** filter Shanghai and Chongqing by category. Verified locations use color-coded icon pins (sights, activities, shows, food, cafés, shopping, nightlife, transport and day trips). Each pin links to Amap, Apple Maps and Google Maps. Guide venues without confirmed coordinates appear in an Amap/Apple location directory instead of being pinned at a guessed point; your own dated stops remain visible.
- **Guides:** Shanghai and Chongqing categorized as Sights & places, Activities & theme parks, Shows & experiences, Day trips, Shopping & brands, Cafés & desserts, Food & restaurants, Nightlife & views and Unique transport. Cards include clear category badges; individually curated Wikipedia lead photos are used only for confirmed subjects, otherwise a category illustration is shown. November-specific hours, booking links, visit length, travel estimates and seasonal cautions appear where researched.
- **China 101:** three tabs. Essentials (payments, internet, transport, emergency numbers, manners), Phrases you can show full screen, and Fun facts about China, Shanghai and Chongqing.
- **Lists:** a before-we-fly checklist grouped into documents, money and phone, apps and packing, and souvenirs grouped by where to buy them.
- **Share:** "Share with my partner" creates a link that has the whole plan inside it.
- **Calendar:** download a `.ics` file with every stop at the right China time.
- **Light and dark mode.**

Anyone with the link can view the plan. Only the owner can edit. The first time, sign in with a fine-grained GitHub token (the site gives a pre-filled link) and choose a password. After that, any device signs in with just the password. The token is stored in `auth.json` encrypted with that password (AES-GCM, PBKDF2), and every change is saved to `plan.json`.

## Services used

All free, with no API keys:

- [Wikipedia](https://www.wikipedia.org) API for confirmed Wikipedia subject images only; uncertain venues use category icons instead of unrelated search-result photos
- [OpenStreetMap](https://www.openstreetmap.org) and [CARTO](https://carto.com) map tiles, shown with [Leaflet](https://leafletjs.com)
- [Open-Meteo](https://open-meteo.com) for weather
- [ExchangeRate-API](https://www.exchangerate-api.com) open endpoint for CNY, SAR and USD rates

## Run locally

Open `index.html` in a browser, or serve the folder with any static server:

```sh
python3 -m http.server
```

## Mapping and photo accuracy

- The map is rendered with Leaflet and CARTO / OpenStreetMap tiles. Amap and Google Maps JavaScript SDKs require project/API credentials; this public static site does not ship any map-provider keys.
- External Amap/Apple/Google links are intended for turn-by-turn navigation. Map pin coordinates are approximate and must be verified, particularly in multi-level Chongqing. Unknown locations are listed separately, never placed at the city center.
- Category groupings are **presentation-only**. They do not change existing saved itinerary item IDs or `plan.json`.
- Photo display uses a specific allowlist of Wikipedia article titles. Missing or unverified pictures fall back to a category visual; never auto-assign a broadly searched unrelated photo.
- Seasonal event schedules may change. Double-check booking pages before travel.
