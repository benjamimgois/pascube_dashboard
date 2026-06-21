## Why

When hovering over performance records in the top charts, it is currently not possible to identify which client submitted the result. Adding a truncated client ID (first 8 characters) to the hover popups enables users to quickly identify and verify submissions, distinguishing between multiple runs or authors.

## What Changes

- Modify tooltips in CPU Single-Thread, CPU Multi-Thread, and GPU Performance charts to display the `client-id` (first 8 characters) of the submitting run.
- Modify tooltips in Top 10 Mobile CPU Performance and Top 10 Mobile GPU Performance charts to display the `client-id` (first 8 characters) of the best run for that model.

## Capabilities

### New Capabilities

<!-- None -->

### Modified Capabilities

- `dashboard-advanced-charts`: Show the client-id (first 8 characters) in tooltips/popups when hovering over data points in CPU Single-Thread, CPU Multi-Thread, and GPU Performance charts.
- `dashboard-mobile-charts`: Show the client-id (first 8 characters) in tooltips/popups when hovering over data points in Top 10 Mobile CPU Performance and Top 10 Mobile GPU Performance charts.

## Impact

- `app.js`: Update the chart tooltip rendering configurations and the `getTopMobileCPUs` and `getTopMobileGPUs` aggregation functions.
