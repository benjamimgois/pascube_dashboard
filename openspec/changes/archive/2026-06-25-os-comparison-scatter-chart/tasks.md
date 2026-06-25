## 1. HTML Canvas

- [x] 1.1 Adicionar container `.chart-container-wrapper` com canvas `osHardwareScatterChart` na seção Community Insights (após o chart de Package Distribution)

## 2. Data Aggregation

- [x] 2.1 Criar função `getOSvsHardwareScatterData()` que agrupa benchmarks por hardware key (`normalizeCPU + normalizeGPU`), retorna top 15 hardwares por contagem, e mapeia pontos com {x, y, os, user, clientId, kernel, driver, hardwareLabel}

## 3. Scatter Chart Renderer

- [x] 3.1 Criar função `renderOSHardwareScatterChart(canvasId, data)` que renderiza Chart.js scatter com:
  - Eixo X = índice do hardware (0..14), labels mapeados via `ticks.callback`
  - Eixo Y = mainScore
  - Dataset separado por OS, cada um com cor distinta
  - pointRadius: 5, backgroundColor com alpha 0.7
  - Tooltip customizado mostrando hardware, OS, score, user, clientId

- [x] 3.2 Implementar paleta de cores por OS (Ubuntu, Fedora, Arch, SteamOS, Bazzite, CachyOS, Nobara, Linux Mint, Pop!_OS, Other)

## 4. Integration

- [x] 4.1 Chamar `getOSvsHardwareScatterData()` e `renderOSHardwareScatterChart()` dentro do bloco Community Insights na `renderCharts()`
- [x] 4.2 Limitar a hardwares com 3+ amostras para evitar overplotting
- [x] 4.3 Destruir instância anterior do chart se existir no `chartInstances`

## 5. Verification

- [ ] 5.1 Abrir index.html no navegador e confirmar que scatter chart aparece em Community Insights
- [ ] 5.2 Verificar tooltips com hardware, OS, score, user
- [ ] 5.3 Verificar cores distintas por OS
