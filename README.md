# 🌌 Stargazing Planner

A browser-based stargazing session planner built for the **SEDS (Students for the Exploration and Development of Space)** telescope club. Enter any date, time, and location to get a complete sky report — no apps, no accounts, no API keys needed.

![Stargazing Planner Screenshot](docs/preview.png)

---

## ✨ Features

| Feature | Details |
|---|---|
| **Live weather** | Cloud cover, temperature, humidity, wind, precipitation, visibility |
| **Moon phase** | Phase name, illumination %, moonrise & moonset times |
| **Planet visibility** | Mercury, Venus, Mars, Jupiter, Saturn — evening/morning/night |
| **Bonus objects** | Seasonal deep sky objects: Milky Way, Orion Nebula, meteor showers, etc. |
| **Session score** | 0–100 rating combining all factors at a glance |
| **Session tips** | Contextual advice based on the night's conditions |
| **Location modes** | Auto-detect via browser GPS or manual city name entry |

---

## 🚀 Quick Start

This is a **zero-dependency, single-file web app**. No build tools, no npm, no server required.

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/stargazing-planner.git
cd stargazing-planner

# Open directly in your browser
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

Or just double-click `index.html`. That's it.

---

## 📂 Project Structure

```
stargazing-planner/
├── index.html          # Complete app — HTML, CSS, and JS in one file
├── docs/
│   └── preview.png     # Screenshot for README
└── README.md
```

The entire app is self-contained in `index.html` — intentional. The goal is that any SEDS member can clone this, open the file, and use it immediately.

---

## 🔌 APIs Used

All APIs are **free and require no API key**.

| API | Used for |
|---|---|
| [Open-Meteo](https://open-meteo.com/) | Weather forecast (cloud cover, temperature, wind, etc.) |
| [Open-Meteo Geocoding](https://open-meteo.com/en/docs/geocoding-api) | City name → coordinates lookup |
| [Nominatim (OpenStreetMap)](https://nominatim.openstreetmap.org/) | Reverse geocoding (GPS coords → city name) |
| Browser Geolocation API | Auto-detect user's current position |

Moon phase, moonrise/set, and planet visibility are calculated **entirely in JavaScript** using astronomy algorithms — no external API needed.

---

## 🧮 How the Astronomy Works

### Moon Phase
Uses the synodic period of the Moon (29.53 days) referenced from a known new moon date (Jan 6, 2000). The current phase age is computed and mapped to one of 8 named phases. Illumination percentage is derived from the phase angle.

### Moonrise & Moonset
Approximates the Moon's declination and hour angle using simplified orbital elements, then computes rise/set times relative to the observer's latitude and longitude.

### Planet Visibility
Each planet's approximate sky position is estimated from its orbital period and a base angle referenced to J2000. Elongation from the Sun determines whether the planet appears in the evening sky, morning sky, or is well-placed for observation.

These are **approximations** — sufficient for session planning, not for precise ephemeris work. For high-accuracy data, see [JPL Horizons](https://ssd.jpl.nasa.gov/horizons/).

---

## 🌐 Deploy Online (Optional)

To share with your SEDS club, deploy for free:

**GitHub Pages** (simplest):
1. Go to your repo → Settings → Pages
2. Set source to `main` branch, `/ (root)`
3. Your app is live at `https://YOUR_USERNAME.github.io/stargazing-planner/`

**Netlify** (drag & drop):
1. Go to [netlify.com](https://netlify.com) → Add new site → Deploy manually
2. Drag the project folder into the upload area
3. Done — live URL in seconds.

---

## 🛠 Extending This Project

Ideas for future improvements:

- [ ] **ISS pass times** — using [Open Notify API](http://open-notify.org/Open-Notify-API/ISS-Pass-Times/)
- [ ] **Bortle scale estimator** — estimate light pollution from coordinates
- [ ] **Export to PDF** — session report card to share with club
- [ ] **Recurring session planner** — find the best night in a given week
- [ ] **Telescope FOV overlay** — show what fits in eyepiece for a given object
- [ ] **Push notifications** — alert when a good night is coming up

Pull requests are welcome!

---

## 📸 How to Add a Preview Screenshot

1. Open `index.html` in your browser
2. Plan a session with good conditions
3. Take a screenshot and save it as `docs/preview.png`
4. Commit and push — it will appear in this README automatically

---

## 🔭 About

Built by a member of **SEDS (Students for the Exploration and Development of Space)** to solve a real problem: forgetting to check conditions before telescope sessions. 

No frameworks. No build step. Pure HTML, CSS, and vanilla JavaScript.

---

## 📄 License

MIT — free to use, modify, and share.
