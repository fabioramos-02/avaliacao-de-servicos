# 7. Recomendação

## A recomendação em uma linha

Adotar no Portal MS um **modelo de avaliação simples, voluntário e alinhado ao gov.br** (Portaria SGD/MGI nº 1.083/2025), com adaptação institucional mínima e piloto controlado antes da expansão.

## Por quê

1. **Padrão nacional.** A Portaria SGD/MGI nº 1.083/2025 (revisora da 548/2022) já formatou o instrumento para toda a Administração Federal. Divergir gera custo sem ganho.
2. **Comparabilidade.** MS entra no mesmo referencial dos demais entes que caminham para adesão ao modelo federal.
3. **Aderência legal.** Lei nº 13.460/2017 exige avaliação; LGPD exige minimização. O modelo gov.br já foi desenhado para atender ambos.
4. **Baixo risco técnico.** Formulário simples, sem integração complexa, sem coleta de dado novo do cidadão além do que já entra pelo login.
5. **Baixo atrito para o cidadão.** 1 pergunta obrigatória + 3 opcionais; ~5 segundos no mínimo, ~80 segundos no máximo.

## O que será adotado

- Pergunta: *"Como foi a sua experiência com o serviço?"*
- Escala: 5 estrelas rotuladas — Péssima / Ruim / Mais ou menos / Boa / Excelente.
- 3 blocos opcionais: motivos positivos (6 cards, até 3) + comentário aberto (2000 caracteres) + autodeclaração PcD.
- Momento: convite único ao concluir o serviço. **Nunca bloqueia.**
- Identificação: cidadão logado no Portal MS. Registram-se `id_usuario` e município do serviço finalístico. **Nenhum campo novo de identificação no formulário.**
- Indicador principal: nota média (1–5) + % Satisfeitos (notas 4 e 5).
- Meta orientativa: nota média ≥ 4,0 e % Satisfeitos ≥ 80%.

Detalhamento completo em [Modelo proposto](03-modelo-proposto.md).

## O que NÃO será adotado (e por quê)

- **NPS como métrica principal.** Serviço público monopolista não tem lógica de recomendação — cidadão não escolhe o órgão.
- **Coleta de CPF, e-mail, telefone, nome ou endereço no formulário.** A identificação vem do login. Nada disso agrega uso operacional; tudo isso amplia risco LGPD.
- **Avaliação anônima.** Divergência consciente do gov.br federal — decisão SGD 2026-08-25. A identificação vem do login já existente, permite retorno ao cidadão e análise por perfil/localização. Base LGPD: execução de política pública.
- **Bloqueio da conclusão do serviço em avaliação.** Vedado por lei (art. 7º, §3º da Portaria SGD/ME nº 548/2022).
- **Avaliação como canal de reclamação com resposta individual.** Esse é o papel da Ouvidoria Estadual.
- **Expansão em escala sem piloto.** O piloto de 4 semanas é pré-requisito para calibrar taxa de resposta e revelar problemas de fluxo.

## Condições

A implantação depende de:

1. **Escopo restrito a serviços que nascem no orquestrador X-VIA** — decisão SGD 2026-08-25.
2. **Encarregado (DPO) estadual identificado e publicado** antes do go-live. Hoje **não identificado** publicamente — bloqueio crítico.
3. **Ato normativo estadual** instituindo o Modelo de Qualidade dos Serviços Digitais do MS, com previsão expressa da coleta identificada.
4. **RIPD (Relatório de Impacto à Proteção de Dados)** elaborado e aprovado pelo DPO antes do go-live.
5. **Definição técnica do sinal de conclusão** que o sistema do órgão finalístico envia ao X-VIA — pré-requisito para o disparo do e-mail transacional com link único.
6. **Piloto de 4 semanas** em serviço de alta demanda com todos os critérios de aceite atendidos.

## Riscos e mitigações

| Risco | Impacto | Mitigação |
|---|---|---|
| Baixa taxa de resposta | Dado pouco representativo | Convite discreto mas visível; mensuração no piloto |
| Comentários abertos usados como canal de manifestação sem retorno | Cidadão frustrado | Aviso claro + orientação ao canal formal (Ouvidoria) |
| Divergência entre painel MS e painéis federais | Confusão de indicadores | Publicar mesma fórmula e escala do gov.br |
| Mudança na Portaria federal | Precisa acompanhar | Monitorar publicações SGD/MGI trimestralmente |
| Órgão setorial não usa o painel | Avaliação vira ruído | Comitê mensal por Secretaria; acesso obrigatório do gestor |
| Uso indevido do e-mail transacional | Ampliação de risco LGPD | Canal técnico separado, opt-out específico, template fechado, auditoria de disparo |

## Alternativas consideradas

Comparação estruturada entre alternativas. Notas de 1 (ruim) a 5 (excelente) por critério.

**Alternativas avaliadas:**

- **A** — Modelo gov.br idêntico.
- **B** — Modelo gov.br + adaptação MS leve (idêntico ao A + cabeçalho institucional MS + painel próprio).
- **C** — Modelo próprio (CSAT + CES + comentário aberto).
- **D** — Modelo enxuto (só estrelas, sem qualificadores, sem comentário).

**Critérios e pesos:**

| Critério | Peso | Justificativa |
|---|---|---|
| Simplicidade para o cidadão | 4 | Determinante da taxa de resposta |
| Taxa de resposta esperada | 4 | Sem resposta, não há dado |
| Qualidade do dado gerado | 4 | Sem dado útil, não há decisão |
| Capacidade analítica | 3 | Habilita gestão baseada em evidência |
| Aderência à LGPD | 5 | Não negociável — risco jurídico |
| Custo operacional | 3 | Manutenção, moderação, painel |
| Aplicabilidade a serviço público | 4 | Referências privadas nem sempre servem |
| Compatibilidade com gov.br | 5 | Comparabilidade nacional |
| Acessibilidade | 4 | Público heterogêneo, PcD |

**Resultado:**

| Critério (peso) | A (idêntico) | B (adaptado) | C (próprio) | D (enxuto) |
|---|---|---|---|---|
| Simplicidade (4) | 5 | 5 | 3 | 5 |
| Taxa de resposta (4) | 4 | 4 | 3 | 5 |
| Qualidade do dado (4) | 4 | 5 | 4 | 2 |
| Capacidade analítica (3) | 4 | 5 | 4 | 2 |
| Aderência LGPD (5) | 5 | 5 | 4 | 5 |
| Custo operacional (3) | 4 | 4 | 2 | 5 |
| Aplicabilidade a serviço público (4) | 5 | 5 | 3 | 3 |
| Compatibilidade gov.br (5) | 5 | 5 | 2 | 3 |
| Acessibilidade (4) | 5 | 5 | 4 | 4 |
| **Nota ponderada** | **158** | **163** | **117** | **131** |

**Leitura:**

- **B vence** por combinar aderência total ao padrão gov.br com adaptação institucional mínima (cabeçalho MS, painel próprio, integração com o catálogo de serviços do Portal).
- **A** é praticamente empatado; a diferença é que ter painel próprio permite ler o dado por município, canal e etapa — o painel federal genérico não oferece isso ao estado.
- **C (próprio)** perde pesado em compatibilidade e aplicabilidade a serviço público. Só faria sentido se o Estado tivesse hipótese específica que o gov.br não cobre — não é o caso.
- **D (enxuto)** parece atraente pela simplicidade, mas mata a capacidade analítica: sem qualificadores, o gestor sabe que o serviço é ruim mas não sabe por quê.

**Recomendação:** alternativa **B — Modelo gov.br + adaptação MS leve**.

Após a decisão SGD 2026-08-25 (avaliação identificada), a nota de "Compatibilidade gov.br" cai de 5 → 4 (a divergência é justificada e documentada, mas existe). A nota ponderada de B fica em **158**, mantendo a alternativa como vencedora.

## Registro de decisões

Cada linha responde: **o que foi decidido, quando, por quem, com base em quê**.

| # | Data | Decisão | Quem decidiu | Base |
|---|---|---|---|---|
| D1 | 2026-08-18 | Adotar gov.br como referência principal | Chefia SGD | Portaria SGD/MGI nº 1.083/2025 é padrão nacional |
| D2 | 2026-08-18 | Manter linguagem institucional, simples, sem jargão de projeto | Chefia SGD | Público-alvo é diretoria e gestão sênior |
| D3 | 2026-08-18 | Escala 5 estrelas rotuladas (não NPS, não emojis) | Estudo | Aderência gov.br + comparabilidade nacional |
| D4 | 2026-08-18 | Anônimo por default; sem CPF, e-mail ou nome | Estudo | LGPD art. 6º, III + prática gov.br |
| D5 | 2026-08-18 | Indicador principal: nota média + % Satisfeitos | Estudo | Duplo indicador cobre cidadão e gestor |
| D6 | 2026-08-18 | Recomendação: alternativa B (gov.br + adaptação MS leve) | Estudo | Nota 163/195 na comparação |
| D7 | 2026-08-18 | Convite único, nunca bloquear | Estudo | Portaria SGD/ME nº 548/2022 art. 7º §3º |
| D8 | 2026-08-18 | Retenção: 5 anos bruto, 3 anos dado sensível PcD | Estudo | LGPD art. 6º III + proporcionalidade |
| D9 | 2026-08-18 | Piloto de 3 meses antes de escalar | Estudo | Reduz risco + gera dado para calibração |
| **D10** | **2026-08-25** | **Revoga D4.** Avaliação passa a ser **identificada** (usuário logado + município do serviço finalístico). Base LGPD: execução de política pública (art. 7º III + art. 11 II "b"), não mais anonimato | SGD | Permite retorno ao cidadão, análise por perfil/localização e integração com histórico do Portal |
| **D11** | **2026-08-25** | Escopo restrito a **serviços que nascem no orquestrador X-VIA**. Serviços fora ficam de fora nesta onda | SGD | Sem orquestrador não há sinal confiável de conclusão do serviço |
| **D12** | **2026-08-25** | Ajuste de retenção: 24 meses no estado identificado, 12 meses no comentário aberto, pseudonimização em agregado histórico. Revoga D8 | SGD | Combina exercício de direitos do titular, análise anual e redução de risco |

### Decisões pendentes — a tomar na validação

| # | Decisão | Quem decide | Prazo |
|---|---|---|---|
| P1 | Adotar formalmente o modelo | Secretário Executivo SETDIG | 2 semanas |
| P2 | Escolher serviço piloto (entre os que nascem no X-VIA) | SGD + órgão setorial | 4 semanas |
| P3 | Aprovar texto do aviso LGPD + validar RIPD | Jurídico + DPO | 2 semanas |
| P4 | Definir Secretaria responsável pelo painel gestor | SETDIG | 4 semanas |
| P5 | Definir se integração futura com API gov.br entra em fase 2 | Direção SETDIG | Após o piloto |
| P6 | Definir cadência de publicação em `dados.ms.gov.br` (somente agregado) | SETDIG + área de dados abertos estadual | Após o piloto |
| P7 | **Reunião técnica:** entender como o sistema do órgão sinaliza ao X-VIA que o serviço foi concluído. Bloqueia a proposta prévia de retorno por e-mail | SGD + X-VIA | Imediato |
| P8 | Definir caminho de retorno: e-mail com link único (proposta prévia) | SGD | Após P7 |
| P9 | Publicar ato normativo estadual instituindo o Modelo de Qualidade dos Serviços Digitais do MS com previsão da coleta identificada | SETDIG + PGE-MS | Antes do go-live |
| P10 | Publicar contato do DPO estadual (bloqueio para o aviso de privacidade) | SETDIG + PGE-MS | Antes do go-live |

## Próximos passos

### Fase 1 — Validação (semanas 1 a 13)

Cronograma completo em [6. Validação](06-validacao.md).

### Fase 2 — Escala (mês 4 em diante)

- Expandir para 5 novos serviços por mês.
- Reunião mensal de qualidade por Secretaria.
- Publicar primeiros indicadores agregados em portal público.
- Iniciar conversa com SGD/MGI sobre eventual integração com API federal.

### Fase 3 — Maturidade (ano 2)

- Publicação sistemática em `dados.ms.gov.br` (agregado mensal).
- Série histórica de 12 meses disponível.
- Ranking público de serviços com meta atingida.
- Estudo de correlação avaliação × indicadores de uso.

## Recomendações complementares (fora do escopo deste estudo)

Sugestões que **não** são deste estudo, mas o time da SETDIG deveria considerar:

1. **Pesquisa qualitativa com cidadãos** antes de escalar — grupo focal com 15–20 usuários no serviço piloto. Custo baixo, retorno alto.
2. **Auditoria de acessibilidade externa (WCAG 2.1 AA)** antes de escalar.
3. **Manual do gestor** — 4 páginas ensinando como ler o painel e agir sobre os dados.
4. **Programa de reconhecimento** — publicar semestralmente os "10 serviços mais bem avaliados do MS".
5. **Integração com Ouvidoria Estadual** — cidadão com nota 1 ou 2 recebe convite discreto para registrar manifestação formal se desejar.
6. **Governança do catálogo de serviços** — `id_servico` da avaliação precisa ser o mesmo do catálogo unificado; sem isso, os dados não conversam.

## Sinais de que a decisão foi acertada

- Em 6 meses: ≥ 10 serviços com avaliação ativa; taxa de resposta ≥ 5%.
- Em 12 meses: nota média do Portal ≥ 4,0; ranking público disponível.
- Em 18 meses: ao menos um caso documentado de melhoria de serviço motivada pela avaliação.
- Em 24 meses: MS entre os estados de referência em governo digital no Brasil.

## Sinais de que a decisão precisa ser revista

- Taxa de resposta < 2% em 6 meses.
- Painéis não são utilizados pelos gestores.
- Ouvidoria reporta que comentários abertos criaram carga sem retorno.
- Incidente de LGPD relacionado à avaliação.

## Referências

- [Contexto](01-contexto.md)
- [Referência adotada](02-referencia.md)
- [Modelo proposto](03-modelo-proposto.md)
- [Dados e privacidade](04-dados-e-privacidade.md)
- [Indicadores](05-indicadores.md)
- [Validação](06-validacao.md)
