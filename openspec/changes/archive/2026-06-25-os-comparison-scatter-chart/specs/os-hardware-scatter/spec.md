## ADDED Requirements

### Requirement: OS-vs-hardware scatter chart
The system SHALL render a scatter chart in the Community Insights section plotting mainScore against hardware configuration, with points colored by operating system.

#### Scenario: Scatter chart renders with correct axes
- **WHEN** benchmark data is loaded and Community Insights section is visible
- **THEN** a scatter chart SHALL appear with hardware label on X-axis (formatted as "CPU + GPU"), mainScore on Y-axis, and each point colored by OS

#### Scenario: Points grouped by OS
- **WHEN** multiple benchmarks share the same hardware (CPU+GPU combo)
- **THEN** each point SHALL be colored according to its OS, forming clusters per hardware

#### Scenario: Tooltip shows benchmark details
- **WHEN** user hovers over a scatter point
- **THEN** tooltip SHALL display: hardware label, OS name, mainScore, user name, and clientId

#### Scenario: Hardware selection limited to top N
- **WHEN** there are more hardware combos than visible slots
- **THEN** only the top 15 hardware combos (by total submission count) SHALL appear, with scrollable navigation via `makeChartScrollable`

#### Scenario: Color mapping for OS
- **WHEN** mapping OS to colors
- **THEN** common OS (Ubuntu, Fedora, Arch, SteamOS, Bazzite, CachyOS, Nobara, Linux Mint, Pop!_OS) SHALL have distinct assigned colors, and other OS SHALL be gray
