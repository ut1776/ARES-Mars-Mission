<div align="center">

# 🔴 ARES — THE FIRST MARSWALK, PLANNED

### Adaptive Reconnaissance & Expedition System

**A data-driven mission-planning experience for a future human EVA at Jezero Crater.**

<p>
  <img src="https://commons.wikimedia.org/wiki/Special:Redirect/file/Spinning_Mars.gif" alt="Animated rotating planet Mars" width="190">
</p>

[![LAUNCH LIVE MISSION](https://img.shields.io/badge/LAUNCH-Live%20Mission%20Experience-e85d2a?style=for-the-badge)](https://ares-mars-mission-d4yz.onrender.com)
[![SCIENTIFIC NOTEBOOK](https://img.shields.io/badge/EXPLORE-Scientific%20Notebook-20232a?style=for-the-badge&logo=jupyter)](notebook/ARES_Martian_Mission_Planner_FINAL.ipynb)
[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

*NASA Space Apps Challenge 2026 · Marswalk · Jezero Crater*

<sub>Rotating Mars animation: “Spinning Mars” by JOGOS Public Assets, CC BY-SA 4.0. <a href="https://commons.wikimedia.org/wiki/File:Spinning_Mars.gif">Source and license</a>.</sub>

</div>

---

<p align="center">
  <a href="https://ares-mars-mission-d4yz.onrender.com"><img src="data/ares_mission_dashboard.png" alt="ARES mission dashboard" width="94%"></a>
</p>

> **The challenge:** A crew walking on Mars cannot rely on GPS or a global map. They need a local plan that connects terrain, hazards, science targets, time, and the journey home.

## 🚀 Judge walkthrough — follow this mission sequence

**Recommended time: 5–7 minutes.** Start with the live experience, then use the notebook to verify how the planning outputs were produced.

<p align="center">
  <a href="https://ares-mars-mission-d4yz.onrender.com"><img src="data/ares_mission_dashboard.png" alt="ARES mission dashboard — open the live mission experience" width="94%"></a>
</p>

### Step 1 — Launch the mission (30 seconds)

Open **[ARES Live Mission Experience](https://ares-mars-mission-d4yz.onrender.com)**. Begin with the mission brief and identify the central problem: a Mars crew needs a local route that connects terrain safety, science objectives, EVA time and a viable return to its habitat.

### Step 2 — Understand the planetary data (60 seconds)

Find the NASA data / mission context section. Notice how ARES combines:
- **HiRISE** imagery and terrain elevation for local-scale surface context.
- **CRISM** spectral summary parameters to flag areas of scientific interest.
- **MOLA** elevation for regional topographic context.
- **Perseverance** imagery and traverse waypoints as nearby rover-ground-truth context.

The point is data fusion: no single layer answers every mission-planning question.

### Step 3 — Explore the 3D terrain (60–90 seconds)

Open the **3D Terrain Lab**. Drag to rotate the terrain view, use the zoom control or wheel/pinch gesture to move closer, and use **Reset View** to return to the starting camera. Toggle the route and terrain overlays where available.

Treat this as an explanatory terrain preview. It helps orient the judge to the landscape; it is not the source of the quantitative slope or hazard calculations.

### Step 4 — Follow the EVA route (60–90 seconds)

Open the **EVA Mission Replay** and follow the planned loop from the habitat through the selected science stops and back. Watch the route metrics as the replay progresses: distance, elapsed time, slope, elevation and walk-back context. Where available, toggle the no-go terrain and Perseverance traverse overlays to compare the planned route with the surrounding evidence.

### Step 5 — Inspect the science and hazard reasoning (60 seconds)

Review the three selected spectral science stops and the hazard-screening view. Ask:
- What terrain and spectral evidence contributed to the stop selection?
- How does slope screening influence the route?
- How does the plan account for the distance and time needed to return?

CRISM summary parameters are indicators for investigation; they do not independently establish mineral identity.

### Step 6 — Check the mission numbers (30 seconds)

Compare the live experience with the mission snapshot below. The current project plan is **9.24 km**, an estimated **4.17-hour EVA**, a maximum route slope of **8.2°**, and a maximum walk-back distance of **4.62 km**, against an **assumed 8.0-hour planning limit**.

### Step 7 — Verify the analysis (60 seconds)

Open the **[final scientific notebook](notebook/ARES_Martian_Mission_Planner_FINAL.ipynb)**. Inspect the data preparation, terrain/hazard analysis, route planning and outputs. The [mission JSON](data/mission.json) is the structured dataset used by the web experience.

**What to take away:** ARES connects orbital science data to a human-scale EVA planning workflow, makes its assumptions visible, and gives the judge a route they can explore rather than only a static map.

## 🧭 Project summary

ARES (Adaptive Reconnaissance & Expedition System) turns NASA orbital data into a hyperlocal planning tool for a human Marswalk at Jezero Crater. It layers HiRISE 1 m terrain and imagery, CRISM spectral summary parameters and MOLA elevation, screens terrain by slope and hazard, selects 3 spectral science stop(s), and plans a least-cost walking loop from a habitat site: 9.24 km with an estimated 4.17 h EVA, inside the assumed 8.0 h limit, a maximum slope of 8.2 degrees and a maximum walk-back distance of 4.62 km. Every output is labelled measured, derived or assumed, and the route is a planning prototype rather than a certified safe traverse. The hazard model is checked against 261 NASA Perseverance waypoints (0.8% fall in ARES no-go terrain), and nearest rover images show the crew what to expect.

## 📊 Mission snapshot

| Planning output | Current project result |
|---|---:|
| Planned route | **9.24 km** |
| Estimated EVA duration | **4.17 h** |
| Assumed EVA time limit | **8.0 h** |
| Maximum slope along route | **8.2°** |
| Maximum walk-back distance | **4.62 km** |
| Perseverance waypoints used for comparison | **261** |
| Waypoints falling in ARES no-go terrain | **0.8%** |
| Spectral science stops | **3** |

These are supplied project results, not independently certified operational limits. See the notebook and mission data for calculations and assumptions.

## 🛰️ NASA data field

- **MRO HiRISE** — Jezero digital terrain model and orthoimage products ESP_045994_1985 / ESP_046060_1985.
- **MRO CRISM** — MTRDR HRL000040FF summary parameters and IN mask, accessed via the PDS Mars Orbital Data Explorer.
- **MGS MOLA** — MEGDR regional topography for elevation context.
- **Mars 2020 Perseverance** — raw image feed and rover traverse waypoints from mars.nasa.gov and MMGIS.
- **Mars 2020 MEDA** — weather feed, where retrieved and available in the analysis build.

| Source | Mission-planning role |
|---|---|
| HiRISE imagery | Fine-scale visual context |
| HiRISE DTM | Local elevation and derived slope |
| CRISM summary parameters | Spectral indicators used to prioritize science stops |
| MOLA MEGDR | Regional topographic context |
| Perseverance imagery and waypoints | Nearby visual context and rover-path comparison |
| MEDA | Environmental context when retrieved |

CRISM indices identify spectral targets for investigation; they do not, by themselves, prove mineral identity.

## 🗺️ Mission visuals

<p align="center"><img src="data/ares_route_map.png" alt="ARES planned route map" width="88%"><br><em>Planned EVA route and mission geography.</em></p>

<p align="center"><img src="data/ares_rover_vs_ares.png" alt="ARES hazard model comparison with Perseverance rover observations" width="88%"><br><em>ARES hazard screening compared with Perseverance rover traverse observations.</em></p>

The repository also includes the underlying basemap, no-go mask, mission JSON and three nearby Perseverance point-of-view images in the data/ directory.

## 🔬 Reproducibility

- [Open the final mission-planning notebook](notebook/ARES_Martian_Mission_Planner_FINAL.ipynb)
- [Inspect the mission dataset](data/mission.json)
- [Inspect the route map](data/ares_route_map.png)
- [Inspect the dashboard](data/ares_mission_dashboard.png)

The notebook documents the analysis workflow and produces the mission products consumed by the website. The interactive site reads the mission JSON and local image assets to present the route and its context.

## ⚖️ Scientific integrity & limitations

- **Measured:** source imagery, elevation products, spectral parameters and rover observations.
- **Derived:** slope, hazard screening, selected science stops, least-cost route and EVA estimates.
- **Assumed:** operational thresholds, walking speed, stop duration and planning constraints.

ARES is a **planning prototype, not a certified safe traverse**. The route depends on stated assumptions and available data. Rock-scale hazards below the terrain-model resolution, suit effects, thermal loads and live space weather are not fully modelled. The Perseverance comparison is a useful external check on the hazard map, but a rover is not a suited astronaut and its path does not certify human safety. MEDA weather context is included only where successfully retrieved.

## 🖼️ Project-page image checklist

| Image | Supplied size | Repository status |
|---|---:|---|
| ares_mission_dashboard.png | 0.78 MB | Present |
| ares_rover_vs_ares.png | 1.31 MB | Present |
| ares_perseverance_pov.png | 1.70 MB | Not in current repository tree |
| ARES_integrated_surface_atlas.png | 2.66 MB | Not in current repository tree |
| ares_route_map.png | 1.42 MB | Present |
| ares_route_profile.png | 0.12 MB | Not in current repository tree |

All supplied sizes are below the stated 10 MB project-page limit. The repository also contains pov_1.jpg, pov_2.jpg and pov_3.jpg as individual rover-view assets. Add the three missing PNGs before linking them from the project page.

## 🎬 Video

[Watch the ARES project video on YouTube](https://m.youtube.com/watch?v=CZ2nQl5CsOQ&pp=iggUQAFKEEhLdWJubjhseUVPZnNrQUk%3D&ra=m)

## 👩‍🚀 Team

Umar Tabbsum · Aiden Janes · Luke Korth · Viralbhai Patel

---

NASA data acknowledgements: MRO HiRISE, MRO CRISM, MGS MOLA, Mars 2020 Perseverance and MEDA instrument/data teams, NASA/JPL-Caltech and the Planetary Data System.

No NASA logos or mission identifiers are used. This project is not endorsed by NASA.

**Code license:** MIT. See [LICENSE](LICENSE).