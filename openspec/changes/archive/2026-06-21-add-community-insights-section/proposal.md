## Why

The benchmark dashboard displays detailed performance rankings and demographic distributions, but does not present high-level statistics about the dataset volume, submission activity over time, or the contributors. Introducing a "PascubeDB Community Insights" section at the end of the page will show the overall health, activity trends, and top contributors of the database.

## What Changes

- Add a new "PascubeDB Community Insights" section at the bottom of the page in `index.html`.
- Implement metric cards for:
  - Pageviews (with a mock placeholder or simple Github traffic badge/contributor metric)
  - Unique Contributors (total unique client IDs)
  - Hardware Models (total unique CPUs + unique GPUs)
  - Submissions in the last 7 days
- Implement a smooth line chart showing the trend of daily benchmark submissions over the last 30 days.
- Implement a "Top Contributors" (Hall of Fame) table displaying the top client IDs/users by number of submissions.

## Capabilities

### New Capabilities

- `dashboard-community-insights`: Specifies the layout, metrics calculation, and charts for the PascubeDB community insights section at the bottom of the page.

### Modified Capabilities

<!-- None -->

## Impact

- `index.html`: Append a new section containing metrics cards, a line chart container, and a hall of fame table at the bottom of the page.
- `app.js`: Implement the calculations for unique contributors, hardware diversity, last 7 days submissions, daily submission trend data for the last 30 days, and the top contributors list. Render the line chart and the Hall of Fame table.
- `style.css`: Add styling for the new insights section, cards, and list layout.
