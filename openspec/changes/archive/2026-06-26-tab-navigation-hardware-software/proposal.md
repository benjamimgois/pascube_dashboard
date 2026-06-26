## Why

Navegacao atual tem 6 pills (Highest, Demographics, Advanced, Software, Portable, Community) que ocupam muito espaco e misturam metricas de hardware com software. Separar em 2 abas (Hardware / Software) organiza melhor o conteudo.

## What Changes

- Substituir 6 nav-pills por 2 tabs: "Hardware benchmark" e "Software benchmark"
- Aba Hardware: todos os graficos exceto Software Comparison e Package Distribution
- Aba Software: Software Comparison (scatters + winners) + Package Distribution
- Stats grid do topo permanece visivel em ambas as abas
- JS para alternar visibilidade das secoes conforme tab ativa

## Capabilities

### New Capabilities
- `tab-navigation`: Sistema de 2 abas (Hardware/Software) com toggle de visibilidade

### Modified Capabilities
- (nenhuma — mudanca de UI apenas)

## Impact

- `index.html`: nav section, reorganizacao das secoes
- `style.css`: estilos dos novos tabs
- `app.js`: logica de toggle das secoes por tab
