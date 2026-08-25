# LGPD e governança do dado da avaliação

> Este documento fixa o corte de LGPD e governança do dado do instrumento de avaliação do Portal de Serviços do MS. Ele complementa — não substitui — a Política de Privacidade geral do Governo do Estado. Referência âncora: gov.br (Central de Qualidade + Ferramenta de Avaliação).

> **Atualização 2026-08-25 (decisão SGD).** Duas mudanças de escopo alteram o desenho anterior deste documento:
>
> 1. **Escopo:** o instrumento vale apenas para serviços que nascem no **orquestrador X-VIA**. Serviços legados fora do orquestrador ficam de fora desta onda.
> 2. **Identificação:** a avaliação **deixa de ser anônima**. O cidadão já está logado no Portal MS (via conta gov.br) para acessar o serviço via X-VIA — a avaliação usa a mesma sessão e registra id do usuário e município do serviço finalístico. Nenhum campo novo de identificação é pedido no formulário.
>
> Consequência jurídica: a base LGPD deixa de se apoiar em anonimato e passa a se apoiar em **execução de política pública** (art. 7º III + art. 11 II "b" para dado sensível) + **finalidade específica declarada**. Isso é o que este documento sustenta, seção a seção. Onde havia argumento centrado em anonimato, foi substituído por argumento centrado em base legal, finalidade e minimização.

---

## 1. Enquadramento legal

`[FATO]` Duas leis se sobrepõem no instrumento:

- **Lei 13.460/2017 — Código de Defesa do Usuário de Serviços Públicos.** Art. 23 obriga órgãos e entidades a avaliar continuamente a satisfação do usuário, a qualidade do atendimento, o cumprimento de prazos, a quantidade de manifestações e as medidas adotadas. O resultado deve ser publicado no sítio do órgão. Fonte: [Lei 13.460/2017 — Planalto](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/lei/l13460.htm).
- **Lei 13.709/2018 — LGPD.** Rege o tratamento de todo dado pessoal, inclusive quando coletado pelo Poder Público em execução de política pública. Fonte: [Lei 13.709/2018 — Planalto](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm).

`[INTERPRETAÇÃO]` A Lei 13.460 é a **causa** da avaliação (obriga a coletar); a LGPD é o **limite** (define como e o quê pode ser coletado). O instrumento nasce, portanto, obrigatório por lei e minimalista por lei — o que reforça o desenho enxuto do gov.br.

---

## 2. Base legal para tratamento

`[RECOMENDAÇÃO]` Adotar **duas bases legais convivendo**, cada uma para um tipo de dado:

| Bloco do formulário | Base legal LGPD | Fundamento |
|---|---|---|
| Nota (estrelas) + motivos positivos (cards) | Art. 7º, III — execução de política pública | Cumpre obrigação legal da Lei 13.460/2017 art. 23 |
| Campo aberto (comentário) | Art. 7º, III — execução de política pública | Mesmo fundamento; texto voluntário fornecido no ato |
| Bloco de acessibilidade (autodeclaração PcD) | Art. 11, II, "b" — execução de política pública para dado sensível | Deficiência é **dado pessoal sensível** (art. 5º II); requer base específica |
| id_usuario (do IdP gov.br/Portal) + município do serviço finalístico | Art. 7º, III — execução de política pública | Identificação vem do login já existente; município vem do orquestrador X-VIA. Usados para (a) prevenir duplicidade, (b) permitir retorno ao cidadão via e-mail, (c) análise por perfil/localização. |
| Metadados técnicos (timestamp, id_execucao_orquestrador) | Art. 7º, III + art. 16, II | Necessários para operação, agregação temporal e prevenção de duplicidade |

`[RECOMENDAÇÃO]` **Evitar consentimento (art. 7º I)** como base primária. Em serviço público, "consentimento" cobrado como pré-condição de avaliar é frágil juridicamente (não é livre nem informado no sentido pleno da lei) e mistura duas relações — a de acesso ao serviço e a de melhoria do serviço. A execução de política pública cobre exatamente esse caso.

`[RECOMENDAÇÃO]` **Não usar legítimo interesse (art. 7º IX)**. A ANPD desestimula seu uso pelo Poder Público quando há hipótese específica disponível (execução de política pública cobre o caso).

`[INTERPRETAÇÃO]` Por que **não anonimato** (mudança 2026-08-25). O modelo anterior sustentava o instrumento em anonimato por design. A SGD decidiu identificar a avaliação porque (a) o orquestrador X-VIA já garante que o cidadão está logado, então "não identificar" seria descartar informação já disponível; (b) sem identificação não é possível fechar o ciclo com o cidadão (por exemplo, disparo de e-mail com link único de avaliação após conclusão do serviço no sistema do órgão); (c) sem localização não é possível ver diferenças regionais que orientem decisão de política pública. A troca é legítima desde que a base legal correta seja declarada (execução de política pública) e a minimização e a finalidade específica sejam mantidas — o que este documento faz.

---

## 3. Princípio da minimização aplicado ao instrumento

`[FATO]` LGPD art. 6º III: "limitação ao mínimo necessário para a realização de suas finalidades".

`[RECOMENDAÇÃO]` Traduzir a minimização em quatro regras práticas para o formulário:

1. **Toda pergunta precisa justificar seu próprio uso.** Se um dado não vai virar decisão, indicador ou retorno ao cidadão, ele não entra.
2. **Opcionalidade por default nas perguntas de conteúdo.** Único campo obrigatório: a nota. Motivos, comentário e acessibilidade são opcionais.
3. **Nenhum campo novo de identificação no formulário.** A identificação vem do login já existente no Portal MS (via IdP gov.br) — não se pede CPF, nome, telefone, e-mail nem endereço no ato da avaliação. Isso preserva minimização mesmo com avaliação identificada.
4. **Município do serviço vem do X-VIA, não do cidadão.** O município registrado é o do serviço finalístico (dado da operação), não a residência do cidadão (dado pessoal adicional).

---

## 4. Finalidade

`[RECOMENDAÇÃO]` Redigir a finalidade em uma frase única, replicável em todos os pontos de contato:

> "Coletar avaliações identificadas do cidadão logado no Portal MS sobre serviços digitais que nascem no orquestrador X-VIA, para diagnosticar qualidade, priorizar melhorias, viabilizar retorno ao próprio cidadão quando aplicável e cumprir o art. 23 da Lei 13.460/2017."

`[INTERPRETAÇÃO]` Finalidade específica (art. 6º I) blinda o dado contra desvio de uso posterior. Três consequências práticas:
1. Usar o comentário aberto para outra coisa (por exemplo, treinar modelo de IA de atendimento) exige nova finalidade e reavaliação — não está automaticamente autorizado.
2. Usar o id do usuário para marketing, ranking individual público ou perfil comercial está fora da finalidade — vedado.
3. Cruzar avaliação com outros dados do cidadão em outros serviços do Estado depende de finalidade explícita e proporcional — não é livre por padrão.

---

## 5. Dados que serão tratados

| Dado | Coletado? | Base legal | Retenção sugerida | Forma |
|---|---|---|---|---|
| Nota (1–5 estrelas) | Sim, obrigatório | Art. 7º III | Bruto: 24 meses. Agregado: indefinido | Numérica |
| Motivos positivos (até 3 cards) | Sim, opcional | Art. 7º III | Bruto: 24 meses. Agregado: indefinido | Categórica |
| Comentário aberto (até 2000 caracteres) | Sim, opcional | Art. 7º III | Bruto: 12 meses. Pseudonimizado pós-triagem: até 24 meses | Texto — passa por triagem |
| Autodeclaração PcD (Sim/Não) | Sim, opcional | Art. 11 II "b" | Bruto: 24 meses. Agregado: indefinido | Booleano |
| id_usuario (referência ao IdP gov.br / conta Portal MS) | Sim, obrigatório | Art. 7º III | Bruto: 24 meses. Após: pseudonimizado em agregados históricos | Identificador do IdP (não é CPF em claro) |
| Município do serviço finalístico | Sim, obrigatório | Art. 7º III | Bruto: 24 meses. Agregado: indefinido | Código IBGE do município |
| id_servico + id_orgao | Sim, obrigatório | Art. 7º III | Enquanto o serviço existir | Chave técnica |
| id_execucao_orquestrador (X-VIA) | Sim, obrigatório | Art. 7º III + art. 16 II | 24 meses | UUID — vincula avaliação à execução do serviço, previne duplicidade |
| Timestamp da avaliação | Sim, obrigatório | Art. 7º III | Igual à nota | Metadado técnico |
| User-agent (navegador/SO) | Sim, opcional | Art. 7º III | 90 dias | Diagnóstico de acessibilidade |

`[INTERPRETAÇÃO]` A identificação não passa por CPF em claro. O vínculo com o cidadão é o id do IdP (identificador opaco, próprio da conta gov.br/Portal). CPF, nome, e-mail e telefone só saem da conta quando um serviço específico os solicita — o instrumento de avaliação não solicita.

---

## 6. Dados que NÃO serão coletados

`[RECOMENDAÇÃO]` Lista negativa explícita, publicada no aviso de privacidade:

| Dado | Por que não |
|---|---|
| CPF em claro no payload da avaliação | O vínculo com o cidadão é feito pelo id do IdP; circular CPF em claro seria desnecessário |
| Nome | Não é pedido no formulário; se necessário para retorno, é obtido por referência via id do IdP |
| E-mail | Não é pedido no formulário; o disparador de e-mail transacional usa o e-mail cadastrado na conta gov.br via id do IdP, sem duplicar o dado |
| Telefone | Sem uso na avaliação |
| Endereço | Município do serviço finalístico já cobre a necessidade regional |
| Geolocalização precisa (GPS) | Município é suficiente; GPS é excessivo |
| IP completo | Prevenção de duplicidade usa `id_usuario + id_execucao_orquestrador`, não IP |
| Tipo específico de deficiência | O bloco de acessibilidade fica em Sim/Não; detalhe abre risco de identificação em serviços de baixo volume |
| Renda, raça, religião, orientação política ou sexual, saúde | Sensíveis (art. 5º II); sem nexo com a finalidade |
| Cookies de terceiros / rastreadores publicitários | Sem finalidade no instrumento |

`[INTERPRETAÇÃO]` A lista negativa é tão importante quanto a positiva: comunica ao cidadão o que ele **não vai** entregar ao clicar em "Enviar avaliação" — e vincula juridicamente o órgão. A regra permanece mesmo com a mudança para avaliação identificada: identificar não é a mesma coisa que coletar dado novo.

---

## 7. Direitos do titular

`[FATO]` LGPD art. 18 garante ao titular: confirmação de tratamento, acesso, correção, anonimização/bloqueio/eliminação, portabilidade, informação sobre compartilhamentos, revogação de consentimento e revisão de decisões automatizadas.

`[INTERPRETAÇÃO]` Como a avaliação passou a ser identificada (decisão SGD 2026-08-25), os direitos do titular são **plenamente operáveis** — o cidadão logado pode ser localizado pelo id do IdP e ter sua avaliação acessada, retificada ou eliminada individualmente. A operacionalização deixa de ter a limitação do modelo anônimo anterior.

`[RECOMENDAÇÃO]` Procedimento mínimo para atender direitos do titular:

1. **Canal:** DPO estadual (contato **não identificado** publicamente hoje — pendência a resolver antes do go-live).
2. **Prazo:** 15 dias corridos após solicitação, conforme prática ANPD.
3. **Escopo do acesso:** cidadão consegue ver suas próprias avaliações (por serviço, data, nota, motivos, comentário, PcD, município).
4. **Retificação:** permitida para nota, motivos, comentário e PcD. Não para dados de operação (id_servico, timestamp, id_execucao_orquestrador).
5. **Eliminação:** apaga o registro individual do dado bruto. Estatísticas agregadas já publicadas não são recomputadas retroativamente (o dado agregado, após pseudonimização, não é dado pessoal — art. 12).
6. **Portabilidade:** exportação em CSV/JSON das próprias avaliações.
7. **Revisão de decisão automatizada:** não se aplica — o instrumento não toma decisão automatizada sobre o cidadão.

`[RECOMENDAÇÃO]` Texto padrão no aviso de privacidade sobre direitos:

> "Você pode consultar, corrigir, exportar ou pedir a exclusão das avaliações que enviou. Como você está logado no Portal MS, conseguimos identificar suas avaliações e atender essas solicitações em até 15 dias. Fale com o Encarregado pelo Tratamento de Dados (DPO) do Estado do MS: [contato]. Se você quiser fazer uma manifestação formal (elogio, reclamação, sugestão, denúncia, solicitação de acesso à informação), o canal é a Ouvidoria do Estado: [link] — a avaliação de serviço não substitui a Ouvidoria."

`[RECOMENDAÇÃO]` Para o campo aberto: manter procedimento de **triagem** para pseudonimizar dados que o próprio cidadão eventualmente escreva sobre terceiros (nome, CPF, telefone de outra pessoa) — ver seção 9.

---

## 8. Aviso de privacidade no ato — rascunho de texto

`[RECOMENDAÇÃO]` Texto curto, visível **antes** do envio (link "Como tratamos seus dados" logo abaixo do botão "Enviar avaliação"):

```
Como tratamos seus dados nesta avaliação

Esta avaliação é identificada. Como você está logado no Portal MS
para acessar este serviço, sabemos que é você quem está avaliando e
sabemos em qual município o serviço foi prestado. Não pedimos seu
CPF, nome, telefone ou endereço nesta tela — usamos apenas o vínculo
com a sua conta.

Coletamos: a nota que você deu, os motivos positivos que você marcou
(se marcou), o comentário que você escreveu (se escreveu), a
autodeclaração de deficiência (se respondeu) e o município do serviço.
Guardamos também o identificador da sua conta, o identificador do
serviço avaliado, o identificador da execução do serviço no
orquestrador X-VIA e a data.

Usamos essas informações para: (1) melhorar o serviço avaliado,
publicando nota média agregada na página do serviço e resumos em
painéis de gestão; (2) permitir análise por perfil e localização;
(3) prevenir avaliações duplicadas da mesma execução do serviço;
(4) se aplicável, voltar a falar com você sobre esta avaliação (por
exemplo, envio do link de avaliação por e-mail após conclusão do
serviço no sistema do órgão).

Dados brutos ficam guardados por até 24 meses; comentários abertos
por até 12 meses; user-agent técnico por 90 dias. Depois desses
prazos, os dados são pseudonimizados em séries agregadas ou apagados.

Não compartilhamos seus dados com empresas privadas. Publicamos em
painéis públicos e em dados abertos apenas resultados agregados
(nunca sua avaliação individual).

Você pode acessar, corrigir, exportar ou pedir a exclusão das suas
avaliações a qualquer momento — fale com o Encarregado pelo
Tratamento de Dados (DPO) do Estado do MS: [contato].

Base legal: Lei 13.709/2018 (LGPD), art. 7º III e art. 11 II "b" —
execução de política pública prevista na Lei 13.460/2017 (Código de
Defesa do Usuário de Serviços Públicos).

Ouvidoria do Estado (para manifestações formais): [link]
Política de Privacidade completa: [link]
```

`[INTERPRETAÇÃO]` O texto propositalmente evita jargão jurídico salvo nas citações legais. Boa prática ANPD: aviso "em camadas" — resumo curto no ato, política completa em link. Como a avaliação é identificada, o texto **descreve o que é feito com a identificação** (retorno, análise, prevenção de duplicidade) para que a base legal seja transparente ao cidadão.

---

## 9. Anonimização e pseudonimização

`[FATO]` LGPD art. 5º III define **anonimização**: "utilização de meios técnicos razoáveis e disponíveis no momento do tratamento, por meio dos quais um dado perde a possibilidade de associação, direta ou indireta, a um indivíduo". Art. 12 diz que dado anonimizado **não é considerado dado pessoal** — salvo se a anonimização puder ser revertida com esforço razoável. LGPD art. 13 §4º define **pseudonimização**: dado que só pode ser atribuído a um titular específico mediante informação adicional mantida separadamente.

`[INTERPRETAÇÃO]` A avaliação passou a ser identificada na coleta. A camada de anonimização/pseudonimização se desloca da coleta para o **ciclo de vida do dado**: entra identificado, é usado identificado enquanto necessário, e sai pseudonimizado ou agregado quando a finalidade que exige identificação se exaure.

`[RECOMENDAÇÃO]` Três camadas de tratamento do dado:

1. **Coleta e uso corrente (0–24 meses):** o dado é identificado pelo id do IdP. Uso restrito a: retorno ao cidadão, análise por perfil/localização, prevenção de duplicidade, atendimento aos direitos do titular.
2. **Triagem do comentário aberto:** rotina periódica (`[RECOMENDAÇÃO]` semanal) que revisa comentários buscando dado identificável **de terceiros** escrito pelo próprio cidadão (nome, CPF, telefone, e-mail, número de protocolo de outra pessoa) e substitui por marcador `[dado suprimido]`. O texto do próprio cidadão sobre si mesmo permanece, já que a avaliação é identificada.
3. **Pseudonimização em agregados históricos (> 24 meses):** id do usuário é substituído por hash irreversível antes de ir para a base analítica histórica. A tabela de mapeamento (id_usuario → hash) é destruída — a partir dali o dado deixa de ser dado pessoal (art. 12).
4. **Publicação:** só sai em forma agregada (nota média, contagem de motivos, série temporal por serviço/órgão/município). Avaliação individual, com ou sem identificação, **nunca** é publicada — pode ser citada em relatório interno com trecho e serviço, mas sem identificador do cidadão.

`[INTERPRETAÇÃO]` Corte mínimo de amostra para publicação: em serviços de baixíssimo volume (por exemplo, um serviço com 3 avaliações no ano), agregar por município ou por perfil pode reidentificar indiretamente. Daí a regra `[HIPÓTESE]` mínimo de **10 avaliações no período por corte** para publicar média específica; abaixo disso, exibir só "amostra ainda insuficiente".

---

## 10. Retenção

`[FATO]` A LGPD não fixa prazo numérico; art. 15 diz que o tratamento termina quando a finalidade se exaure ou quando o titular solicita eliminação (o que, aqui, é limitado pelo anonimato).

`[RECOMENDAÇÃO]` Política de retenção proposta:

| Categoria | Prazo | Justificativa |
|---|---|---|
| Nota + motivos + PcD + município + metadados de serviço | 24 meses no estado identificado; após, pseudonimização + retenção indefinida em forma agregada | 2 ciclos anuais permitem análise de sazonalidade; agregado histórico pseudonimizado não é dado pessoal |
| Vínculo id_usuario ↔ avaliação | 24 meses | Prazo suficiente para retorno ao cidadão, atendimento a direitos do titular e análise por perfil; após, pseudonimização com destruição da tabela de mapeamento |
| Comentário aberto | 12 meses no estado bruto (pós-triagem); após, descarte ou consolidação em relatório qualitativo agregado pseudonimizado | Texto tem maior potencial de reidentificação; ciclo mais curto |
| id_execucao_orquestrador (X-VIA) | 24 meses | Necessário para prevenção de duplicidade dentro da janela ativa |
| User-agent | 90 dias | Diagnóstico técnico de acessibilidade; padrão conservador |
| Token do link único de e-mail (proposta prévia) | Duração do token (por padrão ≤ 30 dias) | Após uso ou expiração, apagado |
| Logs de auditoria (quem acessou painel gestor, quando) | 5 anos | Boa prática de segurança para trilha de auditoria |

`[INTERPRETAÇÃO]` Diretriz ANPD para setor público: reter pelo prazo necessário à finalidade, documentar a decisão. Os prazos acima são recomendação — não obrigação legal específica. A janela de 24 meses para dado identificado combina (a) atendimento aos direitos do titular, (b) análise anual + comparação ano-contra-ano, (c) redução de risco pela pseudonimização antes de virar histórico permanente.

---

## 11. Compartilhamento

`[RECOMENDAÇÃO]`

| Com quem | O que compartilhar | Base | Forma |
|---|---|---|---|
| Órgão setorial dono do serviço | Notas, motivos e comentários referentes aos seus serviços | Execução de política pública | Painel restrito por perfil |
| Ouvidoria estadual | Estatísticas agregadas e alertas de temas críticos recorrentes no campo aberto | Art. 26 LGPD (compartilhamento entre entes públicos para execução de política pública) | Relatório periódico |
| ANPD | Sob demanda, em caso de incidente ou fiscalização | Obrigação legal | Ofício formal |
| SGD/MGI (federal) | Se e quando houver integração com API gov.br | A definir em convênio | Convênio específico |
| Público em geral (dados abertos) | **Apenas agregado**: nota média por serviço/órgão/período, distribuição de motivos, série temporal | Transparência ativa (Lei 12.527/2011 + Lei 13.460 art. 23 §2º) | CSV/JSON em portal de dados abertos |
| Terceiros privados (fornecedores, empresas) | **Nada** | — | — |

`[RECOMENDAÇÃO]` Se houver fornecedor operando a infraestrutura (nuvem, plataforma), formalizar como **operador** (art. 5º VII LGPD) em contrato com cláusula específica de tratamento, e não como controlador.

---

## 12. Publicação (dados abertos)

`[FATO]` Lei 13.460/2017 art. 23 §2º: os resultados da avaliação devem ser "integralmente publicados no sítio do órgão ou entidade, incluindo o ranking das entidades com maior incidência de reclamação". A publicação, portanto, é obrigatória — não facultativa.

`[RECOMENDAÇÃO]`

1. **Página pública de cada serviço no Portal MS**: nota média + nº de avaliações no período visível (padrão gov.br).
2. **Painel público consolidado**: nota média por órgão, ranking, série temporal.
3. **Dataset em dados abertos**: CSV mensal com colunas `servico_id, orgao, mes, n_avaliacoes, nota_media, distribuicao_motivos, pct_pcd`. Sem coluna de comentário aberto.
4. **Corte mínimo de amostra**: só publicar média específica quando houver ≥10 avaliações no período. Abaixo disso, exibir "amostra ainda insuficiente" (evita ranking injusto e reduz risco de reidentificação em serviços pequenos).

---

## 13. Governança

`[RECOMENDAÇÃO]` Papéis explícitos:

- **Controlador:** Governo do Estado do MS (pessoa jurídica). Cada órgão setorial é corresponsável pelos dados dos serviços que oferta.
- **Encarregado / DPO:** DPO do Estado do MS. **Não identificado** publicamente o nome/e-mail atual — precisa ser confirmado junto à SETDIG e publicado no aviso de privacidade.
- **Operador:** eventual fornecedor de infraestrutura (nuvem, plataforma de avaliação), formalizado em contrato.
- **Autoridade fiscalizadora:** ANPD (Autoridade Nacional de Proteção de Dados).
- **Canal de manifestação identificada do cidadão:** Ouvidoria Estadual — não o instrumento de avaliação.

`[RECOMENDAÇÃO]` Rotinas mínimas de governança:

1. **Revisão anual do desenho do instrumento** com participação do DPO e da Ouvidoria.
2. **Log de acesso ao painel gestor** com trilha de auditoria (5 anos).
3. **Plano de resposta a incidente** documentado — quem notifica ANPD e cidadão (via aviso público, dado o anonimato) em caso de vazamento.
4. **Relatório de Impacto à Proteção de Dados (RIPD)** — art. 38 LGPD. **Obrigatório antes do go-live** pela combinação de (a) tratamento identificado em larga escala de dados de cidadãos usando serviço público, (b) dado sensível (autodeclaração PcD) na mesma base, (c) uso do dado para retorno individual ao cidadão (disparo de e-mail transacional).

---

## 14. Cidadão vulnerável

`[RECOMENDAÇÃO]` Cuidados específicos:

- **PcD:** bloco de acessibilidade opcional e binário (Sim/Não), sem detalhar tipo de deficiência. Uso: analisar se a experiência varia entre PcD e não-PcD. Nunca cruzar com serviço específico em publicação quando amostra for pequena.
- **Idoso:** priorizar linguagem simples, fontes maiores, alto contraste no formulário. Não perguntar idade — não é necessária ao instrumento.
- **Criança:** avaliação de serviço público digital, por design, é para o usuário adulto do serviço. Se responsável legal responde por menor, a avaliação continua sendo do serviço, não da criança — não coletar dados do menor.
- **Não-alfabetizado digital:** considerar canal alternativo (totem físico com pictogramas, ou avaliação verbal via atendente do Fácil MS) — fora do escopo digital deste documento, mas registrado para consistência de política.

---

## 15. Base legal usada pelo gov.br (MGI)

`[FATO]` gov.br opera a Ferramenta de Avaliação como instrumento **anônimo por design**, apoiado em Portaria SGD/ME 548/2022 e Portaria SGD/MGI 1.083/2025 — ambas normatizam a coleta como parte do Modelo de Qualidade dos Serviços Públicos federais, o que se enquadra em execução de política pública (LGPD art. 7º III). Fontes: [Portaria 548/2022](https://www.in.gov.br/en/web/dou/-/portaria-sgd/me-n-548-de-24-de-janeiro-de-2022-375784151); [Portaria 1083/2025 — Biblioteca Digital MGI](https://bibliotecadigital.gestao.gov.br/handle/123456789/533149).

`[INTERPRETAÇÃO]` MS **diverge** do gov.br nesse ponto (decisão SGD 2026-08-25): a avaliação estadual é identificada. A base LGPD continua sendo a mesma (execução de política pública), mas o desenho é mais amplo. A divergência precisa ser sustentada em três frentes:

1. **Ato normativo estadual próprio** que institua o Modelo de Qualidade dos Serviços Digitais do MS e reconheça expressamente a coleta identificada como parte da política pública.
2. **RIPD (Relatório de Impacto à Proteção de Dados)** documentando por que a identificação é necessária, proporcional e minimizada.
3. **Transparência ativa** — o aviso de privacidade do MS diz explicitamente que a avaliação é identificada e o que se faz com a identificação, para que o cidadão não seja surpreendido pela diferença em relação ao gov.br federal.

`[RECOMENDAÇÃO]` Publicar ato normativo estadual instituindo o Modelo de Qualidade dos Serviços Digitais do MS antes do go-live do instrumento. Estrutura enxuta, espelhando a lógica das portarias federais, mas com previsão explícita de coleta identificada via IdP gov.br e finalidades autorizadas.

---

## 16. Legislação estadual de MS sobre proteção de dados

`[FATO]` **Não identificado** nesta rodada de pesquisa lei ou decreto estadual específico de MS regulamentando LGPD no Poder Executivo estadual, nem o nome público do Encarregado (DPO) do Governo do Estado. Requer confirmação em rodada de validação com a Procuradoria-Geral do Estado e/ou com a área jurídica da SETDIG.

`[RECOMENDAÇÃO]` Ações de fechamento dessa lacuna:

1. Consultar a **PGE-MS** sobre existência de decreto estadual de LGPD.
2. Identificar publicamente o **DPO/Encarregado do Estado** e seu canal de contato — o nome precisa constar no aviso de privacidade.
3. Verificar se há **Comitê de Governança de Dados** estadual — se sim, submeter o instrumento à apreciação antes do go-live.

---

## 17. Riscos identificados

| # | Risco | Probabilidade | Impacto | Mitigação |
|---|---|---|---|---|
| 1 | Cidadão escreve dado identificável de terceiros no campo aberto | Média | Médio | Triagem periódica com substituição por `[dado suprimido]` antes de disponibilizar em painel |
| 2 | Reidentificação por cruzamento em serviço de baixo volume em publicação | Baixa | Médio | Corte mínimo de 10 avaliações para publicar média específica; publicação sempre agregada |
| 3 | Uso do painel gestor por pessoa não autorizada (agora com acesso a dado identificado) | Baixa | Alto | Perfis restritos por órgão, autenticação forte, log de acesso 5 anos, escopo do painel definido no aceite |
| 4 | Desvio de finalidade (usar id do usuário para marketing, ranking individual público, treinar IA) | Média | Alto | Finalidade específica declarada; qualquer novo uso exige reavaliação formal, atualização do aviso e, se necessário, novo RIPD |
| 5 | Falta de DPO/Encarregado publicado (bloqueio para exercício de direitos do titular) | Alta hoje | Alto | Ação prévia ao go-live: identificar e publicar contato do DPO estadual — pré-requisito, não opcional |
| 6 | Ausência de norma estadual que fundamente "execução de política pública" | Média | Médio | Publicar decreto/resolução instituindo o Modelo de Qualidade do MS antes do go-live |
| 7 | Retenção prolongada sem revisão | Média | Médio | Revisão anual da política de retenção; rotina automática de pseudonimização aos 24 meses |
| 8 | Vazamento de comentários abertos brutos pré-triagem | Baixa | Alto | Criptografia em repouso; acesso restrito à área de triagem; janela curta (12 meses) |
| 9 | Retenção indevida do vínculo id_usuario ↔ avaliação além de 24 meses | Média | Alto | Job automático de pseudonimização + destruição da tabela de mapeamento; auditoria trimestral |
| 10 | Ranking público prejudicando serviços com amostra pequena | Alta | Baixo | Corte mínimo de amostra + rotulagem "amostra insuficiente" |
| 11 | Uso indevido do e-mail transacional de avaliação (proposta prévia) para comunicação de marketing ou massa | Média | Alto | Canal técnico separado, opt-out específico, template fechado, auditoria de disparo |
| 12 | Link único da avaliação por e-mail sendo compartilhado por engano com terceiro | Baixa | Médio | Token curto, uso único, validade limitada, avaliação só é gravada com sessão autenticada do titular |
| 13 | Serviço fora do orquestrador X-VIA sendo avaliado por engano | Baixa | Baixo | Validação de escopo no widget e na API: rejeita avaliação sem `id_execucao_orquestrador` válido |

---

## 18. Lacunas de pesquisa

- **Não identificado** decreto estadual de MS sobre LGPD no Poder Executivo (checar PGE-MS).
- **Não identificado** DPO/Encarregado publicamente indicado para o Estado do MS — **bloqueia** publicar o aviso de privacidade completo.
- **Não identificado** existência de Comitê de Governança de Dados estadual.
- **Não identificado** política de retenção específica da Ferramenta de Avaliação gov.br. Prazos aqui são recomendação por analogia e boa prática ANPD.
- **Não identificado** como cada sistema do órgão finalístico sinaliza ao orquestrador X-VIA que o serviço foi concluído (pendência técnica com Maycon). Sem esse sinal, a proposta prévia de retorno por e-mail não pode ser implementada com prazo estimado.
- **Não identificado** política de retenção e opt-out do e-mail transacional do Portal MS que seria reutilizada pelo disparador de link de avaliação.
- **Não identificado** se a Ouvidoria estadual quer ser destinatária de alertas quando um comentário aberto identificado revelar problema grave (fluxo a definir).
- `[HIPÓTESE]` A ANPD deve emitir, em algum momento, orientação específica sobre pesquisas de satisfação identificadas no setor público — vale monitorar para revisar este documento.

---

## Fontes

Consolidadas em [pesquisa/fontes.md — seção LGPD / Governança](../pesquisa/fontes.md#lgpd--governança).
