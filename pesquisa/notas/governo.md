# Notas de Pesquisa — Governos Digitais

Agente 3. Investigação de como plataformas de governo digital coletam avaliação de cidadãos.
Marcadores: `[FATO]` (fonte oficial), `[INTERPRETAÇÃO]` (leitura minha), `[HIPÓTESE]` (a validar).

---

## 1. GOV.UK (Reino Unido) — GDS

1. **Existe avaliação?** `[FATO]` Sim. Modelo descentralizado: cada serviço transacional é obrigado pelo *Service Standard* a medir satisfação continuamente; adicionalmente o próprio site `gov.uk` tem widget de feedback universal em toda página ("Is this page useful? Yes / No"). Fonte: GOV.UK Service Manual.
2. **Momento** — `[FATO]` "At various stages" do fluxo, e ao final. GOV.UK Pay p.ex. envia survey por e-mail a usuários que logaram nos últimos 12 meses.
3. **Perguntas** — `[FATO]` Não há template obrigatório: "There is no formal guidance on what questions you must ask" (Service Manual). Recomendação: incluir pelo menos **uma pergunta aberta sobre como melhorar o serviço**. Widget do site: "Is this page useful?" → Sim/Não → se "Não", campo aberto "How can we improve this page?".
4. **Escala** — `[FATO]` GOV.UK Pay usa **escala Likert** (não especificado quantos pontos no post do blog). Publicações padronizadas usam escala de satisfação 1–5 ("very dissatisfied"→"very satisfied") herdada do *Digital Service Standard*. `[INTERPRETAÇÃO]` Não há um "modelo GOV.UK único" — a orientação é continuous measurement, não uma escala única.
5. **Campo aberto** — `[FATO]` Sim, obrigatório pelo Service Manual ("open-ended question about how to improve the service").
6. **Dados sensíveis** — `[FATO]` Widget do site é anônimo. Surveys específicos (GOV.UK Pay, Notify) enviam para usuários já autenticados no serviço; feedback trata dado profissional, não pessoal sensível.
7. **Publicação** — `[FATO]` Service Standard exige publicar satisfação **"at least once a month"** enquanto serviço está live. Dados agregados vão para `data.gov.uk` ("User Satisfaction survey" dataset).
8. **Uso pela gestão** — `[FATO]` GOV.UK Pay descreve pipeline: satisfação + tickets de suporte + user research + analytics → roadmap. Ex: 50% dos respondentes 2022 pediram pay-by-bank → time abriu discovery.
9. **Base legal / política** — `[FATO]` Sem lei específica; obrigação vem do *Service Standard* (política interna do governo) e do Data Protection Act 2018 / UK GDPR para PII.
10. **Métrica agregada** — `[FATO]` GDS publica performance data por serviço. Não há "nota GOV.UK única" — cada serviço tem sua métrica.

**Fontes:**
- https://www.gov.uk/service-manual/measuring-success/measuring-user-satisfaction
- https://gds.blog.gov.uk/2024/01/29/how-we-are-improving-gov-uk-pay-with-user-satisfaction-feedback/
- https://gds.blog.gov.uk/2022/11/09/understanding-user-satisfaction-on-gov-uk-notify
- https://www.data.gov.uk/dataset/63e35a14-492b-4577-89e5-a03c5c365c00/user-satisfaction-survey
- https://gds.blog.gov.uk/tag/user-satisfaction

---

## 2. gov.br (Brasil) — Ministério da Gestão / SGD

1. **Existe avaliação?** `[FATO]` Sim. Universal por serviço: cada serviço digital publicado em `gov.br/pt-br/servicos` tem componente de avaliação no topo da página. Também há `avaliacao.servicos.gov.br` como plataforma central.
2. **Momento** — `[FATO]` Ao concluir o serviço digital, o cidadão é convidado a avaliar via link gerado pelo órgão (via API) ou pelo widget na página do serviço.
3. **Perguntas** — `[FATO]` (a) Nota geral 1–5 estrelas. (b) Escolha de 3 entre 6 critérios/dimensões (facilidade, comunicação, atendimento, experiência unificada, acessibilidade, escuta ativa — o site menciona 7 dimensões de qualidade mas apresenta 6 opções ao cidadão). `[HIPÓTESE]` Existe campo de comentário livre, mas documentação oficial não confirma explicitamente que ele é exibido no fluxo padrão.
4. **Escala** — `[FATO]` **1 a 5**, texto ancorado: 1=péssimo, 2=ruim, 3=satisfatório, 4=bom, 5=excelente. Representação visual: estrelas.
5. **Campo aberto** — `[HIPÓTESE]` API aceita campo `descricao`; UI padrão apresenta seleção de critérios. Confirmar em teste real.
6. **Dados sensíveis** — `[FATO]` "Plataforma projetada para receber avaliações anônimas". CPF **não é obrigatório**. API não exige identificação. Consulta por CPF existe (endpoint `porCidadao`) mas é opcional.
7. **Publicação** — `[FATO]` Sim. Nota agregada aparece na **página de cada serviço no Portal GOV.BR** (média + nº de avaliações), no **Painel de Monitoramento** e no **Ranking de Serviços**. Detalhamento por gestor fica no Painel de Gestão da Qualidade (restrito).
8. **Uso pela gestão** — `[FATO]` Ferramenta é do LabQ (Laboratório de Qualidade dos Serviços Públicos). Serve para diagnóstico e plano de melhoria. Portaria SGD/ME 548/2022 institui o Modelo de Qualidade dos Serviços Públicos que operacionaliza esse uso.
9. **Base legal** — `[FATO]` Lei 13.460/2017 (Código de Defesa do Usuário de Serviços Públicos), art. 23 — obrigatoriedade de pesquisa de satisfação anual. Decreto 9.094/2017 — Carta de Serviços ao Usuário e ferramenta de pesquisa de satisfação. Portaria SGD/ME 548/2022 — Modelo de Qualidade. LGPD (13.709/2018) — dados pessoais.
10. **Métrica agregada** — `[FATO]` Sim, gov.br publica média de estrelas por serviço e ranking geral. Não encontrei um índice único federal do tipo "nota gov.br" divulgado ao público geral, mas o Painel de Monitoramento existe.

**Fontes:**
- https://avaliacao.servicos.gov.br/
- https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao
- https://www.gov.br/governodigital/pt-br/estrategias-e-governanca-digital/transformacao-digital/ferramentas/modelo-de-qualidade-dos-servicos-digitais/avaliacao-de-satisfacao-dos-usuarios
- https://manual-avaliacao.servicos.gov.br/pt-br/latest/faq.html
- https://www.gov.br/gestao/pt-br/assuntos/noticias/2024/abril/gestao-lanca-nova-ferramenta-de-avaliacao-dos-servicos-publicos-no-gov.br
- Lei 13.460/2017 (texto oficial): https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/lei/l13460.htm
- Decreto 9.094/2017: https://www2.camara.leg.br/legin/fed/decret/2017/decreto-9094-17-julho-2017-785213-normaatualizada-pe.html

---

## 3. Rio Grande do Sul — rs.gov.br

1. **Existe avaliação?** `[FATO]` Sim. Portal RS.GOV.BR tem página dedicada `rs.gov.br/satisfacao` e componente de avaliação em serviços.
2. **Momento** — `[HIPÓTESE]` Ao concluir serviço digital (padrão gov.br replicado).
3. **Perguntas / Escala** — `[FATO]` Escala qualitativa com categorias "Muito Satisfeito / Satisfeito / ..." (formato exato não confirmado). 89% dos usuários em Muito Satisfeitos + Satisfeitos (dez/2025).
4. **Publicação** — `[FATO]` Métrica agregada divulgada no portal; regulamentação da "Avaliação Continuada dos Serviços Públicos Estaduais Digitais" publicada por decreto estadual.
5. **Base legal** — `[FATO]` Alinhada à Lei 13.460/2017; regulamento estadual próprio publicado.
6. **Uso pela gestão** — `[FATO]` Avalia satisfação, qualidade do atendimento, cumprimento de prazos, quantidade de manifestações, medidas adotadas para melhoria (espelha art. 23 da Lei 13.460).

**Fontes:**
- https://www.rs.gov.br/satisfacao
- https://estado.rs.gov.br/executivo-estadual-publica-regramento-da-avaliacao-dos-servicos-digitais
- https://www.rs.gov.br/conheca-o-rs-gov-br

---

## 4. São Paulo — sp.gov.br / Fala.SP

1. **Existe avaliação?** `[FATO]` Sim, via plataforma `fala.sp.gov.br`: cidadão avalia serviços, direciona e acompanha demandas.
2. **Momento** — `[FATO]` Após atendimento/manifestação junto às ouvidorias.
3. **Escala/perguntas** — `[HIPÓTESE]` Não confirmado texto exato — plataforma é sobretudo de manifestações (elogio/reclamação/sugestão/denúncia + LAI) com módulo de avaliação de atendimento.
4. **Publicação** — `[HIPÓTESE]` Não confirmada divulgação pública de médias.
5. **Base legal** — `[FATO]` Lei 13.460/2017 + regulamentação estadual.

**Fontes:**
- https://fala.sp.gov.br/
- https://servicos.sp.gov.br/
- https://www.poupatempo.sp.gov.br/

---

## 5. USDS / 18F / digital.gov (EUA)

1. **Existe avaliação?** `[FATO]` Não há sistema único federal. Cada agência mede via seus canais; digital.gov mantém guias e "Customer Experience Cookbook".
2. **Abordagem** — `[FATO]` 18F questiona explicitamente uso isolado de CSAT: "surveys should not be created and analyzed in isolation". Recomenda triangulação com research qualitativa.
3. **Métricas** — `[FATO]` Foco em High Impact Service Providers (HISPs). ACSI (American Customer Satisfaction Index) mede satisfação com governo federal, mas ITIF aponta que muitas HISPs ainda não medem bem experiência digital.
4. **Base legal** — `[FATO]` Executive Order de 1993 sobre "Setting Customer Service Standards"; EO 14058/2021 (Biden) sobre Customer Experience; 21st Century IDEA Act.
5. **Uso pela gestão** — `[FATO]` Playbooks; HISPs precisam reportar CX metrics.

**Fontes:**
- https://digital.gov/topics/customer-experience
- https://18f.gsa.gov/2024/03/05/customer-experience-beyond-surveys/
- https://18f.gsa.gov/2016/09/15/gao-report-shows-satisfied-customers-areas-for-improvement/
- https://itif.org/publications/2022/10/24/federal-hisp-digital-customer-experience/

---

## 6. Service NSW (Austrália)

1. **Existe avaliação?** `[FATO]` Sim. NSW faz Customer Experience Survey desde dez/2021, mede facilidade, efetividade e confiança.
2. **Escala** — `[HIPÓTESE]` Não confirmado o formato exato. Reportam % de satisfeitos.
3. **Cobertura** — `[FATO]` 24.000 indivíduos + 6.000 empresas por ano; 550 transações; 37 serviços.
4. **Números** — `[FATO]` 97% de satisfação histórica reportada por Service NSW; 75% satisfeitos na CX Survey mais recente; 77% acham fácil interagir.
5. **Publicação** — `[FATO]` Relatórios anuais publicados em `nsw.gov.au`.
6. **Uso** — `[FATO]` Alimenta estratégia de Customer Experience do estado.

**Fontes:**
- https://www.nsw.gov.au/sites/default/files/2020-06/DCS-OCSC-2019-Annual-Customer-Satisfaction-Survey.pdf
- https://www.nsw.gov.au/sites/default/files/2021-09/2020-annual-customer-satisfaction-measurement-survey.pdf
- https://journal.govcx.org/case-study-new-south-wales-service/
- https://www.themandarin.com.au/202608-survey-shows-a-high-level-of-satisfaction-with-the-nsw-governments-services/

---

## 7. Estonia — e-Estonia

1. **Existe avaliação?** `[FATO]` Sim, via pesquisas periódicas (OECD 2024: 82% de estonianos satisfeitos com serviços públicos, especialmente digitais em eventos de vida).
2. **Modelo** — `[INTERPRETAÇÃO]` Baseia-se mais em pesquisas amostrais periódicas do que em avaliação por serviço na interface.
3. **Publicação** — `[FATO]` OECD e governo publicam resultados agregados.
4. **Métrica agregada** — `[FATO]` 82% (OECD 2024); 89% dos usuários de internet no país usam e-gov.

**Fontes:**
- https://e-estonia.com/estonia-among-the-best-countries-to-provide-digital-public-services-according-to-the-oecd/
- https://e-estonia.com/estonia-a-european-and-global-leader-in-the-digitalisation-of-public-services/

---

## 8. Singapore — GovTech / LifeSG

1. **Existe avaliação?** `[FATO]` Sim, via Annual Satisfaction Survey (Digital Government Perception Survey); ~1.500 respondentes/ano. Adicionalmente Tech Kaki (comunidade de co-criação, 6.000 membros) roda testes qualitativos.
2. **Escala/perguntas** — `[HIPÓTESE]` Não confirmado formato exato usado em LifeSG na interface.
3. **Métrica agregada** — `[FATO]` GovTech publica resultados anuais.

**Fontes:**
- https://www.tech.gov.sg/technews/public-sector-transformation-awards-2026-the-govtech-products-and-people-shaping-digital-government/
- https://www.tech.gov.sg/digital-government-perception-survey-citizen-2005
- https://www.tech.gov.sg/products-and-services/for-citizens/digital-services/lifesg/

---

## 9. Estados brasileiros — status resumido

| Estado | Portal | Tem avaliação? | Fonte |
|---|---|---|---|
| RS | rs.gov.br | `[FATO]` Sim, regulamentado | https://www.rs.gov.br/satisfacao |
| SP | servicos.sp.gov.br + fala.sp.gov.br | `[FATO]` Sim, via Fala.SP | https://fala.sp.gov.br/ |
| MG | mg.gov.br/cidadao | `[HIPÓTESE]` Portal existe; avaliação não confirmada explicitamente na busca | https://www.mg.gov.br/cidadao |
| PR | cidadao.pr.gov.br | **Não identificado** modelo próprio na busca | — |
| CE | ceara.gov.br | `[FATO]` CGE-CE publicou Manual de Avaliação dos Serviços Públicos (2021) | https://www.cge.ce.gov.br/wp-content/uploads/sites/20/2021/12/Manual-de-Avaliacao-de-Servicos-Publicos.pdf |

---

## 10. Marco legal brasileiro consolidado (para MS)

- **Lei 13.460/2017**, art. 23 — `[FATO]` obrigação de avaliar em 5 aspectos: satisfação, qualidade do atendimento, cumprimento de prazos, quantidade de manifestações, medidas de melhoria. Pesquisa "no mínimo a cada um ano" ou por outro meio com significância estatística. Resultado deve ser **integralmente publicado no sítio do órgão**, incluindo ranking de entidades com mais reclamações.
- **Decreto 9.094/2017** — `[FATO]` Carta de Serviços ao Usuário + obrigação de ferramenta de pesquisa de satisfação.
- **Lei 13.709/2018 (LGPD)** — `[FATO]` Art. 7º VII (execução de políticas públicas), Art. 11 (dados sensíveis exigem cuidado adicional), anonimização recomendada sempre que possível.
- **Portaria SGD/ME 548/2022** — `[FATO]` Modelo de Qualidade dos Serviços Públicos federais (referência técnica que MS pode adotar/adaptar).
