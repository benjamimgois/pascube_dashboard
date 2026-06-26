# software-comparison

## Purpose
Specifies the capability to compare software versions (OS, Mesa driver, NVIDIA driver, Kernel) by average benchmark performance and display the winner for each category.

## Requirements

### Requirement: Software Winner Comparison Computation
The system SHALL group benchmark runs by their software version field, compute the average Main Score per group, and elect a winner (the version with the highest average). Groups with fewer than 3 runs SHALL be excluded from comparison.

#### Scenario: Computing the OS winner
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the system groups runs by normalized OS name, computes average Main Score per OS, and elects the OS with the highest average as the winner

#### Scenario: Computing the Mesa driver winner
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the system groups runs by Mesa major.minor version, computes average Main Score per version, and elects the version with the highest average as the winner

#### Scenario: Computing the NVIDIA driver winner
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the system groups runs by NVIDIA major.minor version, computes average Main Score per version, and elects the version with the highest average as the winner

#### Scenario: Computing the Kernel winner
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** the system groups runs by Kernel major.minor version, computes average Main Score per version, and elects the version with the highest average as the winner

### Requirement: Software Comparison Display
The system SHALL render a "Software Comparison" section with 4 cards, one for each category (OS, Mesa, NVIDIA, Kernel). Each card SHALL display:
- A category icon
- The category name
- A WINNER badge with the winning version name
- The percentage improvement of the winner over the average of all other versions

#### Scenario: Displaying the Software Comparison cards
- **WHEN** the dashboard page finishes loading the benchmark data
- **THEN** four comparison cards are rendered showing the WINNER and improvement percentage for OS, Mesa driver, NVIDIA driver, and Kernel
