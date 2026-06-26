# dashboard-community-insights

## Purpose
TBD

## Requirements

### Requirement: Community Metrics Cards
The system SHALL calculate and display four metric cards at the bottom of the page:
1. Pageviews (mocked/static placeholder).
2. Unique Contributors (count of unique client-ids).
3. Hardware Models (count of unique CPUs + unique GPUs).
4. Submissions in last 7 days (count of submissions within the last 7 days).

#### Scenario: Displaying community metrics cards
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** four metric cards displaying Pageviews, Unique Contributors, Hardware Models, and Submissions in last 7 days are rendered at the bottom of the page.

### Requirement: Daily Submission Activity Chart
The system SHALL compute daily submission counts for the last 30 days and render a smooth line chart displaying these counts over time.

#### Scenario: Displaying daily submission activity chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a line chart with a smooth curved line is rendered showing the daily benchmark submission counts for the last 30 days.

### Requirement: Package Distribution Chart
The system SHALL read the "package" field from each benchmark row, aggregate the count of each unique package type (e.g., native, flatpak, appimage), and render a doughnut chart displaying their distribution below the Submission Activity chart in the Community Insights section.

#### Scenario: Rendering the Package Distribution chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a doughnut chart is rendered displaying the percentage distribution of package types among all benchmark submissions, with empty/missing values grouped as "Unknown"
