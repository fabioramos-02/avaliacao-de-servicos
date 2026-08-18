# LGPD e governança do dado da avaliação

> Este documento fixa o corte de LGPD e governança do dado do instrumento de avaliação do Portal de Serviços do MS. Ele complementa — não substitui — a Política de Privacidade geral do Governo do Estado. Referência âncora: gov.br (Central de Qualidade + Ferramenta de Avaliação).

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
| Dados de sessão técnica (IP, timestamp) | Art. 7º, III + art. 16, II | Necessários para operação e prevenção de fraude/duplicidade |

`[RECOMENDAÇÃO]` **Evitar consentimento (art. 7º I)** como base primária. Consentimento cria expectativa de que o cidadão pode revogar e exigir eliminação individual — inviável em base anonimizada. Além disso, "consentimento" cobrado como pré-condição de avaliar um serviço público é frágil juridicamente (não é livre nem informado no sentido pleno da lei).

`[RECOMENDAÇÃO]` **Não usar legítimo interesse (art. 7º IX)**. A ANPD desestimula seu uso pelo Poder Público quando há hipótese específica disponível (execução de política pública cobre o caso).

---

## 3. Princípio da minimização aplicado ao instrumento

`[FATO]` LGPD art. 6º III: "limitação ao mínimo necessário para a realização de suas finalidades".

`[RECOMENDAÇÃO]` Traduzir a minimização em três regras práticas para o formulário:

1. **Toda pergunta precisa justificar seu próprio uso.** Se um dado não vai virar decisão ou indicador publicado, ele não entra no formulário.
2. **Opcionalidade por default.** Único campo obrigatório: a nota. Motivos, comentário e acessibilidade são opcionais.
3. **Anonimato por default.** Sem CPF, sem login, sem e-mail, sem nome. O cidadão que quiser retorno individual usa a Ouvidoria (canal próprio) — não a avaliação.

---

## 4. Finalidade

`[RECOMENDAÇÃO]` Redigir a finalidade em uma frase única, replicável em todos os pontos de contato:

> "Coletar avaliações do cidadão sobre serviços digitais do Estado, para diagnosticar qualidade, priorizar melhorias e cumprir o art. 23 da Lei 13.460/2017."

`[INTERPRETAÇÃO]` Finalidade específica (art. 6º I) blinda o dado contra desvio de uso posterior. Se, no futuro, alguém quiser usar o comentário aberto para outra coisa (por exemplo, treinar modelo de IA de atendimento), essa nova finalidade precisará ser reavaliada — não está automaticamente autorizada.

---

## 5. Dados que serão tratados

| Dado | Coletado? | Base legal | Retenção sugerida | Forma |
|---|---|---|---|---|
| Nota (1–5 estrelas) | Sim, obrigatório | Art. 7º III | Bruto: 24 meses. Agregado: indefinido | Numérica anônima |
| Motivos positivos (até 3 cards) | Sim, opcional | Art. 7º III | Bruto: 24 meses. Agregado: indefinido | Categórica anônima |
| Comentário aberto (até 2000 caracteres) | Sim, opcional | Art. 7º III | Bruto: 12 meses. Anonimizado (pós-triagem): indefinido | Texto — passa por triagem |
| Autodeclaração PcD (Sim/Não) | Sim, opcional | Art. 11 II "b" | Bruto: 24 meses. Agregado: indefinido | Booleano anônimo |
| ID de serviço avaliado | Sim, obrigatório | Art. 7º III | Enquanto o serviço existir | Chave técnica |
| Timestamp da avaliação | Sim, obrigatório | Art. 7º III | Igual à nota | Metadado técnico |
| IP truncado (últimos octetos removidos) | Sim, obrigatório | Art. 7º III + art. 16 II | 90 dias | Antifraude/deduplicação |
| User-agent (navegador/SO) | Sim, opcional | Art. 7º III | 90 dias | Diagnóstico de acessibilidade |

`[FATO]` `[HIPÓTESE]` sobre o IP: gov.br não publica seu esquema exato de retenção de IP na avaliação. **Não identificado**. A prática recomendada aqui é conservadora — truncar e reter só o suficiente para antifraude.

---

## 6. Dados que NÃO serão coletados

`[RECOMENDAÇÃO]` Lista negativa explícita, publicada no aviso de privacidade:

| Dado | Por que não |
|---|---|
| CPF | gov.br não exige; identifica o cidadão sem necessidade; risco desproporcional |
| Nome | Identificação direta sem finalidade proporcional |
| E-mail | Cria expectativa de retorno individual (é papel da Ouvidoria, não da avaliação) |
| Telefone | Idem e-mail |
| Endereço | Sem uso na análise agregada |
| Geolocalização precisa (GPS) | Município do serviço é suficiente; GPS é excessivo |
| IP completo | Truncado é suficiente para deduplicação |
| Tipo específico de deficiência | O bloco de acessibilidade fica em Sim/Não; detalhe abre risco de identificação em serviços de baixo volume |
| Renda, raça, religião, orientação política ou sexual, saúde | Sensíveis (art. 5º II); sem nexo com a finalidade |
| Cookies de terceiros / rastreadores publicitários | Sem finalidade no instrumento |

`[INTERPRETAÇÃO]` A lista negativa é tão importante quanto a positiva: comunica ao cidadão o que ele **não vai** entregar ao clicar em "Enviar avaliação" — e vincula juridicamente o órgão.

---

## 7. Direitos do titular

`[FATO]` LGPD art. 18 garante ao titular: confirmação de tratamento, acesso, correção, anonimização/bloqueio/eliminação, portabilidade, informação sobre compartilhamentos, revogação de consentimento e revisão de decisões automatizadas.

`[INTERPRETAÇÃO]` Em avaliação **anônima por design**, a operacionalização é limitada — e isso precisa ser dito com honestidade:

`[RECOMENDAÇÃO]` Texto padrão no aviso de privacidade:

> "Esta avaliação é anônima. Não coletamos seu nome, CPF ou dados que permitam identificá-lo. Por isso, após o envio, não conseguimos localizar sua avaliação específica para atender pedidos de acesso, correção ou exclusão individual. Se você deseja registrar uma manifestação identificada (elogio, reclamação, sugestão, denúncia ou solicitação de acesso à informação), use a Ouvidoria do Estado: [link]. Encarregado (DPO) do Estado do MS para questões de proteção de dados: [contato]."

`[RECOMENDAÇÃO]` Para o campo aberto (único caminho em que o cidadão pode se autoidentificar voluntariamente ao escrever): manter procedimento de **triagem para anonimização** — ver seção 9.

---

## 8. Aviso de privacidade no ato — rascunho de texto

`[RECOMENDAÇÃO]` Texto curto, visível **antes** do envio (link "Como tratamos seus dados" logo abaixo do botão "Enviar avaliação"):

```
Como tratamos seus dados nesta avaliação

Esta avaliação é anônima. Coletamos: a nota que você deu, os motivos
positivos que você marcou (se marcou), o comentário que você escreveu
(se escreveu) e a autodeclaração de deficiência (se respondeu).
Guardamos também o identificador do serviço avaliado, a data e um
dado técnico truncado para evitar duplicidade.

Não coletamos seu nome, CPF, e-mail, telefone, endereço nem sua
localização exata.

Usamos essas informações para melhorar o serviço avaliado — publicamos
a nota média na página do serviço e o resumo consolidado em painéis
de gestão. Dados brutos ficam guardados por até 24 meses; comentários
abertos por até 12 meses; dados técnicos por 90 dias.

Base legal: Lei 13.709/2018 (LGPD), art. 7º III e art. 11 II "b" —
execução de política pública prevista na Lei 13.460/2017 (Código de
Defesa do Usuário de Serviços Públicos).

Encarregado pelo Tratamento de Dados (DPO) do Estado do MS: [contato]
Ouvidoria do Estado (para manifestações identificadas): [link]
Política de Privacidade completa: [link]
```

`[INTERPRETAÇÃO]` O texto propositalmente evita jargão jurídico salvo nas citações legais. Boa prática ANPD: aviso "em camadas" — resumo curto no ato, política completa em link.

---

## 9. Anonimização e pseudonimização

`[FATO]` LGPD art. 5º III define **anonimização**: "utilização de meios técnicos razoáveis e disponíveis no momento do tratamento, por meio dos quais um dado perde a possibilidade de associação, direta ou indireta, a um indivíduo". Art. 12 diz que dado anonimizado **não é considerado dado pessoal** — salvo se a anonimização puder ser revertida com esforço razoável.

`[RECOMENDAÇÃO]` Três camadas de tratamento do dado:

1. **Coleta:** já entra anônima (sem identificador direto). IP truncado no momento da coleta, nunca armazenado inteiro.
2. **Triagem do comentário aberto:** rotina periódica (`[RECOMENDAÇÃO]` semanal) que revisa comentários buscando dado identificável escrito pelo próprio cidadão (nome, CPF, telefone, e-mail, número de protocolo) e substitui por marcador `[dado suprimido]`. Comentário só entra em dashboard consolidado após triagem.
3. **Publicação:** só sai do órgão em forma agregada (nota média, contagem de motivos, série temporal). Comentário individual **nunca** é publicado bruto — pode ser citado em relatório interno com trecho e serviço, mas sem identificador.

`[INTERPRETAÇÃO]` Nota + motivo + serviço + timestamp, isoladamente, não permitem reidentificar em serviços de alto volume. Em serviços de baixíssimo volume (por exemplo, um serviço com 3 avaliações no ano), a combinação pode ser reidentificável indiretamente — daí a regra de só publicar agregado quando houver massa mínima (`[HIPÓTESE]` corte sugerido: mínimo de 10 avaliações no período para publicar média específica; abaixo disso, exibir só "amostra ainda insuficiente").

---

## 10. Retenção

`[FATO]` A LGPD não fixa prazo numérico; art. 15 diz que o tratamento termina quando a finalidade se exaure ou quando o titular solicita eliminação (o que, aqui, é limitado pelo anonimato).

`[RECOMENDAÇÃO]` Política de retenção proposta:

| Categoria | Prazo | Justificativa |
|---|---|---|
| Nota + motivos + PcD + metadados de serviço | 24 meses no estado bruto; após, retenção indefinida em forma agregada | 2 ciclos anuais permitem análise de sazonalidade; agregado histórico não é dado pessoal |
| Comentário aberto | 12 meses no estado bruto (pós-triagem); após, descarte ou consolidação em relatório qualitativo agregado | Texto tem maior potencial de reidentificação; ciclo mais curto |
| IP truncado + user-agent | 90 dias | Suficiente para antifraude/deduplicação; padrão conservador |
| Logs de auditoria (quem acessou painel gestor, quando) | 5 anos | Boa prática de segurança para trilha de auditoria |

`[INTERPRETAÇÃO]` Diretriz ANPD para setor público: reter pelo prazo necessário à finalidade, documentar a decisão. Os prazos acima são recomendação — não obrigação legal específica.

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
4. **Relatório de Impacto à Proteção de Dados (RIPD)** — art. 38 LGPD. Recomendável elaborar antes do go-live, mesmo não sendo obrigatório para dado majoritariamente anonimizado, porque a autodeclaração PcD é dado sensível.

---

## 14. Cidadão vulnerável

`[RECOMENDAÇÃO]` Cuidados específicos:

- **PcD:** bloco de acessibilidade opcional e binário (Sim/Não), sem detalhar tipo de deficiência. Uso: analisar se a experiência varia entre PcD e não-PcD. Nunca cruzar com serviço específico em publicação quando amostra for pequena.
- **Idoso:** priorizar linguagem simples, fontes maiores, alto contraste no formulário. Não perguntar idade — não é necessária ao instrumento.
- **Criança:** avaliação de serviço público digital, por design, é para o usuário adulto do serviço. Se responsável legal responde por menor, a avaliação continua sendo do serviço, não da criança — não coletar dados do menor.
- **Não-alfabetizado digital:** considerar canal alternativo (totem físico com pictogramas, ou avaliação verbal via atendente do Fácil MS) — fora do escopo digital deste documento, mas registrado para consistência de política.

---

## 15. Base legal usada pelo gov.br (MGI)

`[FATO]` gov.br opera a Ferramenta de Avaliação como instrumento anônimo por design, apoiado em Portaria SGD/ME 548/2022 e Portaria SGD/MGI 1.083/2025 — ambas normatizam a coleta como parte do Modelo de Qualidade dos Serviços Públicos federais, o que se enquadra em execução de política pública (LGPD art. 7º III). Fontes: [Portaria 548/2022](https://www.in.gov.br/en/web/dou/-/portaria-sgd/me-n-548-de-24-de-janeiro-de-2022-375784151); [Portaria 1083/2025 — Biblioteca Digital MGI](https://bibliotecadigital.gestao.gov.br/handle/123456789/533149).

`[INTERPRETAÇÃO]` MS pode reproduzir a mesma lógica: uma norma estadual (decreto ou resolução SETDIG) que institua o Modelo de Qualidade dos Serviços Digitais do Estado dá lastro jurídico direto à execução de política pública como base LGPD.

`[RECOMENDAÇÃO]` Publicar ato normativo estadual instituindo o Modelo de Qualidade dos Serviços Digitais do MS antes do go-live do instrumento. Estrutura enxuta, espelhando a lógica das portarias federais.

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
| 1 | Cidadão escreve dado identificável no campo aberto (nome, CPF, telefone) | Média | Médio | Triagem periódica com substituição por `[dado suprimido]` antes de disponibilizar em painel |
| 2 | Reidentificação por cruzamento em serviço de baixo volume | Baixa | Médio | Corte mínimo de 10 avaliações para publicar média específica |
| 3 | Uso do painel gestor por pessoa não autorizada | Baixa | Alto | Perfis, autenticação forte, log de acesso 5 anos |
| 4 | Desvio de finalidade (usar dados para outra coisa, ex.: treinar IA) | Média | Alto | Finalidade específica declarada; qualquer novo uso exige reavaliação formal e ajuste do aviso |
| 5 | Falta de DPO/Encarregado publicado | Alta hoje | Médio | Ação prévia ao go-live: identificar e publicar contato do DPO estadual |
| 6 | Ausência de norma estadual que fundamente "execução de política pública" | Média | Médio | Publicar decreto/resolução instituindo o Modelo de Qualidade do MS |
| 7 | Retenção prolongada sem revisão | Média | Baixo | Revisão anual da política de retenção; rotina automática de descarte após prazo |
| 8 | Vazamento de comentários abertos brutos pré-triagem | Baixa | Alto | Criptografia em repouso; acesso restrito à área de triagem; janela curta (12 meses) |
| 9 | Coleta involuntária de IP completo por camada de infraestrutura | Média | Médio | Truncamento no ponto de entrada (edge), auditável |
| 10 | Ranking público prejudicando serviços com amostra pequena | Alta | Baixo | Corte mínimo de amostra + rotulagem "amostra insuficiente" |

---

## 18. Lacunas de pesquisa

- **Não identificado** decreto estadual de MS sobre LGPD no Poder Executivo (checar PGE-MS).
- **Não identificado** DPO/Encarregado publicamente indicado para o Estado do MS.
- **Não identificado** existência de Comitê de Governança de Dados estadual.
- **Não identificado** política de retenção específica da Ferramenta de Avaliação gov.br (prazos exatos de descarte de IP e comentários no lado do MGI). Prazos aqui são recomendação por analogia e boa prática ANPD.
- `[HIPÓTESE]` A ANPD deve emitir, em algum momento, orientação específica sobre pesquisas de satisfação no setor público — vale monitorar para revisar este documento.

---

## Fontes

Consolidadas em [pesquisa/fontes.md — seção LGPD / Governança](../pesquisa/fontes.md#lgpd--governança).
