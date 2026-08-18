# Benchmark — GOV.UK (Reino Unido)

> Fonte principal: GOV.UK Service Manual, GDS Blog. Todas as observações marcadas `[FATO]`/`[INTERPRETAÇÃO]`/`[HIPÓTESE]`.

## Contexto da plataforma

GOV.UK é o portal único de serviços públicos do Reino Unido, operado pelo **Government Digital Service (GDS)**. Modelo consolidado desde 2012, referência mundial em governo digital. Coexistem no ecossistema:

- **gov.uk** — portal informacional único.
- **Serviços transacionais** — cada agência entrega seu serviço seguindo o *Service Standard* comum.
- **Plataformas comuns** — GOV.UK Pay, GOV.UK Notify, GOV.UK One Login.

## Modelo de avaliação

`[FATO]` **Descentralizado com padrões comuns**. Não há um "botão único gov.uk de nota 1–5". O GDS define o **Digital Service Standard**, que obriga cada equipe a:

- Medir satisfação **continuamente** enquanto o serviço está no ar.
- Publicar dados **pelo menos uma vez por mês**.
- Coletar feedback em **múltiplos endpoints** (formulário no site, e-mail pós-serviço, tickets de suporte, redes sociais, entrevistas).

`[FATO]` Adicionalmente, cada página do `gov.uk` tem um widget universal:

> "Is this page useful?" → **Yes / No** → se "No", campo aberto "How can we improve this page?"

## Perguntas, escala e momento

`[FATO]` **Sem template obrigatório**: "There is no formal guidance on what questions you must ask" (Service Manual). O GDS orienta que cada serviço:

- Inclua **pelo menos uma pergunta aberta** sobre como melhorar o serviço.
- Meça satisfação em escala Likert (comumente **5 pontos**, "very dissatisfied" → "very satisfied").
- Colete feedback em **vários pontos do fluxo**, não só no final.

`[FATO]` **Exemplo GOV.UK Pay (2024)**: envia survey por e-mail a usuários que logaram ≥1 vez nos últimos 12 meses. Escala Likert por feature. Amostra 2023: 3.444 destinatários (apenas usuários profissionais do serviço, não cidadãos finais).

`[FATO]` **Exemplo GOV.UK Notify (2022)**: também usa survey Likert com foco em feature-level satisfaction.

## Uso pela gestão

`[FATO]` GDS descreve pipeline replicável:

1. Coleta multi-canal (survey + suporte + user research + analytics).
2. Triangulação — nenhum canal isolado decide roadmap.
3. Priorização de melhorias no roadmap do serviço.
4. **Exemplo concreto**: 50% dos respondentes da survey GOV.UK Pay 2022 pediram *pay-by-bank* → equipe abriu descoberta técnica em 2023.

`[FATO]` Dados agregados são publicados em `data.gov.uk` como dataset "User Satisfaction survey".

## Base legal

`[FATO]` Não há lei específica do parlamento sobre pesquisa de satisfação. As obrigações vêm de:

- **Digital Service Standard** — política interna do governo, condição para serviços passarem por *service assessment* e serem publicados no gov.uk.
- **Data Protection Act 2018 + UK GDPR** — para tratamento de dados pessoais coletados.

## Aprendizados aplicáveis ao MS

1. **Widget universal de 1 pergunta + campo aberto condicional** (modelo "Is this page useful?") é barato, ubíquo e escalável — reduz atrito, permite ler tendências agregadas por página.
2. **Padronizar `Service Standard` local** — obrigação de medir + publicar mensalmente cria disciplina sem impor formato único que engessa todos os serviços.
3. **Triangular fontes** — CSAT sozinho engana. Combinar com dados de suporte/ouvidoria (Fala.MS?) + analytics.
4. **Publicação em `dados.ms.gov.br`** — expor dataset de satisfação como dado aberto, replicando `data.gov.uk`, aumenta accountability e permite reuso.
5. **Pergunta aberta sempre presente** — é o item mais defendido pelo Service Manual e o mais barato de implementar.
6. **Não pedir identificação** por padrão — GOV.UK Pay só faz survey identificado porque destinatários já são usuários autenticados profissionais; feedback do site é anônimo.

## Fontes

- GOV.UK Service Manual — Measuring user satisfaction: https://www.gov.uk/service-manual/measuring-success/measuring-user-satisfaction
- GDS Blog — Improving GOV.UK Pay with satisfaction feedback (2024): https://gds.blog.gov.uk/2024/01/29/how-we-are-improving-gov-uk-pay-with-user-satisfaction-feedback/
- GDS Blog — Understanding user satisfaction on GOV.UK Notify (2022): https://gds.blog.gov.uk/2022/11/09/understanding-user-satisfaction-on-gov-uk-notify
- data.gov.uk — User Satisfaction survey dataset: https://www.data.gov.uk/dataset/63e35a14-492b-4577-89e5-a03c5c365c00/user-satisfaction-survey
- GDS Blog — tag user-satisfaction: https://gds.blog.gov.uk/tag/user-satisfaction
