## Context

We need to implement 5 new advanced charts:
1. Average CPU Multi Score by CPU model.
2. Average GPU Score by GPU model.
3. Average Main Score by OS.
4. Score Distribution Histogram (density).
5. Version distributions for Mesa and Kernel major versions.

## Goals / Non-Goals

**Goals:**
- Design a clean layout grid for the advanced performance and density stats.
- Write robust version parsers for Mesa and Kernel version strings.
- Aggregate averages correctly, avoiding samples with small counts skewing the data (e.g. only models/operating systems with at least 1 or 2 runs).
- Implement dynamic binning logic for the score density histogram.

**Non-Goals:**
- Modifying current benchmark submission flow.

## Decisions

### 1. Advanced Section Layout
- **Choice**: Group charts in a new layout section `advanced-charts-section` with:
  - An `advanced-averages-grid` containing the 3 average score charts (CPU, GPU, OS) in a 3-column layout.
  - An `advanced-density-grid` containing the Histogram (large/vertical bar) and two version distribution doughnut charts (Mesa, Kernel).
- **Rationale**: Groups performance indicators separately from version/OS metadata.

### 2. Averages Threshold Filtering
- **Choice**: Only display CPU/GPU models with at least 1 valid benchmark score to calculate average.
- **Rationale**: Since the database is relatively small, we don't need a high threshold, but we should ignore null values.

### 3. Version String Parsing
- **Choice**:
  - *Mesa Version*: Extract major/minor digits from string (e.g., `Mesa 26.1.2` -> `Mesa 26.1`, `Mesa 26.0.6` -> `Mesa 26.0`).
  - *Kernel Version*: Extract major/minor digits from kernel string (e.g., `7.0.12-1-cachyos` -> `7.0`, `6.19.10` -> `6.19`).
- **Rationale**: Merging micro-releases avoids having dozens of legend items and keeps the charts legible.

## Risks / Trade-offs

### [Risk] Version parsing failures on custom formats → Mitigation
- *Risk*: A customized driver or kernel string format is not matched by the regex.
- *Mitigation*: Fall back to a default value like "Other" or "Unknown Version".
