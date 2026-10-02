<p align="center"><img src="assets/header.svg" alt="Bardia Malackzadeh — Computing Science, Vancouver BC" width="100%"></p>

<p align="center">
  <a href="https://tcicsbooking.com">Live project</a> ·
  <a href="https://github.com/Bardmalek/TCICS">Flagship case study</a> ·
  <a href="https://github.com/Bardmalek/carwatch">Computer-vision project</a> ·
  <a href="https://github.com/Bardmalek?tab=repositories">All repositories</a>
</p>

I study Computing Science at **Simon Fraser University** and build software around real workflows: event booking, operational dashboards, connected hardware, and computer-vision and decision-support prototypes. I’m especially interested in backend systems, machine-learning systems, and quantitative finance.

### Selected work

| Project | What it shows |
| :--- | :--- |
| **[Tiregan 2026 / TCICS](https://github.com/Bardmalek/TCICS)** | A **deployed** vendor booking platform: interactive floor plan, server-verified PayPal payments, TypeScript Edge Functions on PostgreSQL, and organizer operations. [Visit the site ↗](https://tcicsbooking.com) |
| **[CarWatch](https://github.com/Bardmalek/carwatch)** | Real-time vehicle tracking and driving-pattern analysis: YOLO26 + BoT-SORT, camera-motion stabilization, speed and acceleration with error bars, a behaviour model evaluated on real tracks, and a live local dashboard. 39 tests, CI, and published results, including the ones that didn’t work. |
| **[VenueMap](https://github.com/Bardmalek/venuemap)** | Event and booth discovery interfaces, map editing, and vendor and organizer workspaces. [Live preview ↗](https://venuemap-gamma.vercel.app) |
| **[X-Plane Emergency Assistant](https://github.com/Bardmalek/xplane-emergency-assistant)** | Typed telemetry, a rule-based emergency decision engine behind a swappable interface, and a simulator that runs without X-Plane. 18 unit tests, CI on Python 3.10 and 3.12. |
| **[Sensory Substitution Kit](https://github.com/Bardmalek/sensory-substitution-kit)** | An ESP32 sound-to-touch firmware prototype (FFT, four frequency bands, vibration motors) with a React Native companion app. |

### Featured: CarWatch

<table>
<tr>
<td width="55%" valign="top">

Most “AI traffic” demos stop at drawing boxes. CarWatch tries to be **measurable and honest**:

- **Error bars on every number.** A quadratic fit gives speed and acceleration, and its covariance gives a 1σ error.
- **Tested on real tracks.** Hand-set thresholds false-alarmed on 54% of normal real windows; a model trained on real tracks with injected events cut that to about 12%. The README says exactly what that does and doesn’t prove.
- **Negative results kept.** Sliced inference raised recall but hurt F1 and ran about 15× slower, so it isn’t wired in.
- **Private by default.** No face or plate recognition, and everything stays on `127.0.0.1`.

[Read the write-up →](https://github.com/Bardmalek/carwatch)

</td>
<td width="45%">

<img src="https://raw.githubusercontent.com/Bardmalek/carwatch/main/docs/dashboard.png" alt="CarWatch live dashboard (synthetic demo data)">

<sub>Dashboard shown with synthetic data.</sub>

</td>
</tr>
</table>

### Things I work with

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white" alt="Supabase">
  <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="React">
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white" alt="OpenCV">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn">
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git">
</p>

<p align="center"><sub>Built in Vancouver · Always iterating</sub></p>
