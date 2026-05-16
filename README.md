# Halāl Map 🕌

An interactive, live halal food finder — single HTML file, no build step, free to host.

## One-Click Deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/YOUR_USERNAME/halal-map)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/YOUR_USERNAME/halal-map)

> **Before using the buttons:** Replace `YOUR_USERNAME` with your actual GitHub username in the URLs above, then push this repo to GitHub. The buttons will then work for anyone who visits your repo.

---

## Features
- 🗺 Live data from OpenStreetMap via Overpass API (no API key needed)
- 📍 Auto-detect your location
- 🔍 Search any city, area or postcode (UK & worldwide)
- 🎛 Filter by cuisine: Indian, Turkish, Lebanese, Pakistani, Arabic, Chinese
- 📏 Adjustable search radius (500m – 5km)
- 🟡 Verified halal markers (restaurants tagged `diet:halal=yes`)
- 📱 Mobile-responsive with sidebar toggle
- 🌑 Dark Islamic-gold theme, marker clustering

---

## Hosting Options

### Option 1 — GitHub Pages (recommended, free)

1. Create a new GitHub repo (e.g. `halal-map`)
2. Push `index.html` to the repo root
3. Go to **Settings → Pages → Source: main branch / root**
4. Your site will be live at `https://yourusername.github.io/halal-map`

```bash
git init
git add index.html
git commit -m "Initial halal map"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/halal-map.git
git push -u origin main
```

### Option 2 — Netlify Drop (instant, no account needed)

1. Go to https://app.netlify.com/drop
2. Drag and drop index.html
3. Get a live URL immediately (e.g. https://random-name.netlify.app)

### Option 3 — Vercel

```bash
npm i -g vercel
vercel --yes
```

---

## Customisation

### Change default location
In index.html, find:
```js
initMap(); // defaults to London lat/lon
```
Replace with:
```js
initMap(51.5136, -0.1585); // e.g. Marble Arch
```

### Change default search radius
```js
let searchRadius = 1500; // metres — change this
```

### Add more cuisine filters
Add a chip in the #filters div:
```html
<button class="filter-chip" data-cuisine="afghan" onclick="setFilter(this)">Afghan</button>
```

### Add your own known spots
After the window load listener, add manual markers using makeIcon() and L.marker().

---

## Tech Stack
| Library | Purpose |
|---------|---------|
| Leaflet.js v1.9.4 | Interactive map |
| Leaflet.MarkerCluster | Cluster overlapping pins |
| Overpass API | Live OSM restaurant data |
| Nominatim | Geocoding (search to lat/lon) |

All free. No API keys. No backend.

---

## Improving data coverage
If you find a missing halal restaurant, add it to OpenStreetMap at https://www.openstreetmap.org
Tag it with `diet:halal=yes` and it will appear in this map within minutes.
