## Context

Dashboard ja tem distribuicao de versoes (Mesa, Kernel, NVIDIA) mas nao mostra qual versao performa melhor. A comparacao por media de Main Score agrupado por versao revela o vencedor.

## Goals / Non-Goals

**Goals:**
- Criar funcao `getSoftwareWinner(data, type)` que retorna {winner, avg, improvement} para OS/Mesa/NVIDIA/Kernel
- Renderizar 4 cards com WINNER badge, nome da versao, e % improvement
- Secao posicionada entre Advanced e Portable Devices

**Non-Goals:**
- Nao criar novos graficos — sao cards de texto/estatistica

## Decisions

- **Agrupamento**: 
  - OS: agrupar por nome normalizado (getOSDistribution)
  - Mesa: agrupar por major.minor (getVersionDistribution com type='mesa')
  - NVIDIA: agrupar por major.minor (getVersionDistribution com type='nvidia')
  - Kernel: agrupar por major.minor (getVersionDistribution com type='kernel')
- **Calculo**: Para cada grupo, media de Main Score. Winner = grupo com maior media.
- **Improvement**: `((winner_avg - others_avg) / others_avg) * 100` onde others_avg é a media dos demais grupos
- **Layout**: Grid de 4 cards (2x2 ou 4x1), cada um com icone, label, WINNER badge, e stats

## Risks / Trade-offs

- [Vies de hardware] Versoes novas de software podem ter media mais alta por serem usadas em hardware mais potente — nao controlamos por hardware. Aceitavel para comparacao simples.
- [Poucos dados] Versoes com 1-2 runs podem distorcer — filtrar grupos com < 3 runs (configuravel)
