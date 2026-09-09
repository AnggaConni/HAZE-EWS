# 🌋🔥 HazeGuard EWS | Wildfire Smoke, Volcanic Ash, Industrial Pollution & Tsunami Early Warning System

[![PWA Ready](https://img.shields.io/badge/PWA-Online%20First-c2410c?style=for-the-badge&logo=pwa)](https://pwabuilder.com)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Architecture](https://img.shields.io/badge/Architecture-Serverless%20%2F%20Client--Side-0ea5e9?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![Data Protection](https://img.shields.io/badge/Privacy-100%25%20Local%20(IndexedDB)-10b981?style=for-the-badge)](#-privacy--zero-server-data-guarantee)

**HazeGuard EWS** is a zero-cost, serverless Progressive Web Application (PWA) designed as an integrated **Impact-Based Early Warning System (IBEWS)** for atmospheric hazards and disaster risks — specifically peatland/wildfire haze (*karhutla*), volcanic ashfall, urban/industrial air pollution, and coastal earthquake/tsunami threats.

By fusing real-time satellite telemetry (NASA FIRMS, NASA GIBS, NASA POWER), global atmospheric reanalysis (CAMS / Open-Meteo Air Quality), live seismic networks (USGS Earthquake API), and localized socio-demographic diagnostic models, HazeGuard transforms complex geophysical data into actionable, community-level health protection strategies.

---

## 📋 Table of Contents

- [✨ Key Features & Capabilities](#-key-features--capabilities)
- [🧮 Scientific & Risk Scoring Methodology](#-scientific--risk-scoring-methodology)
- [🌐 Real-Time API Integrations](#-real-time-api-integrations)
- [📂 Progressive Web App (PWA) & APK Setup](#-progressive-web-app-pwa--apk-setup)
- [🏗️ Technical Architecture & Stack](#️-technical-architecture--stack)
- [🚀 Quick Start & Installation](#-quick-start--installation)
- [📱 Dashboard & UI Modules](#-dashboard--ui-modules)
- [🔒 Privacy & Zero-Server Data Guarantee](#-privacy--zero-server-data-guarantee)
- [👤 Author & Acknowledgments](#-author--acknowledgments)

---

## ✨ Key Features & Capabilities

### 1. 🔥 Wildfire & Peatland Haze Monitoring (*Karhutla*)
- **NASA FIRMS Hotspot Detection**: Real-time satellite thermal anomaly scanning using VIIRS (S-NPP, NOAA-20, NOAA-21 at 375m) and MODIS (1km) sensors.
- **Fire Radiative Power (FRP)**: Calculates megawatts (MW) of fire intensity and proximity/distance (km) relative to target monitoring sites.
- **Smoke Transport & Wind Plume Simulation**: Direct vector analysis of wind direction and speed, rendering visual plume threat cones (*wedge polygons*) and grid-based directional wind fields on an interactive Leaflet map.
- **NASA OMPS Aerosol Index**: Visualizes satellite-detected smoke column density directly on spatial basemaps.

### 2. 🌋 Volcanic Ashfall & Urban/Industrial Air Quality
- **Multi-Hazard Support**: Dynamic threshold monitoring for wildfires, volcanic ash, industrial/vehicle emissions, and coastal tsunami threats.
- **Full Gas & Particulate Suite**: Real-time tracking of PM₂.₅, PM₁₀, Carbon Monoxide (CO), Nitrogen Dioxide (NO₂), Sulphur Dioxide (SO₂), Ozone (O₃), Dust, Aerosol Optical Depth (AOD), and US/European AQI.
- **Volcanic Ash Safeguards**: Asset protection guidelines (roof load clearing, moisture control, eye protection, water source sealing, PVMBG alert level verification).

### 3. 🌊 Real-time Seismic & Tsunami Early Warning
- **USGS Global Seismic Telemetry**: Monitors M ≥ 5.5 earthquakes in real time.
- **Proximity Radius Calculation**: Automatically computes Haversine distance between epicenter and registered monitoring sites.
- **Automated Web Push Notifications**: Triggers native browser push notifications and critical alert banners if a M ≥ 5.5 earthquake occurs within 300 km or triggers a NOAA/USGS tsunami flag.

### 4. 🏥 Health Exposure & Diagnostic Tools
- **Cigarette Equivalence Calculator**: Translates 24-hour PM₂.₅ exposure into equivalent cigarette consumption using the Berkeley Earth model (Cigarettes ≈ PM₂.₅ / 22).
- **ARI / ISPA Clinical Surge Estimator**: Projects community-level Acute Respiratory Infection (*Infeksi Saluran Pernapasan Akut*) medical visit spikes based on exposed population figures and particulate dosage.
- **30-Day Peat Dryness Index**: Queries NASA POWER climate data to track consecutive dry days (<1mm rain) and cumulative precipitation, identifying high-risk subterranean peat ignition windows.
- **DIY Corsi-Rosenthal Air Cleaner Guide**: Step-by-step engineering instructions for building low-cost MERV-13 box-fan filter units during emergency shortages.

---

## 🧮 Scientific & Risk Scoring Methodology

HazeGuard uses an **Impact-Based Risk Formula** combining Hazard Severity (H), Demographic Vulnerability (V), and Protective Capacity (C):

$$\text{ARI Risk Score (\%)} = \min\left(100, \frac{H \times V}{C} \times \frac{100}{28}\right)$$

```
                             ┌─────────────────────────────────┐
                             │      Hazard Score (H: 0-14)      │
                             │  • PM2.5 Level & Peak Trend       │
                             │  • FIRMS Hotspots & Upwind Path   │
                             │  • CO, AOD, Stagnation, Dryness   │
                             └────────────────┬──────────────────┘
                                              │
 ┌───────────────────────────────┐            │            ┌───────────────────────────────┐
 │ Vulnerability Score (V: 1-6)  │            ▼            │   Capacity Score (C: 0.7-7)   │
 │ • Infants (<5) & Children     │  ┌───────────────────┐  │ • N95 / KN95 Mask Stock        │
 │ • Elderly (65+) & Pregnant    │─►│ DYNAMIC RISK MATRIX│◄─│ • HEPA / Corsi-Rosenthal Fan   │
 │ • Asthma, COPD, Heart Patient │  └───────────────────┘  │ • Sealed Clean-Air Refuge       │
 │ • Outdoor Workers / Labour    │            │            │ • Clinic Access & SOP Alerts    │
 └───────────────────────────────┘            ▼            └───────────────────────────────┘
                          ARI / ISPA Risk Level: LOW / MEDIUM / HIGH
```

### Risk Category Thresholds (WHO 2021 & US EPA Guidelines)

| 24h PM₂.₅ (μg/m³) | AQI Category | ARI / ISPA Health Impact & Action Level |
|---|---|---|
| 0 – 15 | Good | Safe for normal outdoor activities. WHO 24h limit ≤ 15. |
| 15 – 35 | Moderate | Sensitive individuals experience throat/eye irritation. |
| 35 – 55 | Unhealthy (Sensitive) | Children, elderly, and asthma/COPD patients must stay indoors. |
| 55 – 150 | Unhealthy | Sharp rise in ARI/ISPA clinic visits. N95 masks & clean rooms required. |
| 150 – 250 | Very Unhealthy | Health emergency. Suspend outdoor labour & close schools. |
| 250+ | Hazardous | Severe disaster level. Full indoor sheltering or evacuation. |

---

## 🌐 Real-Time API Integrations

HazeGuard operates 100% client-side by consuming open REST APIs directly from the browser:

```
              ┌─────────────────────────────────────────┐
              │               HAZEGUARD EWS              │
              │        (Single Page Web Application)     │
              └────┬──────────┬──────────┬──────────┬────┘
                   │          │          │          │
   ┌───────────────┘          │          │          └───────────────┐
   ▼                          ▼          ▼                          ▼
┌─────────────────────┐  ┌──────────┐ ┌─────────┐  ┌──────────────────────────┐
│   NASA FIRMS API     │  │  Open-   │ │  USGS   │  │     NASA POWER API       │
│ (VIIRS / MODIS Fire) │  │  Meteo   │ │ Quake   │  │   (Peat & Ag-Climate)    │
└─────────────────────┘  └──────────┘ └─────────┘  └──────────────────────────┘
```

**NASA FIRMS (Fire Information for Resource Management System)**
- Endpoint: `https://firms.modaps.eosdis.nasa.gov/api/area/csv/{KEY}/{SENSOR}/{BBOX}/2`
- Purpose: Retrieves thermal hotspots, Fire Radiative Power (FRP), acquisition timestamps, and GPS coordinates.

**Open-Meteo Air Quality API (CAMS European Centre / SILAM)**
- Endpoint: `https://air-quality-api.open-meteo.com/v1/air-quality`
- Purpose: Hourly 72-hour forecasts and current readings for PM₂.₅, PM₁₀, CO, NO₂, SO₂, O₃, AOD, and US/EU AQI.

**Open-Meteo Weather Forecast API**
- Endpoint: `https://api.open-meteo.com/v1/forecast`
- Purpose: 5-day weather, dominant wind direction, wind speed, surface pressure, max/min temperature, and daily rainfall totals.

**USGS Earthquake Hazards Program API**
- Endpoint: `https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson`
- Purpose: Identifies M ≥ 5.5 epicenters, focal depths, and NOAA tsunami flags.

**NASA POWER Agroclimatology API**
- Endpoint: `https://power.larc.nasa.gov/api/temporal/daily/point`
- Purpose: Evaluates 30-day historical precipitation trends (PRECTOTCORR) and max temperatures (T2M_MAX) for peat moisture diagnostics.

**NASA GIBS (Global Imagery Browse Services)**
- WMTS Tile Layer: `OMPS_Aerosol_Index`
- Purpose: Visualizes satellite-detected smoke plumes on the Leaflet map layer.

---

## 📂 Progressive Web App (PWA) & APK Setup

HazeGuard is architected as an **Online First, Offline Second** (Network First with Cache Fallback) PWA.

### PWA File Structure

To deploy as a PWA, ensure the following files exist in the same root directory:

```
├── index.html         # Main Application UI (hazard.html)
├── manifest.json      # Web App Manifest
├── sw.js              # Service Worker (Network-First Strategy)
├── icon-192.png       # App Icon (192x192 px)
└── icon-512.png       # App Icon (512x512 px)
```

### 1. `manifest.json`

```json
{
  "name": "HazeGuard EWS | Wildfire Smoke & ARI Warning",
  "short_name": "HazeGuard",
  "description": "Early Warning System for wildfire smoke, peatland haze and Acute Respiratory Infection (ARI/ISPA) risk.",
  "start_url": "./index.html",
  "display": "standalone",
  "background_color": "#0f172a",
  "theme_color": "#c2410c",
  "orientation": "any",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png",
      "purpose": "any maskable"
    },
    {
      "src": "icon-512.png",
      "sizes": "512x512",
      "type": "image/png",
      "purpose": "any maskable"
    }
  ]
}
```

### 2. Service Worker (`sw.js`)

The Service Worker implements a Network-First Strategy:

```javascript
const CACHE_NAME = 'hazeguard-v1';
const ASSETS_TO_CACHE = [
  './',
  './index.html',
  './manifest.json',
  './icon-192.png',
  './icon-512.png',
  'https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap',
  'https://cdn.tailwindcss.com',
  'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css',
  'https://unpkg.com/leaflet@1.9.4/dist/leaflet.css',
  'https://unpkg.com/leaflet@1.9.4/dist/leaflet.js',
  'https://cdn.jsdelivr.net/npm/chart.js',
  'https://cdnjs.cloudflare.com/ajax/libs/localforage/1.10.0/localforage.min.js'
];

self.addEventListener('install', (e) => {
  e.waitUntil(
    caches.open(CACHE_NAME).then((cache) => cache.addAll(ASSETS_TO_CACHE))
  );
});

self.addEventListener('fetch', (e) => {
  if (e.request.method !== 'GET') return;
  e.respondWith(
    fetch(e.request)
      .then((netRes) => {
        if (netRes && netRes.status === 200) {
          const clone = netRes.clone();
          caches.open(CACHE_NAME).then((c) => c.put(e.request, clone));
        }
        return netRes;
      })
      .catch(() => caches.match(e.request).then((cRes) => cRes || caches.match('./index.html')))
  );
});
```

### 3. Converting to Android APK via PWABuilder.com

1. Host your project on any HTTPS provider (GitHub Pages, Vercel, Netlify).
2. Visit [pwabuilder.com](https://pwabuilder.com) and paste your application URL.
3. Verify that Manifest, Service Worker, and HTTPS indicators pass validation.
4. Click **Package for Store → Android** to generate the `.apk` or `.aab` package for distribution.

---

## 🏗️ Technical Architecture & Stack

| Component | Library / Technology | Function |
|---|---|---|
| UI Framework | HTML5 + Tailwind CSS (CDN) | Responsive, mobile-first utility layout |
| Typography & Icons | Plus Jakarta Sans + FontAwesome 6 | Clean design language and visual indicators |
| Interactive Map | Leaflet.js v1.9.4 | Geospatial visualization, custom vector cones & markers |
| Basemaps | Esri World Street / Satellite + NASA GIBS | Topographic, imagery, and satellite smoke overlays |
| Data Analytics & Charts | Chart.js | 72h hourly PM₂.₅ trend charts & 5-day climate forecasts |
| Data Persistence | LocalForage (IndexedDB fallback) | 100% offline-ready local storage |
| Translation | Google Translate Element API | Dynamic multilingual UI support (EN, ID, MS, ZH, TH) |
| Print & PDF Engine | CSS `@media print` | Auto-formatted PDF report generation directly from browser |

---

## 🚀 Quick Start & Installation

### Local Development

No Node.js, build pipeline, or backend server setup is required.

1. **Clone or Download the Repository:**

```bash
git clone https://github.com/your-username/hazeguard-ews.git
cd hazeguard-ews
```

2. **Serve using any Static Web Server:**

```bash
# Using Python 3
python3 -m http.server 8000

# Or using Node.js http-server
npx http-server -p 8000
```

3. **Open in Browser:**

Navigate to `http://localhost:8000`.

4. **Add NASA FIRMS Key (Free):**

Click **Settings** (gear icon) or follow the onboard prompt. Obtain a free `MAP_KEY` from the [NASA FIRMS API](https://firms.modaps.eosdis.nasa.gov/api/), then paste the key into the app settings to enable hotspot scanning.

---

## 📱 Dashboard & UI Modules

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  NAVBAR: HazeGuard EWS | Lang Switcher | Settings | Print PDF Report        │
├──────────────────────────────┬──────────────────────────────────────────────┤
│  LEFT PANEL: MAP              │  RIGHT PANEL: DASHBOARD ANALYTICS           │
│                                │                                             │
│  • Esri Street / Satellite    │  • ARI/ISPA Risk Gauge Score (%)           │
│  • Fire Hotspot Pulse Markers │  • Overview KPIs: PM2.5, Fire, Vis, Wind   │
│  • Dynamic Wind Plume Cones   │  • 72-Hour PM2.5 & AQI Line Chart          │
│  • Regional Wind Field SVG    │  • Exposure Dose & Cigarette Equivalents   │
│  • NASA Smoke Layer           │  • Multi-Tab Views:                        │
│  • USGS Quake Epicenters      │    [Air & Health] [Risk Matrix] [Forecast] │
│                                │    [Actions] [History]                     │
└──────────────────────────────┴──────────────────────────────────────────────┘
```

- **Overview Tab**: Gauge score displaying the calculated ARI Risk (%), quick status cards, hourly 72h PM₂.₅ forecast graph, and Berkeley Earth exposure dose estimation.
- **Air & Health Tab**: Itemized indicators for PM₂.₅, PM₁₀, CO, NO₂, SO₂, AOD, smoke transport vectors, child outdoor safe exposure limit, and demographic breakdown.
- **Risk Matrix Tab**: Destana-aligned breakdown of Hazard, Vulnerability, and Capacity scoring metrics alongside WHO 2021 air quality thresholds.
- **Forecast Tab**: 5-day weather & fire-weather forecast cards, rain vs. temperature vs. wind trend charts, and NASA POWER peat dryness context.
- **Actions Tab**: Priority-ranked health protection actions tailored to current hazard levels, mask guidelines, clean-room construction, vulnerability alerts, and volcanic ash/tsunami emergency red flags.
- **History Tab**: Automatically logs every day with MEDIUM or HIGH smoke risk (stores up to 5 years locally).

---

## 🔒 Privacy & Zero-Server Data Guarantee

- **Zero Tracking**: No user data, site coordinates, or API keys are ever transmitted to an external application backend.
- **100% Local Storage**: All registered monitoring sites, custom protective capacity profiles, historical logs, and NASA API keys are stored strictly inside your browser's IndexedDB via LocalForage.
- **Direct API Connections**: Network requests are performed directly from your browser client to public open-data endpoints (NASA, Open-Meteo, USGS).

---

## 👤 Author & Acknowledgments

**Author:** Angga Conni Saputra
**License:** MIT License

**Data Sources & Special Thanks:**
- NASA FIRMS (Fire Information for Resource Management System)
- NASA Earthdata GIBS (Global Imagery Browse Services)
- NASA POWER (Prediction Of Worldwide Energy Resources)
- Open-Meteo Air Quality & Weather API (CAMS / ECMWF reanalysis)
- USGS Earthquake Hazards Program
- World Health Organization (WHO 2021 Air Quality Guidelines)
