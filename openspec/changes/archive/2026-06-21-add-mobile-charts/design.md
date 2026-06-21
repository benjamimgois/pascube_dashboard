## Context

The Pascube Benchmark Dashboard currently displays general performance rankings (overall top 10 CPU/GPU) and general demographics (OS, CPU/GPU brand, video driver distribution). There is no section specifically showcasing portable or mobile devices (handhelds and laptops). Since these devices have unique characteristics, power limits, and a growing community presence (especially Linux gaming handhelds like Steam Deck and ROG Ally running Bazzite), a dedicated dashboard section will provide valuable comparison insights.

## Goals / Non-Goals

**Goals:**
- Add a new "Mobile Devices" section in `index.html` styled cohesively with the rest of the application.
- Implement classification logic in `app.js` to label benchmark records as Handheld, Notebook, or Desktop.
- Render five new Chart.js charts in the new section:
  1. **Mobile Distribution** (Doughnut Chart): Handheld vs. Notebook counts.
  2. **Top 10 Mobile CPUs** (Horizontal Bar Chart): Average CPU Multi score.
  3. **Top 10 Mobile GPUs** (Horizontal Bar Chart): Average GPU score.
  4. **Top 10 Handhelds** (Horizontal Bar Chart): Top individual Main Scores.
  5. **Notebook vs. Handheld Averages** (Grouped Bar Chart): Comparing average Main, CPU Single, CPU Multi, and GPU scores.

**Non-Goals:**
- Modifying the benchmark CSV data schema or ingestion method.
- Creating a separate page/route for mobile devices; the charts will be integrated into the existing dashboard page.

## Decisions

### 1. Mobile Hardware Classification Logic
We will define a helper function `classifyDevice(row)` in `app.js` that checks:
- **Handheld**: CPU contains "Steam Deck", "Z1 Extreme", "Z1", "Custom APU 0405", "AMD Custom GPU 0405"; OS contains "Bazzite (ROG Ally", "Steam Deck", "Ally", "Legion Go", "MSI Claw", etc.
- **Notebook**: CPU contains mobile suffixes (e.g., i7-10870H, Ryzen 9 9950HX, Ryzen AI 9 HX 370, or Ryzen AI Max); GPU contains "Laptop", "Mobile", or "Geforce MX".
- **Desktop/Other**: Anything else.

*Alternative Considered*: Relying on a static list of mobile models.
*Reason for Choice*: CPU and GPU naming patterns (e.g., "Laptop", "Mobile", "HX", "HS", "U") are robust and scale better to new submissions.

### 2. Dashboard Layout and Chart styling
We will place the new "Mobile Devices" section below the existing "System Demographics" section.
- The layout will consist of a section header followed by a grid of charts:
  - Top Row: Mobile Distribution (Doughnut) + Notebook vs Handheld Averages (Grouped Vertical Bar).
  - Middle/Bottom Row: Top 10 Mobile CPUs + Top 10 Mobile GPUs + Top 10 Handhelds (Horizontal Bar).
- Colors will match the dashboard's design system using vibrant semi-transparent fills and solid borders (e.g., Purple/Indigo for Handhelds, Amber/Sky for Notebooks).

### 3. Notebook vs. Handheld Comparison Data
For the comparison chart, we will average the scores for the two groups across four metrics:
- Main Score
- CPU Single
- CPU Multi
- GPU Score

*Alternative Considered*: Radar chart.
*Reason for Choice*: Grouped bar charts are much easier to read for comparing distinct numeric metrics side-by-side.

## Risks / Trade-offs

- **Risk**: False positives or false negatives in mobile classification (e.g., a desktop APU being flagged as mobile, or a new laptop CPU missing mobile suffix detection).
  - *Mitigation*: Refine regex patterns to be specific, and ensure they are tested against the fallback CSV entries to ensure correct classification.
