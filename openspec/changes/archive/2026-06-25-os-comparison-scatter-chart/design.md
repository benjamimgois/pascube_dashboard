## Context

Community Insights section já tem charts estáticos (bar, donut, line). Falta visual que cruze hardware × OS × score. Scatter chart é ideal: cada ponto = um benchmark, eixo X = hardware (CPU+GPU), eixo Y = mainScore, cor = OS.

## Goals / Non-Goals

**Goals:**
- Scatter chart na Community Insights mostrando mainScore por combinação hardware + SO
- Pontos coloridos por SO, tooltip com hardware, SO, score, user, clientId
- Hardware no eixo X usa label `${normalizeCPU} + ${normalizeGPU}`

**Non-Goals:**
- Não alterar charts existentes
- Não adicionar dependências novas
- Não modificar filtros ou leaderboard

## Decisions

- **Chart type**: `scatter` do Chart.js (nativo, sem plugin extra)
- **Eixo X**: labels categóricos (hardware). Chart.js scatter espera dados numéricos, então usaremos `type: 'scatter'` com coordenadas numéricas e `ticks.callback` pra mapear de volta ao label, OU usaremos `type: 'bar'` com `datasets` separados por OS. Decisão: usar `scatter` com eixo X numérico (índice do hardware) e `ticks.callback` para exibir label truncado.
- **Cores por OS**: paleta fixa mapeada para OS mais comuns (Ubuntu, Fedora, Arch, SteamOS, etc), cinza para "Other"
- **Agrupamento**: hardware key = `${normalizeCPU(r.cpu)} + ${normalizeGPU(r.gpu)}` (mesmo padrão já usado em other charts)
- **Tooltip**: exibe hardware completo, OS, mainScore, user, kernel/driver

## Risks / Trade-offs

- **Eixo X denso**: muitos hardwares únicos → labels truncados. Mitigação: mostrar ~15-20 hardwares com mais amostras via `makeChartScrollable`.
- **Overplotting**: múltiplos pontos no mesmo hardware+OS. Mitigação: Chart.js scatter com `pointRadius` pequeno (4) e semi-transparência.
- **Performance**: scatter com muitos pontos (~500+) pode ficar lento. Mitigação: limitar a hardwares com 3+ amostras totais.
