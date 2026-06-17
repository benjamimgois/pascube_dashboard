## ADDED Requirements

### Requirement: Top 10 CPU Most Used Chart
The system SHALL aggregate the benchmark data to identify the top 10 most frequently occurring CPU models and render a horizontal bar chart displaying their frequency counts.

#### Scenario: Rendering Top 10 CPU usage chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a horizontal bar chart is rendered displaying the top 10 CPU models sorted by occurrence count in descending order

### Requirement: Top 10 GPU Most Used Chart
The system SHALL aggregate the benchmark data to identify the top 10 most frequently occurring GPU models and render a horizontal bar chart displaying their frequency counts.

#### Scenario: Rendering Top 10 GPU usage chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a horizontal bar chart is rendered displaying the top 10 GPU models sorted by occurrence count in descending order

### Requirement: Operating Systems Distribution Chart
The system SHALL aggregate the count of each unique operating system name present in the benchmark data and render a pie or doughnut chart displaying their percentage distribution.

#### Scenario: Rendering Operating Systems distribution pie chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a doughnut chart is rendered showing the distribution of operating systems in the dataset

### Requirement: CPU Brands Distribution Chart
The system SHALL categorize CPU models into Intel, AMD, or Other brands and render a pie or doughnut chart showing their distribution.

#### Scenario: Rendering CPU Brands distribution pie chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a doughnut chart is rendered displaying the distribution of CPU brands (Intel, AMD, Other)

### Requirement: GPU Brands Distribution Chart
The system SHALL categorize GPU models into NVIDIA, AMD, Intel, or Other brands and render a pie or doughnut chart showing their distribution.

#### Scenario: Rendering GPU Brands distribution pie chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a doughnut chart is rendered displaying the distribution of GPU brands (Nvidia, AMD, Intel, Other)

### Requirement: Video Driver Distribution Chart
The system SHALL categorize video drivers from the dataset (such as Mesa, NVIDIA Proprietary, or Other) and render a pie or doughnut chart showing their distribution.

#### Scenario: Rendering Video Driver distribution pie chart
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** a doughnut chart is rendered displaying the distribution of video drivers (Mesa, NVIDIA, Other)
