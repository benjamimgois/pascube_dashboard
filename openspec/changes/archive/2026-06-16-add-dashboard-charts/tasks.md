## 1. UI Layout Updates

- [x] 1.1 Add chart canvas elements for Top 10 CPU / Top 10 GPU usage charts to index.html
- [x] 1.2 Add chart canvas elements for OS, CPU Brand, GPU Brand, and Video Driver doughnut charts to index.html
- [x] 1.3 Add CSS styles to style.css for demographics and distribution chart container grids

## 2. Core Implementation in app.js

- [x] 2.1 Implement CPU and GPU model frequency aggregation functions in app.js
- [x] 2.2 Implement brand categorizers (Intel vs AMD for CPU; NVIDIA vs AMD vs Intel for GPU) in app.js
- [x] 2.3 Implement video driver categorizers (Mesa vs NVIDIA vs Other) in app.js
- [x] 2.4 Update `renderCharts` in app.js to initialize new horizontal bar and doughnut charts

## 3. Verification

- [x] 3.1 Verify charts render correctly using mock/fallback CSV data
- [x] 3.2 Verify charts render correctly using real Google Sheets data (if online)
