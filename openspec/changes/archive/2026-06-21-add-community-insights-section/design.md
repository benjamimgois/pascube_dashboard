## Context

The benchmark dashboard features detailed performance metrics, but lacks high-level community stats. We need to introduce the "PascubeDB Community Insights" section at the bottom of the page, containing metrics cards, a line chart of daily submissions (last 30 days), and a contributors leaderboard.

## Goals / Non-Goals

**Goals:**
- Add the `community-insights-section` layout to the bottom of `index.html`.
- Calculate metrics dynamically: Unique Contributors, Hardware Models, and Submissions in the last 7 days.
- Format YYYY-MM-DD/DD-MM-YYYY dates from CSV record strings for timeline computations.
- Render a smooth activity line chart showing daily benchmark submissions over the last 30 days.
- Display a leaderboard table of the top 5 contributors.

**Non-Goals:**
- Modifying other existing charts.

## Decisions

### 1. Dynamic Reference Date (Reference Time)
- **Decision:** Calculate the maximum date present in the benchmark dataset (`maxDate`) and use it as the reference date for "today".
- **Rationale:** If the spreadsheet is populated with static test/cached records, using the actual current time (`new Date()`) might result in the last 7 days card showing `0` runs. Setting the reference date to the latest run ensures the metrics cards show realistic, populated data regardless of the system time.

### 2. CSV Date Parser
- **Decision:** Implement a robust `parseDate(dateStr)` helper to split and parse `DD/MM/YYYY` CSV timestamps.
- **Rationale:** Ensures reliable date calculations for activity grids and day intervals without relying on external libraries (like moment or date-fns).

### 3. Activity Chart (Smooth Line Chart)
- **Decision:** Use Chart.js with the `tension: 0.4` property and a soft gradient background fill.
- **Rationale:** Yields a beautiful, modern "smooth line/wave" graph matching the premium visual style of the application.

## Risks / Trade-offs

- **[Risk]** Missing or empty client-ids.
  - *Mitigation:* The unique contributor count and leaderboard grouping logic explicitly filter out `'N/D'` or empty values.
