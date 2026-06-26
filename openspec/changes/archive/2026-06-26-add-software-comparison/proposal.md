## Why

Comparar qual versao de OS, Mesa, NVIDIA driver e Kernel entrega o melhor desempenho medio ajuda a comunidade a decidir qual software usar. Atualmente os charts de versao mostram apenas distribuicao (contagem), nao performance.

## What Changes

- Adicionar nova secao "Software Comparison" entre Advanced e Portable Devices
- Criar 4 cards comparativos: OS, Mesa Driver, NVIDIA Driver, Kernel
- Cada card elege um WINNER (versao com maior media de Main Score)
- Mostrar estatistica de % de melhoria do vencedor sobre a media dos outros
- Calcular usando dados ja existentes (getOSDistribution, getVersionDistribution + medias)

## Capabilities

### New Capabilities
- `software-comparison`: Secao com cards comparativos de software (OS, Mesa, NVIDIA, Kernel) que elegem vencedor por performance

### Modified Capabilities
- (nenhuma — nova secao, nao altera specs existentes)

## Impact

- `app.js`: nova funcao `getSoftwareWinner()` + renderizacao de cards
- `index.html`: nova secao Software Comparison com 4 cards
- `style.css`: estilos para os cards de comparacao (WINNER badge)
