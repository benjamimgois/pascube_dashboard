## Context

Atualmente 6 nav pills controlam visibilidade de secoes individuais. Precisamos simplificar para 2 tabs principais que agrupam secoes relacionadas.

## Goals / Non-Goals

**Goals:**
- 2 tabs: Hardware benchmark, Software benchmark
- Tab Hardware mostra Stats grid + secoes: Highest, Demographics, Advanced, Portable, Community
- Tab Software mostra Software Comparison + Package Distribution
- Stats grid sempre visivel
- Tab ativa destacada visualmente

**Non-Goals:**
- Nao alterar conteudo interno das secoes

## Decisions

- **Toggle**: CSS class `active` no tab, secoes com `data-tab="hardware|software"`, JS toggle via `display`
- **Default**: Tab Hardware ativa no carregamento
- **Package Distribution**: Movido de Community Insights para Software benchmark

## Risks

- [Scroll position] Alternar tabs pode resetar scroll — usar `overflow` controlado
