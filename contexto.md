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
| 1b | Benchmark mercado | iFood, Uber, Airbnb, Google, Amazon (referência secundária) | ✅ Concluída |
| 1c | Benchmark governo | GOV.UK, gov.br federal, USDS (contexto global) | ✅ Concluída |
| 1d | Deep dive gov.br | Central de Qualidade + Ferramenta de Avaliação (âncora) | ✅ Concluída |
| 2a | UX/Service Design | Momento ideal, tamanho de formulário, taxa de resposta | ✅ Concluída |
| 2b | Dados/Analytics | Indicadores, dimensões, estrutura BI | ✅ Concluída |
| 2c | LGPD/Governança | Base legal, minimização, retenção | ✅ Concluída |
| 3 | Proposta + Validação | Modelo para MS + matriz decisão + estratégia validação | ✅ Concluída |
| 4 | Empacotamento MkDocs | Build, revisão navegação, ajustes finais | ✅ Concluída |
| 5 | Especificação TO BE | Pacote de documentação para a Xvia (campos, regras, RBAC, pendências) | ✅ v1 escrita, aguardando validação |

---

## Onde paramos

**Estudo concluído. Especificação TO BE v1 escrita.** Todas as ondas finalizadas. `mkdocs build --strict` passa (0 warnings). CI GitHub Pages configurado em `.github/workflows/gh-pages.yml`.

**Entregas prontas para validação:**

- Recomendação final em `docs/07-conclusao/recomendacao.md`.
- Modelo proposto em `docs/05-proposta/modelo-proposto.md`.
- Matriz de decisão em `docs/05-proposta/matriz-decisao.md`.
- Estratégia de validação em `docs/06-validacao/estrategia.md`.
- Corte LGPD em `docs/04-cidadao/lgpd.md`.
- Documentação navegável rodando com tema SEGOV.
- **Especificação TO BE** em `docs/08-to-be/avaliacao-de-servico-to-be.md` — pacote para a Xvia, no formato dos pacotes já aceitos pelo fornecedor (*Carta de Serviço — TO BE v5*).

### Direcionamento da gestão (ago/2026)

- O MS opera **instrumento próprio** de avaliação, hospedado no Portal Único — não integração com a ferramenta federal.
- Os dados serão **cedidos ao gov.br via API quando necessário**. Escopo de documento separado, fora do pacote TO BE atual.
- As métricas devem **apoiar o contrato de gestão do Governo do Estado** — indicadores propostos na Seção 7.4 do TO BE, pendentes de pactuação formal.

**Próximos passos (fora deste estudo):**

1. Levar recomendação para deliberação da diretoria SETDIG.
2. Escolher serviço piloto conforme critérios em `docs/06-validacao/estrategia.md`.
3. Parecer jurídico e alocação de time técnico.
4. Piloto de 3 meses.
5. Go/no-go pós-piloto.

**Melhorias futuras da documentação (opcional):**

- Gerar apresentação PPTX executiva sobre os docs consolidados.
- Publicar site em GitHub Pages (workflow já pronto, basta push).
- Pesquisa qualitativa com cidadão antes de escala.

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
