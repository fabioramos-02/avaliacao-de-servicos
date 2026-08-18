# Contexto e plano de implementação

Documento vivo do estudo **Avaliação dos Serviços do Portal MS**. Atualiza a cada onda concluída.

---

## Objetivo

Definir como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão.

Ponto de partida: **replicar/adaptar o modelo do gov.br** (Central de Qualidade + Ferramenta de Avaliação), padronizado pela Portaria SGD/ME 548/2022. Este é o padrão nacional que o MGI adotou e que outros entes públicos vêm seguindo.

## Referências oficiais

- Central de Qualidade — https://www.gov.br/governodigital/pt-br/estrategias-e-governanca-digital/transformacao-digital/central-de-qualidade
- Ferramenta de Avaliação — https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao
- Portaria SGD/MGI nº 1.083/2025 (vigente) — revisou a 548/2022.
- Portaria SGD/ME nº 548/2022 — padronização original do instrumento.
- Lei 13.460/2017 (Código de Defesa do Usuário de Serviço Público).
- Lei 13.709/2018 (LGPD).

## Modelo padrão gov.br (base do estudo)

- Pergunta principal: "Como foi a sua experiência com o serviço?"
- Escala: 5 estrelas rotuladas — Péssima / Ruim / Mais ou menos / Boa / Excelente.
- Pergunta 2 opcional: "O que você mais gostou em nosso serviço?" — 6 cards (marque até 3): Fácil de usar, Site/aplicativo funcionou bem, Informações claras, Consegui resolver, Foi rápido, Fácil de encontrar.
- Campo aberto opcional (até 2000 caracteres).
- Bloco acessibilidade opcional (autodeclaração PcD).

---

## Estrutura do estudo

```
docs/
├── 01-contexto/         Panorama do estudo
├── 02-modelos/          NPS, CSAT, CES, escalas, comparativo teórico
├── 03-benchmark/        gov.br (âncora) + referências secundárias
├── 04-cidadao/          O que perguntar + LGPD
├── 05-proposta/         Modelo para o Portal MS + matriz de decisão
├── 06-validacao/        Estratégia com stakeholders
└── 07-conclusao/        Recomendação e próximos passos
```

Documentação navegável via MkDocs (`http://127.0.0.1:8000` local).

---

## Plano de execução — ondas

| # | Onda | Escopo | Status |
|---|------|--------|--------|
| 1a | Modelos de avaliação | NPS/CSAT/CES/SUS/ACSI, escalas, adequação a serviço público | ✅ Concluída |
| 1b | Benchmark mercado | iFood, Uber, Airbnb, Google, Amazon (referência secundária) | ⏳ Em andamento |
| 1c | Benchmark governo | GOV.UK, gov.br federal, USDS (contexto global) | ⏳ Em andamento |
| 1d | Deep dive gov.br | Central de Qualidade + Ferramenta de Avaliação (âncora) | ✅ Concluída |
| 2a | UX/Service Design | Momento ideal, tamanho de formulário, taxa de resposta | ⏳ Em andamento |
| 2b | Dados/Analytics | Indicadores, dimensões, estrutura BI | ⏳ Em andamento |
| 2c | LGPD/Governança | Base legal, minimização, retenção | ⏳ Em andamento |
| 3 | Proposta + Validação | Modelo para MS + matriz decisão + estratégia validação | ⬜ Pendente |
| 4 | Empacotamento MkDocs | Build, revisão navegação, ajustes finais | ⬜ Pendente |

---

## Onde paramos

**Última ação:** reorientação do estudo — gov.br promovido a referência principal (era um de vários benchmarks). Refatoração dos docs em curso para linguagem simples, macro estratégica, sem jargão de backlog.

**Próximos passos imediatos:**

1. Aguardar conclusão dos agentes das ondas 1b, 1c e 1d.
2. Rodar ondas 2a/2b/2c em paralelo.
3. Consolidar em proposta do MS (onda 3).
4. Build final MkDocs.

---

## Design system e visual

- Tema MkDocs Material com paleta SEGOV (#004F9F azul primário, #30302E darkgray).
- Logo oficial SEGOV em `docs/assets/img/segov-logo.svg`.
- CSS customizado em `docs/assets/css/segov.css` (light + dark modes).
- Fonte: system-ui (padrão gov MS).

## Como rodar a documentação

```bash
pip install -r requirements.txt
python -m mkdocs serve -a 127.0.0.1:8000
```

Build estático:

```bash
python -m mkdocs build
```

---

## Princípios do estudo

1. **gov.br é a âncora.** Divergir do padrão federal exige justificativa.
2. **Menos é mais.** Cidadão de serviço público não tolera formulário longo.
3. **Coletar só o que será usado.** LGPD art. 6º (minimização).
4. **Fechar o ciclo.** Feedback sem uso vira ruído.
5. **Comparável.** Indicador precisa permitir comparação entre serviços e no tempo.
6. **Linguagem simples.** Documento voltado a decisor, não a especialista.

## Marcadores usados

- `[FATO]` — informação confirmada por fonte primária.
- `[INTERPRETAÇÃO]` — análise baseada em evidência.
- `[HIPÓTESE]` — proposição a validar.
- `[RECOMENDAÇÃO]` — sugestão do estudo.
- `**Não identificado**` — buscado, sem evidência conclusiva.
