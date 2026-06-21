## ADDED Requirements

### Requirement: CPU Single-Thread Top 10 Chart with Client ID
The system SHALL render a horizontal bar chart displaying the top 10 CPU models sorted by CPU Single score in descending order. When hovering over a bar in the chart, the tooltip SHALL display the score and the client-id (first 8 characters) of the run.

#### Scenario: Rendering CPU Single Thread Top 10 Chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the top 10 CPU Single-Thread chart is rendered and displays the client-id (first 8 characters) of the run in the tooltip on hover

### Requirement: CPU Multi-Thread Top 10 Chart with Client ID
The system SHALL render a horizontal bar chart displaying the top 10 CPU models sorted by CPU Multi score in descending order. When hovering over a bar in the chart, the tooltip SHALL display the score and the client-id (first 8 characters) of the run.

#### Scenario: Rendering CPU Multi Thread Top 10 Chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the top 10 CPU Multi-Thread chart is rendered and displays the client-id (first 8 characters) of the run in the tooltip on hover

### Requirement: GPU Performance Top 10 Chart with Client ID
The system SHALL render a horizontal bar chart displaying the top 10 GPU models sorted by GPU score in descending order. When hovering over a bar in the chart, the tooltip SHALL display the score and the client-id (first 8 characters) of the run.

#### Scenario: Rendering GPU Performance Top 10 Chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the top 10 GPU Performance chart is rendered and displays the client-id (first 8 characters) of the run in the tooltip on hover
