# 4. Dados e privacidade

## Princípio único

**Menos é mais.** Cada campo extra reduz a taxa de resposta e amplia risco LGPD. Coleta-se só o que a gestão vai usar.

`[FATO]` Três forças reforçam o desenho enxuto:

- **Portaria SGD/ME nº 548/2022, art. 7º, §3º:** *"a avaliação de satisfação não poderá ser uma etapa obrigatória da jornada do usuário"*.
- **LGPD, art. 6º, III:** minimização — coletar apenas o necessário para a finalidade declarada.
- **Instrumentos de 2–3 perguntas** atingem 86,8% de conclusão vs. 77,4% em formulários de 4–6 perguntas (Survicate 2025).

## Enquadramento legal

`[FATO]` Duas leis se sobrepõem no instrumento:

- **Lei nº 13.460/2017** — Código de Defesa do Usuário. Art. 23 **obriga** órgãos e entidades a avaliar continuamente a satisfação do usuário, com resultado publicado no sítio do órgão.
- **Lei nº 13.709/2018 (LGPD)** — rege todo tratamento de dado pessoal, inclusive pelo Poder Público em execução de política pública.

`[INTERPRETAÇÃO]` A Lei 13.460 é a **causa** da avaliação (obriga a coletar); a LGPD é o **limite** (define como e o quê pode ser coletado). O instrumento nasce obrigatório por lei e minimalista por lei — o que reforça o desenho enxuto adotado.

## Base legal para o tratamento

`[RECOMENDAÇÃO]` Adotar **duas bases legais convivendo**, cada uma para um tipo de dado:

| Bloco do formulário | Base legal LGPD | Fundamento |
|---|---|---|
| Nota + motivos positivos | Art. 7º, III — execução de política pública | Cumpre obrigação legal da Lei nº 13.460/2017 art. 23 |
| Comentário aberto | Art. 7º, III — execução de política pública | Mesmo fundamento; texto voluntário |
| ~~Autodeclaração PcD~~ | ~~Art. 11, II, "b"~~ — **fora da primeira versão** (decisão D13) | Deficiência é dado pessoal sensível (art. 5º, II). Sem o bloco, a primeira versão não trata dado sensível e opera só com o art. 7º, III |
| Vínculo com o cidadão (`id_usuario` do IdP) + município do serviço | Art. 7º, III — execução de política pública | Identificação vem do login já existente; município vem do orquestrador X-VIA. Usados para (a) prevenir duplicidade, (b) permitir retorno ao cidadão via e-mail, (c) análise por perfil/localização. |
| Metadados técnicos (timestamp, `id_execucao_orquestrador`) | Art. 7º, III + art. 16, II | Necessários para operação, agregação temporal e prevenção de duplicidade |

`[RECOMENDAÇÃO]` **Evitar consentimento (art. 7º, I)** como base primária. Em serviço público, o consentimento é frágil juridicamente (não é livre nem plenamente informado no sentido pleno da lei) e mistura duas relações — a de acesso ao serviço e a de melhoria do serviço. A execução de política pública cobre exatamente esse caso.

`[RECOMENDAÇÃO]` **Não usar legítimo interesse (art. 7º, IX).** A ANPD desestimula seu uso pelo Poder Público quando há hipótese específica disponível.

## Por que a avaliação passou a ser identificada

`[INTERPRETAÇÃO]` A decisão SGD de 2026-08-25 mudou o instrumento de anônimo para identificado. A troca é legítima desde que a base legal correta seja declarada (execução de política pública) e a minimização seja mantida.

Três motivos justificam a identificação:

1. **O X-VIA já garante que o cidadão está logado.** Não identificar seria descartar informação já disponível.
2. **Sem identificação não é possível fechar o ciclo com o cidadão** — em particular, o disparo de e-mail com link único de avaliação depois que o serviço termina no sistema do órgão.
3. **Sem localização não é possível ver diferenças regionais** que orientem decisão de política pública.

A **divergência em relação ao gov.br** (que é anônimo por design) é justificada em duas frentes:

- **Ato normativo estadual próprio** instituindo o Modelo de Qualidade dos Serviços Digitais do MS, com previsão expressa da coleta identificada.
- **Relatório de Impacto à Proteção de Dados (RIPD)** documentando por que a identificação é necessária, proporcional e minimizada.

## Dados que serão tratados

| Dado | Coletado? | Base legal | Retenção | Forma |
|---|---|---|---|---|
| Nota (1–5 estrelas) | **Obrigatório** | Art. 7º, III | Bruto: 24 meses. Agregado: indefinido | Inteiro 1–5 |
| Motivos positivos (6 cards, até 3) | Opcional | Art. 7º, III | Bruto: 24 meses. Agregado: indefinido | Lista de códigos |
| Comentário aberto | Opcional | Art. 7º, III | Bruto: 12 meses (com triagem). Agregado: indefinido | Texto até 2000 caracteres |
| Autodeclaração PcD | **Não** — fora da primeira versão (D13) | Art. 11, II, "b" quando entrar | Bruto: 24 meses. Agregado: indefinido | Booleano |
| `id_usuario` (ref. ao IdP gov.br / conta Portal MS) | **Sempre** (vem do login) | Art. 7º, III | Bruto: 24 meses. Após: pseudonimização em agregados históricos | Identificador do IdP — **não é CPF em claro** |
| Município do serviço finalístico | **Sempre** (vem do X-VIA) | Art. 7º, III | Bruto: 24 meses. Agregado: indefinido | Código IBGE do município |
| `id_servico`, `id_orgao` | **Sempre** | Metadado — não é dado pessoal | Indefinido | Chave técnica |
| `id_execucao_orquestrador` (X-VIA) | **Sempre** | Art. 7º, III + art. 16, II | 24 meses | UUID — vincula avaliação à execução e previne duplicidade |
| Canal (web / mobile) | **Sempre** | Metadado | Indefinido | Enum |
| Origem do convite (tela / e-mail) | **Sempre** | Metadado | Indefinido | Enum |
| Timestamp da avaliação | **Sempre** | Metadado | Bruto: 24 meses | ISO-8601 |
| Versão do formulário | **Sempre** | Metadado | Indefinido | Inteiro |

`[INTERPRETAÇÃO]` A identificação **não** passa por CPF em claro. O vínculo com o cidadão é o identificador opaco do provedor de identidade (IdP gov.br / conta Portal MS). CPF, nome, e-mail e telefone só saem da conta quando um serviço específico os solicita — o instrumento de avaliação **não** solicita.

## Dados que NÃO serão coletados

Lista negativa explícita, publicada no aviso de privacidade:

| Dado | Por que não |
|---|---|
| CPF em claro no formulário | O vínculo com o cidadão é feito pelo id do IdP; circular CPF é desnecessário |
| Nome | Não é pedido no formulário; se necessário para retorno, é obtido por referência via id do IdP |
| E-mail | Não é pedido no formulário; o disparador de e-mail transacional usa o e-mail já cadastrado na conta, sem duplicar o dado |
| Telefone | Sem uso na avaliação |
| Endereço | Município do serviço já cobre a necessidade regional |
| Geolocalização precisa (GPS) | Município é suficiente; GPS é excessivo |
| IP completo | Prevenção de duplicidade usa `id_usuario + id_execucao_orquestrador`, não IP |
| Qualquer dado sobre deficiência | O bloco de autodeclaração está fora da primeira versão (D13). Quando entrar, fica em Sim/Não: o tipo específico abre risco de identificação em serviço de baixo volume |
| Renda, raça, religião, orientação política ou sexual, saúde | Sensíveis (art. 5º, II) sem nexo com a finalidade |
| Cookies de terceiros / rastreadores publicitários | Sem finalidade no instrumento |

`[INTERPRETAÇÃO]` A lista negativa é tão importante quanto a positiva: comunica ao cidadão o que ele **não vai entregar** ao clicar em "Enviar avaliação" — e vincula juridicamente o Estado. A regra permanece mesmo com a mudança para avaliação identificada: identificar **não é** a mesma coisa que coletar dado novo.

## Finalidade

`[RECOMENDAÇÃO]` Redigir a finalidade em uma frase única, replicável em todos os pontos de contato:

> *Coletar avaliações identificadas do cidadão logado no Portal MS sobre serviços digitais que nascem no orquestrador X-VIA, para diagnosticar qualidade, priorizar melhorias, viabilizar retorno ao próprio cidadão quando aplicável e cumprir o art. 23 da Lei nº 13.460/2017.*

`[INTERPRETAÇÃO]` A finalidade específica (LGPD art. 6º, I) protege o dado contra desvio de uso posterior. Três consequências práticas:

1. Usar o comentário aberto para outra coisa (por exemplo, treinar modelo de IA de atendimento) exige nova finalidade e reavaliação.
2. Usar o id do usuário para comunicação de marketing, ranking individual público ou perfil comercial está **fora** da finalidade — vedado.
3. Cruzar avaliação com outros dados do cidadão em outros serviços do Estado depende de finalidade explícita e proporcional — não é livre por padrão.

## Minimização aplicada ao instrumento

Quatro regras práticas:

1. **Toda pergunta precisa justificar seu próprio uso.** Se um dado não vai virar decisão, indicador ou retorno ao cidadão, ele não entra.
2. **Opcionalidade por default nas perguntas de conteúdo.** Único campo obrigatório: a nota.
3. **Nenhum campo novo de identificação no formulário.** A identificação vem do login já existente. Isso preserva minimização mesmo com avaliação identificada.
4. **Município vem do X-VIA, não do cidadão.** O município registrado é o do serviço finalístico (dado da operação), não a residência do cidadão (dado pessoal adicional).

## Direitos do titular

`[FATO]` LGPD art. 18 garante ao titular: confirmação de tratamento, acesso, correção, anonimização/bloqueio/eliminação, portabilidade, informação sobre compartilhamentos e revisão de decisões automatizadas.

`[INTERPRETAÇÃO]` Como a avaliação passou a ser identificada, os direitos do titular são **plenamente operáveis** — o cidadão logado pode ser localizado pelo id do IdP e ter sua avaliação acessada, retificada ou eliminada individualmente.

`[RECOMENDAÇÃO]` Procedimento mínimo:

1. **Canal:** Encarregado (DPO) estadual — **Não identificado** publicamente hoje; pendência bloqueadora antes do go-live.
2. **Prazo:** 15 dias corridos após solicitação (prática ANPD).
3. **Escopo do acesso:** cidadão vê suas próprias avaliações por serviço, data, nota, motivos, comentário e município.
4. **Retificação:** permitida para nota, motivos e comentário. Não para dados de operação (`id_servico`, timestamp, `id_execucao_orquestrador`).
5. **Eliminação:** apaga o registro individual. Estatísticas agregadas já publicadas não são recomputadas retroativamente (LGPD art. 12 — dado agregado pseudonimizado não é dado pessoal).
6. **Portabilidade:** exportação em CSV/JSON das próprias avaliações.
7. **Revisão de decisão automatizada:** não se aplica — o instrumento não toma decisão automatizada sobre o cidadão.

## Anonimização, pseudonimização e triagem

`[RECOMENDAÇÃO]` Três camadas de tratamento do dado:

1. **Coleta e uso corrente (0–24 meses).** Dado identificado pelo id do IdP. Uso restrito à finalidade declarada.
2. **Triagem do comentário aberto.** Rotina periódica (recomendação: semanal) revisa comentários buscando dado identificável **de terceiros** escrito pelo próprio cidadão (nome, CPF, telefone, e-mail, protocolo alheio) e substitui por `[dado suprimido]`. O texto do próprio cidadão sobre si mesmo permanece — a avaliação é identificada, e o cidadão pode falar de si.
3. **Pseudonimização em agregados históricos (> 24 meses).** `id_usuario` é substituído por hash irreversível antes de ir para a base analítica histórica. A tabela de mapeamento é destruída — a partir dali, o dado deixa de ser dado pessoal (LGPD art. 12).
4. **Publicação sempre agregada.** Painel público e dados abertos só saem em forma agregada. Avaliação individual, com ou sem identificação, **nunca** é publicada.

`[INTERPRETAÇÃO]` Corte mínimo de amostra para publicação: em serviço de baixíssimo volume, agregar por município ou por perfil pode reidentificar indiretamente. Regra: **≥ 10 avaliações no período por corte** para publicar média específica; abaixo disso, exibir *"amostra ainda insuficiente"*.

## Retenção

| Categoria | Prazo | Justificativa |
|---|---|---|
| Nota + motivos + município + metadados de serviço | 24 meses no estado identificado; após, pseudonimização + retenção indefinida em forma agregada | Dois ciclos anuais para análise de sazonalidade |
| Vínculo `id_usuario` ↔ avaliação | 24 meses | Suficiente para retorno ao cidadão, atendimento a direitos do titular e análise por perfil |
| Comentário aberto | 12 meses no estado bruto (pós-triagem); após, descarte ou consolidação em relatório qualitativo agregado pseudonimizado | Texto tem maior potencial de reidentificação; ciclo mais curto |
| `id_execucao_orquestrador` (X-VIA) | 24 meses | Necessário para prevenção de duplicidade |
| Token do link único de e-mail | Duração do token (≤ 30 dias) | Após uso ou expiração, apagado |
| Logs de auditoria (quem acessou painel) | 5 anos | Boa prática de segurança |

## Aviso de privacidade no ato — rascunho

`[RECOMENDAÇÃO]` Texto visível no formulário (link *"Como tratamos seus dados"* logo abaixo do botão de envio):

```
Como tratamos seus dados nesta avaliação

Esta avaliação é identificada. Como você está logado no Portal MS
para acessar este serviço, sabemos que é você quem está avaliando e
em qual município o serviço foi prestado. Não pedimos seu CPF, nome,
telefone ou endereço nesta tela — usamos apenas o vínculo com a sua
conta.

Coletamos: a nota que você deu, os motivos positivos que você marcou
(se marcou), o comentário que você escreveu (se escreveu) e o
município do serviço.
Guardamos também o identificador da sua conta, o identificador do
serviço avaliado, o identificador da execução do serviço no
orquestrador X-VIA e a data.

Usamos essas informações para: (1) melhorar o serviço avaliado,
publicando nota média agregada na página do serviço e em painéis de
gestão; (2) permitir análise por perfil e localização; (3) prevenir
avaliações duplicadas da mesma execução; (4) quando aplicável, voltar
a falar com você sobre esta avaliação (por exemplo, envio do link de
avaliação por e-mail após conclusão do serviço no sistema do órgão).

Dados brutos ficam guardados por até 24 meses; comentários abertos
por até 12 meses. Depois desses prazos, os dados são pseudonimizados
em séries agregadas ou apagados.

Não compartilhamos seus dados com empresas privadas. Publicamos em
painéis públicos e em dados abertos apenas resultados agregados
(nunca sua avaliação individual).

Você pode acessar, corrigir, exportar ou pedir a exclusão das suas
avaliações a qualquer momento — fale com o Encarregado pelo
Tratamento de Dados (DPO) do Estado: [contato].

Base legal: Lei nº 13.709/2018 (LGPD), art. 7º, III e art. 11, II, "b" —
execução de política pública prevista na Lei nº 13.460/2017.
```

`[INTERPRETAÇÃO]` O texto propositalmente evita jargão jurídico salvo nas citações legais. Boa prática ANPD: aviso "em camadas" — resumo curto no ato, política completa em link.

## Compartilhamento

| Com quem | O que compartilhar | Base | Forma |
|---|---|---|---|
| Órgão setorial dono do serviço | Notas, motivos e comentários referentes aos próprios serviços | Execução de política pública | Painel restrito por perfil |
| Ouvidoria Estadual | Estatísticas agregadas e alertas de temas críticos recorrentes | Art. 26 LGPD (compartilhamento entre entes públicos) | Relatório periódico |
| ANPD | Sob demanda, em caso de incidente ou fiscalização | Obrigação legal | Ofício formal |
| SGD/MGI (federal) | Se e quando houver integração com API gov.br | A definir em convênio | Convênio específico |
| Público em geral (dados abertos) | **Apenas agregado** por serviço/órgão/período/município | Transparência ativa (Lei 12.527/2011 + Lei 13.460 art. 23 §2º) | CSV/JSON em portal de dados abertos |
| Terceiros privados | **Nada** | — | — |

Se houver fornecedor operando a infraestrutura, formalizar como **operador** (LGPD art. 5º, VII) em contrato com cláusula específica de tratamento.

## Governança

**Papéis explícitos:**

- **Controlador:** Governo do Estado do MS. Cada órgão setorial é corresponsável pelos dados dos serviços que oferta.
- **Encarregado / DPO:** DPO do Estado do MS. **Não identificado** publicamente o nome/contato atual — precisa ser confirmado e publicado no aviso de privacidade.
- **Operador:** eventual fornecedor de infraestrutura, formalizado em contrato.
- **Autoridade fiscalizadora:** ANPD.
- **Canal de manifestação identificada do cidadão:** Ouvidoria Estadual — **não** o instrumento de avaliação.

**Rotinas mínimas:**

1. Revisão anual do desenho do instrumento com participação do DPO e da Ouvidoria.
2. Log de acesso ao painel com trilha de auditoria (5 anos).
3. Plano de resposta a incidente documentado.
4. **RIPD (Relatório de Impacto à Proteção de Dados)** — necessário antes do go-live pela combinação de (a) tratamento identificado em larga escala e (b) uso do dado para retorno individual via e-mail transacional. A primeira versão não trata dado sensível, porque a autodeclaração PcD ficou fora (D13); se o bloco entrar, o relatório precisa ser revisto antes.

## Cidadão vulnerável

- **PcD:** a primeira versão não pergunta (D13). Quando o bloco entrar, fica opcional e binário, e nunca deve ser cruzado com serviço específico em publicação quando a amostra for pequena.
- **Idoso:** priorizar linguagem simples, fontes maiores, alto contraste no formulário. Não perguntar idade — não é necessária.
- **Criança:** avaliação é do serviço, não da criança; se responsável responde por menor, não coletar dado do menor.
- **Cidadão não-alfabetizado digital:** considerar canal alternativo (totem físico, avaliação verbal via atendente) — fora do escopo digital deste documento, mas registrado para consistência de política.

## Riscos identificados

| # | Risco | Probabilidade | Impacto | Mitigação |
|---|---|---|---|---|
| 1 | Cidadão escreve dado de terceiros no comentário aberto | Média | Médio | Triagem periódica com substituição por `[dado suprimido]` |
| 2 | Reidentificação por cruzamento em serviço de baixo volume | Baixa | Médio | Corte mínimo ≥ 10 avaliações; publicação sempre agregada |
| 3 | Uso indevido do painel com dado identificado | Baixa | Alto | Perfis restritos, autenticação forte, log de acesso 5 anos |
| 4 | Desvio de finalidade da identificação | Média | Alto | Finalidade específica declarada; novo uso exige nova avaliação e RIPD |
| 5 | Falta de DPO publicado (bloqueio para direitos do titular) | Alta hoje | Alto | Ação prévia ao go-live: identificar e publicar contato do DPO — pré-requisito |
| 6 | Ausência de norma estadual fundamentando "execução de política pública" | Média | Médio | Publicar decreto/resolução instituindo o Modelo de Qualidade dos Serviços Digitais do MS antes do go-live |
| 7 | Retenção prolongada sem revisão | Média | Médio | Revisão anual + rotina automática de pseudonimização aos 24 meses |
| 8 | Uso indevido do e-mail transacional para comunicação de massa | Média | Alto | Canal técnico separado, opt-out específico, template fechado, auditoria de disparo |
| 9 | Link único da avaliação compartilhado por engano com terceiro | Baixa | Médio | Token curto, uso único, validade limitada, avaliação só grava com sessão autenticada do titular |
| 10 | Serviço fora do X-VIA sendo avaliado por engano | Baixa | Baixo | Validação de escopo no widget e na API |

## Base legal usada pelo gov.br (referência)

`[FATO]` gov.br opera a Ferramenta de Avaliação como instrumento **anônimo por design**, apoiado em Portaria SGD/ME nº 548/2022 e Portaria SGD/MGI nº 1.083/2025 — ambas normatizam a coleta como parte do Modelo de Qualidade dos Serviços Públicos federais.

`[INTERPRETAÇÃO]` MS **diverge** desse ponto (decisão SGD 2026-08-25): a avaliação estadual é identificada. A base LGPD continua sendo a mesma (execução de política pública), mas o desenho é mais amplo. A divergência é sustentada pelo ato normativo estadual próprio, RIPD específico e transparência ativa no aviso de privacidade.

## Lacunas de pesquisa

- **Não identificado** decreto estadual de MS sobre LGPD no Poder Executivo (checar PGE-MS).
- **Não identificado** Encarregado (DPO) publicamente indicado para o Estado — **bloqueia** publicar o aviso de privacidade completo.
- **Não identificado** existência de Comitê de Governança de Dados estadual.
- **Não identificado** como cada sistema do órgão finalístico sinaliza ao X-VIA que o serviço foi concluído (pendência técnica). Sem esse sinal, a proposta prévia de retorno por e-mail não pode ser implementada com prazo estimado.
- **Não identificado** política de retenção e opt-out do e-mail transacional do Portal MS que seria reutilizada pelo disparador do link de avaliação.

## Fontes

Consolidadas em [`pesquisa/fontes.md`](pesquisa/fontes.md).
