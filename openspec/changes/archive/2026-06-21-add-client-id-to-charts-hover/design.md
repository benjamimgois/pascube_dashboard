## Context

The Pascube Benchmark Dashboard displays various charts of top CPU/GPU performance (general and mobile-specific). While client IDs are displayed on the community leaderboard table, they are not visible on the chart tooltips. Displaying a truncated client ID when hovering over chart items adds context and verification.

## Goals / Non-Goals

**Goals:**
- Extend the horizontal bar chart tooltips for the specified five charts to include a truncated `Client ID` field (8 characters).
- Maintain clean and backward-compatible chart rendering logic.
- For averaged mobile CPU/GPU charts, show the client ID corresponding to the best-performing run for that specific hardware model.

**Non-Goals:**
- Modifying other charts (like most used, distribution, or demographics charts).
- Changing database structure or sheets parsing logic.

## Decisions

### 1. Extend `renderHorizontalBarChart` signature
- **Decision:** Add an optional `clientIds` parameter to `renderHorizontalBarChart(canvasId, labels, data, datasetLabel, barColor, borderColor, xMax, xMin, clientIds)`.
- **Rationale:** Storing the `clientIds` array inside the dataset object (under `datasets[0].clientIds`) allows standard Chart.js tooltip callbacks to access the value at the corresponding hovered index via `context.dataIndex`.
- **Alternatives Considered:**
  - *Global lookup mapping*: Creating a global lookup map. This would be fragile and complex to synchronize across filters and dynamic data.

### 2. Multi-line Tooltip for Client ID
- **Decision:** Format the tooltip callback to return an array of lines. The first line displays the label and score, and the second line displays `Client ID: <first 8 chars>`.
- **Rationale:** Chart.js tooltip label callback can return an array of strings to render multi-line tooltips. This is cleaner and more readable than appending it to the same line.
- **Example:**
  ```
  CPU Single Score: 2,780
  Client ID: 2648f98e
  ```

### 3. Mobile Charts Client ID selection
- **Decision:** Update `getTopMobileCPUs` and `getTopMobileGPUs` to return the `clientId` of the top-performing run (the one with the maximum score) for each CPU/GPU model.
- **Rationale:** Since the mobile charts aggregate scores by model (averaging them), associating the client ID of the best-performing run tells who achieved the peak performance result for that model.

## Risks / Trade-offs

- **[Risk]** Missing or `N/D` client IDs.
  - *Mitigation:* The tooltip formatter handles missing client IDs or `N/D` values by displaying `N/D` (e.g. `Client ID: N/D`) or skipping the line if no client ID data is available.
