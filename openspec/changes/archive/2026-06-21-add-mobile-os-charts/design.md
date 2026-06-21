## Context

The Mobile Devices section currently displays the Device Type distribution, Notebook vs. Handheld averages, and performance rankings (Top CPUs, GPUs, and handhelds). While we have general OS demographics for the entire system, we lack focused OS distribution statistics for portable form factors. Handheld gaming PCs running Linux (e.g. Steam Deck, ROG Ally) present unique operating system trends that differ significantly from typical laptops.

## Goals / Non-Goals

**Goals:**
- Add a new "Mobile OS Distribution" and "Handheld OS Distribution" doughnut chart to the Mobile Devices section.
- Create a new `mobile-distribution-grid` layout in `index.html` and `style.css` to host these two charts cleanly.
- Implement data aggregation logic in `app.js` to extract OS metrics for mobile and handheld devices.

**Non-Goals:**
- Modifying the existing system-wide OS distribution chart.

## Decisions

### 1. Chart Layout and Placement
We will place the two new charts in a new 2-column grid container called `.mobile-distribution-grid` located between the overview stats and performance stats.
- Left column: Mobile OS Distribution (Doughnut).
- Right column: Handheld OS Distribution (Doughnut).
This layout is visually balanced and mirrors the 2-column grids (like `memory-charts-grid`) used elsewhere on the dashboard.

### 2. Reuse OS Distribution Logic
We will reuse the clean OS parsing logic from `getOSDistribution(data)` to group operating systems into clean categories (e.g., SteamOS, Bazzite, Fedora, Ubuntu, Arch, CachyOS, etc.) rather than displaying raw kernel or distribution details. We will write two helper functions:
- `getMobileOSDistribution(data)`: filters data to mobile devices before calling distribution logic.
- `getHandheldOSDistribution(data)`: filters data to handhelds before calling distribution logic.

## Risks / Trade-offs

- **Risk**: Adding more doughnut charts might clutter the layout.
  - *Mitigation*: Restrict their height using the existing `.donut-chart-canvas` class (240px) to keep them compact and neat.
