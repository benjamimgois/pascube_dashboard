## Why

Atualmente não há like visual para comparar desempenho do mesmo hardware rodando SOs diferentes. Usuários não conseguem ver, por exemplo, se um Steam Deck tem score maior no SteamOS vs Arch Linux, ou se uma mesma GPU roda melhor no Ubuntu vs Fedora. Um scatter chart preenche essa lacuna.

## What Changes

- Novo scatter chart na seção Community Insights: eixo X = hardware (CPU+GPU normalizado), eixo Y = mainScore, pontos coloridos por OS
- Tooltip mostra: hardware, OS, score, user, kernel/driver
- Agrupamento inteligente: mesmo hardware (CPU+GPU) com múltiplos OS aparece como cluster
- Linha de média por OS para cada hardware com 3+ amostras

## Capabilities

### New Capabilities
- `os-hardware-scatter`: Scatter chart de mainScore por combinação hardware + SO, com agrupamento por OS

### Modified Capabilities
<!-- nenhuma spec existente é alterada -->

## Impact

- `app.js`: nova função de agregação + renderização do chart (~80-100 linhas)
- `index.html`: novo container de canvas na seção Community Insights
- Nenhuma dependência nova (Chart.js já incluso)
