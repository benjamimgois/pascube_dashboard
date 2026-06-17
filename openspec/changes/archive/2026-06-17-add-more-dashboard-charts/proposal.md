## Why

The benchmark dashboard would benefit from advanced performance and configuration analysis, including average score by hardware model, average score by operating system, distribution of Mesa/Kernel versions, and score density histograms.

## What Changes

- Add "Average Score by CPU" horizontal bar chart.
- Add "Average Score by GPU" horizontal bar chart.
- Add "Average Score by OS" horizontal bar chart.
- Add "Mesa & Kernel Version Distribution" doughnut/bar charts.
- Add "Score Distribution (Histogram)" vertical bar chart.
- Optimize dashboard CSS layout and HTML structure to group and display these new charts.

## Capabilities

### New Capabilities

- `dashboard-advanced-charts`: Renders advanced metrics, averages, and distribution histograms on the dashboard.

### Modified Capabilities

<!-- None -->

## Impact

- `index.html`: Canvas elements and wrappers for advanced charts.
- `app.js`: Implementation of score average calculations, version parser regexes, bin/histogram distribution buckets, and chart definitions.
- `style.css`: Additional styling for advanced metrics section grid.
