## 1. HTML Section Layout

- [x] 1.1 Add the new `community-insights-section` element containing the metrics cards and chart canvas to `index.html`.
- [x] 1.2 Relocate the Community Leaderboard section into a modal dialog container in `index.html`, and add a Leaderboard button in the header actions.

## 2. JavaScript Implementation

- [x] 2.1 Implement the `parseDate` helper function in `app.js` to parse benchmark dates.
- [x] 2.2 Calculate and render the metrics cards (Unique Contributors, Hardware Models, Submissions in last 7 days) in `app.js`.
- [x] 2.3 Calculate the daily submissions dataset for the last 30 days and render the line chart using Chart.js in `app.js`.
- [x] 2.4 Implement setupEventListeners changes to open/close the modal and handle light-dismiss boundary checking fallback.

## 3. CSS Styling

- [x] 3.1 Style the metrics cards and activity chart to match the theme in `style.css`.
- [x] 3.2 Style the modal popup, including glassmorphism backdrop, sizing, layout, header close button, and responsive media query stacking.

## 4. Verification

- [x] 4.1 Verify that the metric card counts are calculated correctly.
- [x] 4.2 Verify that the line chart renders a trend of daily submissions.
- [x] 4.3 Verify that the Leaderboard modal opens and closes correctly on button click, backdrop click, and Esc key, and allows vertical scrolling.
