<p align="center"><img src="assets/header.svg" alt="Bardia Malackzadeh — Computing Science, Vancouver BC. Backend, ML systems, computer vision." width="100%"></p>

<p align="center">
  <a href="https://bardmalek.github.io"><img src="assets/btn-portfolio.svg" alt="Open the interactive portfolio" height="40"></a>
  <a href="https://tcicsbooking.com"><img src="assets/btn-tiregan.svg" alt="Live: Tiregan platform" height="40"></a>
  <a href="https://github.com/Bardmalek/carwatch"><img src="assets/btn-carwatch.svg" alt="CarWatch write-up" height="40"></a>
  <a href="https://github.com/Bardmalek?tab=repositories"><img src="assets/btn-repos.svg" alt="All repositories" height="40"></a>
</p>

I study Computing Science at **Simon Fraser University** and build software around real workflows: event booking, operational dashboards, connected hardware, and computer-vision and decision-support prototypes. I’m especially interested in backend systems, machine-learning systems, and quantitative finance.

<p align="center"><img src="assets/stats.svg" alt="39 automated tests in CI. HOTA 0.543. Harsh-braking false alarms from 54 percent to 12 percent on real tracks. 89 booth spaces on a deployed platform." width="100%"></p>

## Selected work

<table>
<tr>
<td width="50%" valign="top">
<a href="https://github.com/Bardmalek/TCICS"><img src="assets/card-tcics.svg" alt="Tiregan 2026 booking platform" width="100%"></a>
<sub><a href="https://tcicsbooking.com">Live site</a> · <a href="https://github.com/Bardmalek/TCICS">Case study</a></sub>
</td>
<td width="50%" valign="top">
<a href="https://github.com/Bardmalek/carwatch"><img src="assets/card-carwatch.svg" alt="CarWatch vehicle tracking" width="100%"></a>
<sub><a href="https://github.com/Bardmalek/carwatch">Repository</a> · <a href="https://github.com/Bardmalek/carwatch/actions">CI</a></sub>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="https://github.com/Bardmalek/venuemap"><img src="assets/card-venuemap.svg" alt="VenueMap" width="100%"></a>
<sub><a href="https://venuemap-gamma.vercel.app">Live preview</a> · <a href="https://github.com/Bardmalek/venuemap">Repository</a></sub>
</td>
<td width="50%" valign="top">
<a href="https://github.com/Bardmalek/xplane-emergency-assistant"><img src="assets/card-xplane.svg" alt="X-Plane Emergency Assistant" width="100%"></a>
<sub><a href="https://github.com/Bardmalek/xplane-emergency-assistant">Repository</a> · <a href="https://github.com/Bardmalek/xplane-emergency-assistant/actions">CI</a></sub>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="https://github.com/Bardmalek/sensory-substitution-kit"><img src="assets/card-sensory.svg" alt="Sensory Substitution Kit" width="100%"></a>
<sub><a href="https://github.com/Bardmalek/sensory-substitution-kit">Repository</a></sub>
</td>
<td width="50%" valign="middle" align="center">
<sub>More on the <a href="https://bardmalek.github.io">interactive portfolio</a>: project filters, a results explorer, and a booking-flow walkthrough.</sub>
</td>
</tr>
</table>

<p align="center"><img src="assets/divider.svg" alt="" width="100%"></p>

## Under the hood

Open a section to see how things work.

<details>
<summary><b>CarWatch: how the pipeline works</b></summary>

```mermaid
flowchart LR
  A["Camera · video · image folder"] --> B["Detector<br/>YOLO26"]
  B --> C["BoT-SORT tracker"]
  C --> D["ID stitching<br/>+ class vote"]
  A --> E["Stabilizer<br/>optical flow → world frame"]
  D --> F["Vehicle state<br/>world-frame track"]
  E --> F
  F --> G["Kinematics<br/>speed, accel ± error"]
  F --> H["Behaviour model<br/>weaving · harsh accel/brake"]
  G --> I["Over-limit check"]
  H --> J["Flags"]
  I --> J
  J --> K["Evidence packet"]
  G --> L["Speed records<br/>→ regression"]
  L --> M["Local dashboard"]
  J --> M
```

Every number carries an error bar, flags describe driving *patterns* (never impairment), and everything stays on `127.0.0.1`. [Read the write-up →](https://github.com/Bardmalek/carwatch)

</details>

<details>
<summary><b>CarWatch: results at a glance (with caveats)</b></summary>

| Tracker (VisDrone val, vehicles) | HOTA | IDF1 | ID switches |
| :--- | ---: | ---: | ---: |
| ByteTrack | 0.482 | 0.557 | 329 |
| **BoT-SORT** | **0.543** | **0.643** | **104** |
| BoT-SORT + ReID | 0.540 | 0.643 | 144 |

| Behaviour flags on real tracks | Harsh false alarms | Weave false alarms |
| :--- | ---: | ---: |
| Hand-set rules | 54% | 11% |
| Learned, synthetic only | 35% | 10% |
| Learned, real tracks + synthetic | **12%** | **5%** |

> Not real-world accuracy. Real tracks stand in for normal traffic and events are *injected* with known labels, tested leave-one-sequence-out. No labelled real driving events exist yet. Sliced inference is documented as a negative result: higher recall, lower F1, about 15× slower.

</details>

<details>
<summary><b>Tiregan: how a booking flows</b></summary>

```mermaid
flowchart LR
  A["Vendor picks a booth<br/>on the floor plan"] --> B["Temporary hold"]
  B --> C["Edge Function<br/>creates PayPal order"]
  C --> D["PayPal approval"]
  D --> E["Return page:<br/>capture + verify"]
  D --> F["Signature-verified<br/>webhook"]
  E --> G[("PostgreSQL<br/>audit trail")]
  F --> G
  G --> H["Mailgun receipt"]
  G --> I["Realtime availability<br/>refresh"]
```

Seven TypeScript Edge Functions, Row Level Security so anonymous users can only read booth availability, and database audit triggers that keep before/after records of booking changes. [Case study →](https://github.com/Bardmalek/TCICS)

</details>

## Things I work with

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
