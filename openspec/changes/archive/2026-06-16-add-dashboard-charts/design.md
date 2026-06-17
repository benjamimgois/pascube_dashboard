## Context

The Pascube Benchmark Dashboard currently uses Chart.js to render three horizontal bar charts showing top scores. We need to design and add 6 new charts (Top 10 CPU/GPU usage, and distributions for OS, CPU brands, GPU brands, and video drivers) using existing benchmark data.

## Goals / Non-Goals

**Goals:**
- Implement 2 new horizontal bar charts for "Top 10 CPU - Most used" and "Top 10 GPU - Most used".
- Implement 4 new doughnut/pie charts for "Operating Systems", "CPU Brands", "GPU Brands", and "Video Drivers".
- Design a responsive layout that organizes these charts visually into logical groups (e.g., Performance vs Demographics).
- Ensure high performance when aggregating and rendering the data.

**Non-Goals:**
- Changing database structure or changing Google Sheets columns/endpoints.
- Implementing users or authentication on the frontend.

## Decisions

### 1. Chart Layout Organization
- **Choice**: Group charts into two main grid sections in the UI.
  - *Performance Leaderboards*: Keeps the existing 3 top-score charts.
  - *Usage & Distributions*: Adds a new section containing the two Top 10 usage bar charts (using a 2-column layout) and a 4-column/responsive grid containing the 4 doughnut charts.
- **Rationale**: Keeps the page clean, avoids visual clutter, and groups similar metrics together.

### 2. Data Processing & Brand Extraction
- **Choice**: Extract CPU/GPU brands and video drivers using case-insensitive RegExp checks on the existing strings:
  - *CPU Brands*: `AMD` (Ryzen, AMD), `Intel` (Intel, Core, Xeon, i3/i5/i7/i9), `Other` (APU, Custom, Apple, etc.)
  - *GPU Brands*: `NVIDIA` (NVIDIA, RTX, GTX, GeForce), `AMD` (AMD, Radeon, RX), `Intel` (Intel, Arc), `Other`.
  - *Video Drivers*: `Mesa` (contains "Mesa"), `NVIDIA` (contains "NVIDIA" or "NVRM"), `Other`.
- **Rationale**: Simple client-side classification is sufficient since the data set is small and the labels are highly standard.

### 3. Chart type for distribution
- **Choice**: Use Chart.js `doughnut` charts for OS, CPU Brand, GPU Brand, and Video Driver distributions, with a clean aesthetic and centered hollow space to make the design feel premium.
- **Rationale**: Doughnut charts are more modern and visually appealing than standard pie charts, fitting the dark glassmorphic theme.

## Risks / Trade-offs

### [Risk] Brand extraction mismatch → Mitigation
- *Risk*: A CPU/GPU name doesn't match the regex and gets misclassified as "Other".
- *Mitigation*: Build robust regexes that cover all common variations, and keep the rules flexible.
