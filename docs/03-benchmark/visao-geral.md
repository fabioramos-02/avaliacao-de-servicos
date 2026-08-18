# Benchmark — Visão geral

## Referência primária: gov.br

Por decisão da chefia da equipe, **o gov.br é a referência principal deste estudo**. Todo o desenho da avaliação do Portal MS parte do modelo federal — pergunta, escala, cards, campo aberto, bloco de acessibilidade — e só se distancia dele quando houver razão explícita.

Três documentos concentram o estudo do modelo federal:

| Documento | Foco |
|---|---|
| [gov-br.md](./gov-br.md) | Visão consolidada do modelo (pergunta, escala, cards, PCD, base legal, aplicabilidade ao MS) |
| [central-de-qualidade.md](./central-de-qualidade.md) | Guarda-chuva estratégico: pilares, 7 dimensões, governança, ciclo de melhoria |
| [ferramenta-de-avaliacao.md](./ferramenta-de-avaliacao.md) | Peça operacional: formulário do cidadão, API, painel do gestor, cálculo |

`[FATO]` O modelo gov.br está operando em escala real: **1.047 serviços integrados, nota média 4,39/5** (dados publicados pela Central de Qualidade na data de acesso).

## Referências secundárias — cases de mercado

Cases privados foram estudados para calibrar boas práticas de UX, momento de coleta, uso do feedback e prevenção de vieses. **Não substituem o gov.br** — servem como fonte de padrões consolidados na indústria digital.

| Case | Contexto | Documento |
|------|----------|-----------|
| iFood | Delivery de comida (BR) | [ifood.md](./ifood.md) |
| Uber | Mobilidade urbana (global) | [uber.md](./uber.md) |
| Airbnb | Hospedagem entre pessoas (global) | [airbnb.md](./airbnb.md) |
| Google Play | Loja de apps Android (in-app review) | [google.md](./google.md) |
| Amazon | E-commerce (produto + vendedor) | [amazon.md](./amazon.md) |
| GOV.UK | Governo digital do Reino Unido | [gov-uk.md](./gov-uk.md) |

Comparativo tabular consolidado: [comparativo.md](./comparativo.md).

## O que os cases de mercado ensinam (destaque rápido)

1. **Escala visual simples** — todos convergem em 1–5 estrelas como métrica principal. Reforça a escolha do gov.br.
2. **Momento ancorado no evento** — Uber pede após viagem, iFood após pedido, Airbnb após check-out, gov.br pede após uso do serviço. Padrão consolidado.
3. **Campo aberto sempre opcional** — nenhum força comentário livre. gov.br segue o mesmo princípio.
4. **Skip permitido** — só o Uber trava (e é criticado por isso). Serviço público **jamais** deveria bloquear jornada por avaliação — princípio confirmado no Art. 7º §3º da Portaria SGD/ME 548/2022.
5. **Comunicar o que muda com o feedback** — cases sem retorno visível têm queda de participação. Vale para o Portal MS.
6. **Moderação obrigatória** — iFood e Amazon investem em ML + humano. MS precisa de política mínima antes de ir ao ar.
7. **Anti-viés** — Google Play proíbe pré-screening ("Está gostando?"); é boa prática a preservar.

Detalhamento completo de cada case nos respectivos arquivos.

## O que o gov.br tem que os cases privados não têm

`[INTERPRETAÇÃO]` Três diferenciais estruturais do modelo federal, essenciais para serviço público:

- **Bloco de acessibilidade** (PCD). Nenhum case privado analisado coleta essa informação.
- **Base legal explícita** (Lei 13.460, Decreto 9.094, Portaria SGD/MGI 1083/2025). Ancora o formulário em política pública, não em métrica de negócio.
- **Anonimato por default**. Cases privados operam com conta identificada; o gov.br assume avaliação anônima para reduzir atrito e aderir à LGPD.

## Fontes

Consolidado em [../pesquisa/fontes.md](../pesquisa/fontes.md).
