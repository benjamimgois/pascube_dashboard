## MODIFIED Requirements

### Requirement: Top 10 Mobile CPU Performance Chart
The system SHALL identify mobile CPUs in the dataset and render a horizontal bar chart displaying the top 10 mobile CPU models sorted by average CPU Single score in descending order. When a user hovers over a data point, the tooltip SHALL display the client-id (first 8 characters) of the best-performing run for that mobile CPU model.

#### Scenario: Rendering the Top 10 Mobile CPU Performance chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a horizontal bar chart is rendered displaying the top 10 mobile CPU models and their average CPU Single scores, including the client-id (first 8 characters) of the top run in the tooltip on hover

### Requirement: Top 10 Mobile GPU Performance Chart
The system SHALL identify mobile GPUs in the dataset and render a horizontal bar chart displaying the top 10 mobile GPU models sorted by average GPU score in descending order. When a user hovers over a data point, the tooltip SHALL display the client-id (first 8 characters) of the best-performing run for that mobile GPU model.

#### Scenario: Rendering the Top 10 Mobile GPU Performance chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a horizontal bar chart is rendered displaying the top 10 mobile GPU models and their average GPU scores, including the client-id (first 8 characters) of the top run in the tooltip on hover
