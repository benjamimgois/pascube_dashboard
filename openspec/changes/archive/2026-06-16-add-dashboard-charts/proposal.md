## Why

The current dashboard only displays performance ranking charts for Top 8 CPU (Single and Multi-threaded) and Top 8 GPU. To provide deeper insight into the community hardware demographics, the dashboard needs charts showing system hardware distribution and popularity (most used models and brands).

## What Changes

- Add "Top 10 CPU - Most used" horizontal bar/pie/doughnut chart showing frequency of CPU models.
- Add "Top 10 GPU - Most used" horizontal bar/pie/doughnut chart showing frequency of GPU models.
- Add "Operating Systems" distribution pie/doughnut chart.
- Add "CPU Brands" distribution pie/doughnut chart (Intel vs AMD).
- Add "GPU Brands" distribution pie/doughnut chart (Intel vs AMD vs NVIDIA).
- Add "Video Driver" distribution pie/doughnut chart.
- Update layout and styling to gracefully accommodate the new charts while keeping the premium aesthetic.

## Capabilities

### New Capabilities

- `dashboard-analytics-charts`: Renders new distribution charts and hardware usage statistics on the benchmark dashboard.

### Modified Capabilities

<!-- None -->

## Impact

- `index.html`: New layout containers and canvas tags for the additional charts.
- `app.js`: Data aggregation, hardware string parsing (e.g. mapping CPU/GPU names to Intel, AMD, NVIDIA brands), and rendering logic using Chart.js.
- `style.css`: UI layout adjustments, grid updates, and sizing for the new chart containers.
