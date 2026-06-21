## Why

The benchmark dashboard currently provides overall performance charts and general hardware demographics, but lacks a dedicated section focused on mobile computing form factors. Adding a section for mobile devices (laptops and handheld gaming PCs) will allow users to compare and analyze performance trends specifically tailored to portable hardware, which has unique thermal and power constraints.

## What Changes

- Create a new "Mobile Devices" section on the dashboard page.
- Implement classification logic in the data processing layer to identify handhelds and laptops/notebooks based on CPU, GPU, OS, and Kernel strings.
- Add five new interactive charts focusing on mobile devices:
  - Mobile Device Type Distribution (Doughnut chart): Handheld vs. Notebook representation.
  - Top 10 Mobile CPU Performance (Horizontal bar chart): Highest CPU Single and Multi thread scores for mobile processors.
  - Top 10 Mobile GPU Performance (Horizontal bar chart): Highest GPU scores for mobile graphics processors.
  - Top 10 Handheld Performance (Horizontal bar chart): Highest overall scores specifically for handheld gaming PCs.
  - Notebook vs. Handheld Averages (Grouped bar chart): Comparison of average benchmark scores (Main, CPU Single, CPU Multi, GPU) between laptops and handhelds.

## Capabilities

### New Capabilities
- `dashboard-mobile-charts`: Adds a dedicated "Mobile Devices" section to the dashboard with targeted hardware categorization, mobile-specific performance charts, and form factor comparisons.

### Modified Capabilities

## Impact

- `index.html`: Adds new canvas elements and layout structures for the mobile charts.
- `app.js`: Adds mobile hardware detection logic, data filtering/aggregation functions for mobile devices, and Chart.js instantiation code for the five new charts.
- `style.css`: Adds styling for the new mobile section and layout grid responsive adjustments.
