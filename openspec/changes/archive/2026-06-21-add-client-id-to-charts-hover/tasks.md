## 1. Modify Helper and Aggregation Functions

- [x] 1.1 Update `getTopMobileCPUs` in `app.js` to return `{ name, avg, clientId }`, where `clientId` corresponds to the best-performing run.
- [x] 1.2 Update `getTopMobileGPUs` in `app.js` to return `{ name, avg, clientId }`, where `clientId` corresponds to the best-performing run.
- [x] 1.3 Update `renderHorizontalBarChart` in `app.js` to accept a `clientIds` parameter and store it in `datasets[0].clientIds`.
- [x] 1.4 Update the Chart.js tooltip label callback in `renderHorizontalBarChart` to render a second line with the truncated client ID if available.

## 2. Update Chart Render Calls

- [x] 2.1 Update the Top 10 CPU Single Thread chart render call in `renderCharts` to map and pass the client ID array.
- [x] 2.2 Update the Top 10 CPU Multi Thread chart render call in `renderCharts` to map and pass the client ID array.
- [x] 2.3 Update the Top 10 GPU Performance chart render call in `renderCharts` to map and pass the client ID array.
- [x] 2.4 Update the Top 10 Mobile CPU Performance chart render call in `renderCharts` to map and pass the client ID array.
- [x] 2.5 Update the Top 10 Mobile GPU Performance chart render call in `renderCharts` to map and pass the client ID array.

## 3. Verification

- [x] 3.1 Verify tooltips display the correct truncated client ID (first 8 characters) on hover for the general CPU Single, CPU Multi, and GPU charts.
- [x] 3.2 Verify tooltips display the correct truncated client ID (first 8 characters) on hover for the Mobile CPU and Mobile GPU charts.
