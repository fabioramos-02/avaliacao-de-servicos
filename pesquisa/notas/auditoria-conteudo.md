# Auditoria de conteúdo — consolidação 2026-08-28

Nota interna registrando a transformação do repositório em uma entrega executiva enxuta.

## Antes → depois

**Antes:** 8 subpastas em `docs/` (01-contexto até 08-to-be) com ~25 arquivos markdown, sobreposição real entre pastas 04-cidadao e 05-proposta, deep-dives técnicos misturados com material de decisão.

**Depois:** 7 documentos planos em `docs/` mais um `index.md`, alinhados à âncora gov.br (Portaria SGD/MGI nº 1.083/2025). Material técnico e deep-dives preservados em `pesquisa/notas/`.

## Tabela origem → destino

| Origem (removida) | Destino | Ação |
|---|---|---|
| `docs/01-contexto/feature.md` | `docs/01-contexto.md` | Mesclado |
| `docs/01-contexto/objetivos.md` | `docs/01-contexto.md` | Mesclado |
| `docs/02-modelos/modelos-avaliacao.md` | `docs/02-referencia.md` (seção "Modelos de escala") | Consolidado |
| `docs/02-modelos/comparativo.md` | `docs/02-referencia.md` (seção "Modelos de escala") | Consolidado |
| `docs/02-modelos/nps.md` | `pesquisa/notas/deep-dives-modelos.md` | Movido |
| `docs/02-modelos/csat.md` | `pesquisa/notas/deep-dives-modelos.md` | Movido |
| `docs/02-modelos/ces.md` | `pesquisa/notas/deep-dives-modelos.md` | Movido |
| `docs/03-benchmark/gov-br.md` | `docs/02-referencia.md` (corpo principal) | gov.br vira o corpo |
| `docs/03-benchmark/central-de-qualidade.md` | `pesquisa/notas/deep-dives-benchmark.md` | Movido |
| `docs/03-benchmark/ferramenta-de-avaliacao.md` | `pesquisa/notas/deep-dives-benchmark.md` | Movido |
| `docs/03-benchmark/comparativo.md` | `docs/02-referencia.md` (seção "Referências analisadas") | Consolidado |
| `docs/03-benchmark/visao-geral.md` | `pesquisa/notas/deep-dives-benchmark.md` | Movido |
| `docs/03-benchmark/{airbnb,amazon,google,ifood,uber,gov-uk}.md` | `pesquisa/notas/deep-dives-benchmark.md` | Movido em bloco |
| `docs/04-cidadao/o-que-coletar.md` | `docs/04-dados-e-privacidade.md` | Consolidado |
| `docs/04-cidadao/perguntas.md` | `docs/03-modelo-proposto.md` (elimina duplicação com 05-proposta/perguntas.md) | Consolidado |
| `docs/04-cidadao/dados-obrigatorios.md` | `docs/04-dados-e-privacidade.md` | Consolidado |
| `docs/04-cidadao/lgpd.md` | `docs/04-dados-e-privacidade.md` | Consolidado |
| `docs/05-proposta/modelo-proposto.md` | `docs/03-modelo-proposto.md` | Documento principal |
| `docs/05-proposta/perguntas.md` | `docs/03-modelo-proposto.md` | Consolidado |
| `docs/05-proposta/escala.md` | `docs/03-modelo-proposto.md` | Consolidado |
| `docs/05-proposta/fluxo.md` | `docs/03-modelo-proposto.md` | Consolidado |
| `docs/05-proposta/matriz-decisao.md` | `docs/07-recomendacao.md` (seção "Alternativas consideradas") | Consolidado |
| `docs/05-proposta/indicadores.md` | `docs/05-indicadores.md` | Renomeado + revisado |
| `docs/06-validacao/estrategia.md` | `docs/06-validacao.md` | Consolidado |
| `docs/06-validacao/criterios-aceite.md` | `docs/06-validacao.md` | Consolidado |
| `docs/06-validacao/stakeholders.md` | `docs/06-validacao.md` | Consolidado |
| `docs/07-conclusao/recomendacao.md` | `docs/07-recomendacao.md` | Documento principal |
| `docs/07-conclusao/decisoes.md` | `docs/07-recomendacao.md` (seção "Registro de decisões") | Consolidado |
| `docs/07-conclusao/proximos-passos.md` | `docs/07-recomendacao.md` (seção "Próximos passos") | Consolidado |
| `docs/08-to-be/avaliacao-de-servico-to-be.md` | `pesquisa/notas/to-be-xvia.md` | Preservado como contrato com fornecedor, fora da entrega executiva |
| `docs/pesquisa/evidencias.md` (template vazio) | — | Deletado |
| `pesquisa/evidencias.md` (raiz, template vazio) | — | Deletado |
| `pesquisa/fontes.md` (raiz, duplicata de `docs/pesquisa/fontes.md`) | — | Deletado |

## Padrão editorial aplicado

- Linguagem institucional — Superintendente Sênior falando com Diretoria.
- Substituição sistemática de jargão: benchmark→referências analisadas, framework→modelo, jornada→caminho percorrido, feedback→avaliação, stakeholders→áreas envolvidas, KPI→indicador, dashboard→painel.
- Marcadores mantidos: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`, `[RECOMENDAÇÃO]`, `**Não identificado**`.
- Fontes centralizadas em `docs/pesquisa/fontes.md`.

## Critério de sucesso

Um diretor da SETDIG entende problema → referência → proposta → decisão em 10 minutos, com fontes rastreáveis.
