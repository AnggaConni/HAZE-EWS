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
