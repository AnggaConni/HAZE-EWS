readme_content_en = """# 🌋🔥 HazeGuard EWS | Wildfire Smoke, Volcanic Ash, Industrial Pollution & Tsunami Early Warning System

[![PWA Ready](https://img.shields.io/badge/PWA-Online%20First-c2410c?style=for-the-badge&logo=pwa)](https://pwabuilder.com)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Architecture](https://img.shields.io/badge/Architecture-Serverless%20%2F%20Client--Side-0ea5e9?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![Data Protection](https://img.shields.io/badge/Privacy-100%25%20Local%20(IndexedDB)-10b981?style=for-the-badge)](#data-privacy--security)

**HazeGuard EWS** is a zero-cost, serverless Progressive Web Application (PWA) designed as an integrated **Impact-Based Early Warning System (IBEWS)** for atmospheric hazards and disaster risks—specifically peatland/wildfire haze (*karhutla*), volcanic ashfall, urban/industrial air pollution, and coastal earthquake/tsunami threats.

By fusing real-time satellite telemetry (NASA FIRMS, NASA GIBS, NASA POWER), global atmospheric reanalysis (CAMS / Open-Meteo Air Quality), live seismic networks (USGS Earthquake API), and localized socio-demographic diagnostic models, HazeGuard transforms complex geophysical data into actionable, community-level health protection strategies.

---

## 📋 Table of Contents
- [✨ Key Features & Capabilities](#-key-features--capabilities)
- [🧮 Scientific & Risk Scoring Methodology](#-scientific--risk-scoring-methodology)
- [🌐 Real-Time API Integrations](#-real-time-api-integrations)
- [📂 Progressive Web App (PWA) & APK Setup](#-progressive-web-app-pwa--apk-setup)
- [🏗️ Technical Architecture & Stack](#%EF%B8%8F-technical-architecture--stack)
- [🚀 Quick Start & Installation](#-quick-start--installation)
- [📱 Dashboard & UI Modules](#-dashboard--ui-modules)
- [🔒 Privacy & Zero-Server Data Guarantee](#-privacy--zero-server-data-guarantee)
- [👤 Author & Acknowledgments](#-author--acknowledgments)

---

## ✨ Key Features & Capabilities

### 1. 🔥 Wildfire & Peatland Haze Monitoring (*Karhutla*)
* **NASA FIRMS Hotspot Detection**: Real-time satellite thermal anomaly scanning using VIIRS (S-NPP, NOAA-20, NOAA-21 at 375m) and MODIS (1km) sensors.
* **Fire Radiative Power (FRP)**: Calculates megawatts (MW) of fire intensity and proximity/distance (km) relative to target monitoring sites.
* **Smoke Transport & Wind Plume Simulation**: Direct vector analysis of wind direction and speed, rendering visual plume threat cones (*wedge polygons*) and grid-based directional wind fields on an interactive Leaflet map.
* **NASA OMPS Aerosol Index**: Visualizes satellite-detected smoke column density directly on spatial basemaps.

### 2. 🌋 Volcanic Ashfall & Urban/Industrial Air Quality
* **Multi-Hazard Support**: Dynamic threshold monitoring for Wildfires, Volcanic Ash, Industrial/Vehicle Emissions, and Coastal Tsunami threats.
* **Full Gas & Particulate Suite**: Real-time tracking of $\\text{PM}_{2.5}$, $\\text{PM}_{10}$, Carbon Monoxide ($\\text{CO}$), Nitrogen Dioxide ($\\text{NO}_2$), Sulphur Dioxide ($\\text{SO}_2$), Ozone ($\\text{O}_3$), Dust, Aerosol Optical Depth (AOD), and US/European AQI.
* **Volcanic Ash Safeguards**: Asset protection guidelines (roof load clearing, moisture control, eye protection, water source sealing, PVMBG alert level verification).

### 3. 🌊 Real-time Seismic & Tsunami Early Warning
* **USGS Global Seismic Telemetry**: Monitors $M \\ge 5.5$ earthquakes in real time.
* **Proximity Radius Calculation**: Automatically computes Haversine distance between epicenter and registered monitoring sites.
* **Automated Web Push Notifications**: Triggers native browser push notifications and critical alert banners if a $M \\ge 5.5$ earthquake occurs within 300 km or triggers a NOAA/USGS Tsunami flag.

### 4. 🏥 Health Exposure & Diagnostic Tools
* **Cigarette Equivalence Calculator**: Translates 24-hour $\\text{PM}_{2.5}$ exposure into equivalent cigarette consumption using the Berkeley Earth model ($\\text{Cigarettes} \\approx \\text{PM}_{2.5} / 22$).
* **ARI / ISPA Clinical Surge Estimator**: Projects community-level Acute Respiratory Infection (*Infeksi Saluran Pernapasan Akut*) medical visit spikes based on exposed population figures and particulate dosage.
* **30-Day Peat Dryness Index**: Queries NASA POWER climate data to track consecutive dry days ($<1\\text{mm}$ rain) and cumulative precipitation, identifying high-risk subterranean peat ignition windows.
* **DIY Corsi-Rosenthal Air Cleaner Guide**: Step-by-step engineering instructions for building low-cost MERV-13 box-fan filter units during emergency shortages.

---

## 🧮 Scientific & Risk Scoring Methodology

HazeGuard uses an **Impact-Based Risk Formula** combining Hazard Severity ($H$), Demographic Vulnerability ($V$), and Protective Capacity ($C$):

$$\\text{ARI Risk Score (\\%)} = \\min\\left(100, \\frac{H \\times V}{C} \\times \\frac{100}{28}\\right)$$

                                 ┌─────────────────────────────────┐
                                 │      Hazard Score (H: 0-14)     │
                                 │  • PM2.5 Level & Peak Trend     │
                                 │  • FIRMS Hotspots & Upwind Path │
                                 │  • CO, AOD, Stagnation, Dryness │
                                 └────────────────┬────────────────┘
                                                  │
 ┌───────────────────────────────┐                │                ┌───────────────────────────────┐
 │ Vulnerability Score (V: 1-6)  │                ▼                │   Capacity Score (C: 0.7-7)   │
 │ • Infants (<5) & Children     │    ┌───────────────────────┐    │ • N95 / KN95 Mask Stock       │
 │ • Elderly (65+) & Pregnant    │───►│  DYNAMIC RISK MATRIX  │◄───│ • HEPA / Corsi-Rosenthal Fan  │
 │ • Asthma, COPD, Heart Patient │    └───────────────────────┘    │ • Sealed Clean-Air Refuge     │
 │ • Outdoor Workers / Labour    │                │                │ • Clinic Access & SOP Alerts  │
 └───────────────────────────────┘                ▼                └───────────────────────────────┘
                                   ARI / ISPA Risk Level: LOW / MED / HIGH
Risk Category Thresholds (WHO 2021 & US EPA Guidelines)24h PM2.5​ (μg/m3)AQI CategoryARI / ISPA Health Impact & Action Level0 – 15GoodSafe for normal outdoor activities. WHO 24h limit $\le 15$.15 – 35ModerateSensitive individuals experience throat/eye irritation.35 – 55Unhealthy (Sensitive)Children, elderly, and asthma/COPD patients must stay indoors.55 – 150UnhealthySharp rise in ARI/ISPA clinic visits. N95 masks & clean rooms required.150 – 250Very UnhealthyHealth emergency. Suspend outdoor labour & close schools.250+HazardousSevere disaster level. Full indoor sheltering or evacuation.🌐 Real-Time API IntegrationsHazeGuard operates 100% client-side by consuming open REST APIs directly from the browser:                  ┌─────────────────────────────────────────┐
                  │               HAZEGUARD EWS             │
                  │        (Single Page Web Application)    │
                  └────┬──────────┬──────────┬──────────┬───┘
                       │          │          │          │
    ┌──────────────────┘          │          │          └──────────────────┐
    ▼                             ▼          ▼                             ▼
┌─────────────────────────┐ ┌──────────┐ ┌─────────┐ ┌──────────────────────────┐
│     NASA FIRMS API      │ │  Open-   │ │  USGS   │ │     NASA POWER API       │
│  (VIIRS / MODIS Fire)   │ │  Meteo   │ │ Quake   │ │   (Peat & Ag-Climate)    │
└─────────────────────────┘ └──────────┘ └─────────┘ └──────────────────────────┘
NASA FIRMS (Fire Information for Resource Management System)Endpoint: [https://firms.modaps.eosdis.nasa.gov/api/area/csv/](https://firms.modaps.eosdis.nasa.gov/api/area/csv/){KEY}/{SENSOR}/{BBOX}/2Purpose: Retrieves thermal hotspots, Fire Radiative Power (FRP), acquisition timestamps, and GPS coordinates.Open-Meteo Air Quality API (CAMS European Centre / SILAM)Endpoint: [https://air-quality-api.open-meteo.com/v1/air-quality](https://air-quality-api.open-meteo.com/v1/air-quality)Purpose: Hourly 72-hour forecasts and current readings for $\text{PM}_{2.5}$, $\text{PM}_{10}$, $\text{CO}$, $\text{NO}_2$, $\text{SO}_2$, $\text{O}_3$, AOD, and US/EU AQI.Open-Meteo Weather Forecast APIEndpoint: [https://api.open-meteo.com/v1/forecast](https://api.open-meteo.com/v1/forecast)Purpose: 5-day weather, dominant wind direction, wind speed, surface pressure, max/min temperature, and daily rainfall totals.USGS Earthquake Hazards Program APIEndpoint: [https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson](https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson)Purpose: Identifies $M \ge 5.5$ epicenters, focal depths, and NOAA tsunami flags.NASA POWER Agroclimatology APIEndpoint: [https://power.larc.nasa.gov/api/temporal/daily/point](https://power.larc.nasa.gov/api/temporal/daily/point)Purpose: Evaluates 30-day historical precipitation trends (PRECTOTCORR) and max temperatures (T2M_MAX) for peat moisture diagnostics.NASA GIBS (Global Imagery Browse Services)WMTS Tile Layer: OMPS_Aerosol_IndexPurpose: Visualizes satellite-detected smoke plumes on the Leaflet map layer.📂 Progressive Web App (PWA) & APK SetupHazeGuard is architected as an Online First, Offline Second (Network First with Cache Fallback) PWA.PWA File StructureTo deploy as a PWA, ensure the following files exist in the same root directory:├── index.html         # Main Application UI (hazard.html)
├── manifest.json      # Web App Manifest
├── sw.js              # Service Worker (Network-First Strategy)
├── icon-192.png       # App Icon (192x192 px)
└── icon-512.png       # App Icon (512x512 px)
1. manifest.jsonJSON{
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
2. Service Worker (sw.js)The Service Worker implements a Network-First Strategy:JavaScriptconst CACHE_NAME = 'hazeguard-v1';
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
3. Converting to Android APK via PWABuilder.comHost your project on any HTTPS provider (GitHub Pages, Vercel, Netlify).Visit pwabuilder.com and paste your application URL.Verify that Manifest, Service Worker, and HTTPS indicators pass validation.Click Package for Store $\rightarrow$ Android to generate the .apk or .aab package for distribution.🏗️ Technical Architecture & StackComponentLibrary / TechnologyFunctionUI FrameworkHTML5 + Tailwind CSS (CDN)Responsive, mobile-first utility layoutTypography & IconsPlus Jakarta Sans + FontAwesome 6Clean design language and visual indicatorsInteractive MapLeaflet.js v1.9.4Geospatial visualization, custom vector cones & markersBasemapsEsri World Street / Satellite + NASA GIBSTopographic, imagery, and satellite smoke overlaysData Analytics & ChartsChart.js72h hourly $\text{PM}_{2.5}$ trend charts & 5-day climate forecastsData PersistenceLocalForage (IndexedDB fallback)100% offline-ready local storageTranslationGoogle Translate Element APIDynamic multilingual UI support (EN, ID, MS, ZH, TH)Print & PDF EngineCSS @media printAuto-formatted PDF report generation directly from browser🚀 Quick Start & InstallationLocal DevelopmentNo Node.js, build pipeline, or backend server setup is required.Clone or Download the Repository:Bashgit clone https://github.com/your-username/hazeguard-ews.git
cd hazeguard-ews
Serve using any Static Web Server:Bash# Using Python 3
python3 -m http.server 8000

# Or using Node.js http-server
npx http-server -p 8000
Open in Browser:Navigate to http://localhost:8000.Add NASA FIRMS Key (Free):Click Settings (Gear Icon) or follow the onboard prompt.Obtain a free MAP_KEY from NASA FIRMS API.Paste the key into the app settings to enable hotspot scanning.📱 Dashboard & UI Modules ┌─────────────────────────────────────────────────────────────────────────────┐
 │  NAVBAR: HazeGuard EWS | Lang Switcher | Settings | Print PDF Report        │
 ├──────────────────────────────┬──────────────────────────────────────────────┤
 │  LEFT PANEL: MAP             │  RIGHT PANEL: DASHBOARD ANALYTICS            │
 │                              │                                              │
 │  • Esri Street / Satellite   │  • ARI/ISPA Risk Gauge Score (%)             │
 │  • Fire Hotspot Pulse Markers│  • Overview KPIs: PM2.5, Fire, Vis, Wind     │
 │  • Dynamic Wind Plume Cones  │  • 72-Hour PM2.5 & AQI Line Chart            │
 │  • Regional Wind Field SVG   │  • Exposure Dose & Cigarette Equivalents     │
 │  • NASA Smoke Layer         │  • Multi-Tab Views:                          │
 │  • USGS Quake Epicenters     │    [Air & Health] [Risk Matrix] [Forecast]    │
 │                              │    [Actions]      [History]                  │
 └──────────────────────────────┴──────────────────────────────────────────────┘
Overview Tab: Gauge score displaying the calculated ARI Risk (%), quick status cards, hourly 72h $\text{PM}_{2.5}$ forecast graph, and Berkeley Earth exposure dose estimation.Air & Health Tab: Itemized indicators for $\text{PM}_{2.5}$, $\text{PM}_{10}$, $\text{CO}$, $\text{NO}_2$, $\text{SO}_2$, AOD, smoke transport vectors, child outdoor safe exposure limit, and demographic breakdown.Risk Matrix Tab: Destana-aligned Breakdown of Hazard, Vulnerability, and Capacity scoring metrics alongside WHO 2021 air quality thresholds.Forecast Tab: 5-day weather & fire-weather forecast cards, rain vs. temperature vs. wind trend charts, and NASA POWER peat dryness context.Actions Tab: Priority-ranked health protection actions tailored to current hazard levels, mask guidelines, clean-room construction, vulnerability alerts, and volcanic ash/tsunami emergency red flags.History Tab: Automatically logs every day with MEDIUM or HIGH smoke risk (stores up to 5 years locally).🔒 Privacy & Zero-Server Data GuaranteeZero Tracking: No user data, site coordinates, or API keys are ever transmitted to an external application backend.100% Local Storage: All registered monitoring sites, custom protective capacity profiles, historical logs, and NASA API keys are stored strictly inside your browser's IndexedDB via localforage.Direct API Connections: Network requests are performed directly from your browser client to public open-data endpoints (NASA, Open-Meteo, USGS).👤 Author & AcknowledgmentsAuthor: Angga Conni SaputraLicense: MIT LicenseData Sources & Special Thanks:NASA FIRMS (Fire Information for Resource Management System)NASA Earthdata GIBS (Global Imagery Browse Services)NASA POWER (Prediction Of Worldwide Energy Resources)Open-Meteo Air Quality & Weather API (CAMS / ECMWF reanalysis)USGS Earthquake Hazards ProgramWorld Health Organization (WHO 2021 Air Quality Guidelines)
