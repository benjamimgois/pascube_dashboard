# tab-navigation

## Purpose
Specifies the two-tab navigation system (Hardware Benchmark / Software Benchmark) that organizes dashboard sections by category.

## Requirements

### Requirement: Tab Navigation Toggle
The system SHALL render two tab buttons at the top of the dashboard: "Hardware benchmark" and "Software benchmark". Clicking a tab SHALL show the sections belonging to that category and hide the other.

#### Scenario: Switching to Hardware tab
- **WHEN** user clicks "Hardware benchmark" tab
- **THEN** all hardware sections (stats grid, charts, demographics, advanced, portable, community) are visible and software sections (Software Comparison, Package Distribution) are hidden

#### Scenario: Switching to Software tab
- **WHEN** user clicks "Software benchmark" tab
- **THEN** software sections (Winner cards, Software Comparison, Package Distribution) are visible and hardware sections (stats grid, charts, demographics, advanced, portable, community) are hidden

### Requirement: Default Tab
The system SHALL activate the "Hardware benchmark" tab by default when the page loads.

#### Scenario: Page load
- **WHEN** the dashboard page loads
- **THEN** the "Hardware benchmark" tab is active and hardware sections are displayed
