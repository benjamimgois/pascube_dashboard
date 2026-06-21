## Why

Users of portable devices, particularly handheld gaming PCs, run a variety of customized Linux distributions (e.g. SteamOS, Bazzite, Nobara, ChimeraOS). Adding dedicated Operating System distribution charts for all mobile devices and specifically for handhelds will help the community analyze software trends and popularity of different operating systems across these portable form factors.

## What Changes

- Add two new distribution charts inside the Mobile Devices section of the dashboard:
  - Mobile OS Distribution (Doughnut chart): Operating system distribution for all mobile devices (Laptops/Notebooks + Handhelds).
  - Handheld OS Distribution (Doughnut chart): Operating system distribution exclusively for Handheld gaming PCs.
- Implement data aggregation logic in the JavaScript frontend to filter and categorize operating system strings for these subgroups.
- Create container markup and canvas elements in the HTML dashboard structure for the new charts.

## Capabilities

### New Capabilities
- `mobile-os-charts`: Adds OS distribution charts for all mobile devices and handheld gaming PCs to the dashboard's Mobile Devices section.

### Modified Capabilities

## Impact

- `index.html`: Adds new canvas elements and styling structures for the two OS distribution charts.
- `app.js`: Adds data processing, filtering, and aggregation functions for mobile and handheld OS distribution, and instantiates the new Chart.js doughnut charts.
- `style.css`: Updates layouts to integrate the two new charts cleanly into the existing grids.
