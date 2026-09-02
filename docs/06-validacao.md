# 6. Validação

Como a proposta será testada e ajustada antes de virar implantação em escala.

## Objetivo

Confirmar que o modelo proposto:

1. **É viável tecnicamente** no ambiente atual do Portal MS.
2. **É aderente ao marco legal** (Lei nº 13.460/2017, LGPD, Portaria SGD/MGI nº 1.083/2025).
3. **Serve às áreas envolvidas** — órgãos setoriais, Ouvidoria, direção SETDIG.
4. **Funciona com o cidadão** — piloto controlado antes da expansão.

## Áreas envolvidas

| Área | Papel na validação | O que precisa aprovar | Poder de veto |
|---|---|---|---|
| **Secretário Executivo SETDIG** | Patrocinador | Decisão go / no-go final | Sim |
| **Superintendência de Governo Digital (SGD)** | Dona do Portal e do estudo | Modelo, fluxo, painel | Sim (escopo funcional) |
| **Superintendência de Tecnologia da Informação (STI)** | Executor técnico | Viabilidade, integração, desempenho | Sim (viabilidade técnica) |
| **Órgão setorial piloto** | Dono do serviço piloto | Fluxo no serviço, comunicação ao cidadão | Sim (no seu serviço) |
| **Ouvidoria Estadual** | Recebe e triaga comentários | Fluxo de triagem, moderação, encaminhamento | Sim (fluxo de comentários) |
| **Jurídico SETDIG / DPO estadual** | Guardião LGPD | Base legal, aviso, retenção, dado sensível, RIPD | Sim (LGPD) |
| **Xvia** | Time de desenvolvimento do Portal Único | Implementação técnica e integração X-VIA | Não (parecer executor) |
| **CGE (Controladoria)** | Auditoria | Aderência à Lei nº 13.460/2017 | Não (parecer consultivo) |
| **Cidadão-usuário (piloto)** | Validador prático | — | Não (medido por indicadores) |

### Encarregado (DPO) estadual — bloqueio a resolver

Valida base legal, prazo de retenção, texto do aviso, política de pseudonimização, regra de publicação (só agregado, corte ≥ 10) e o **Relatório de Impacto à Proteção de Dados (RIPD)** — necessário antes do go-live pela combinação de avaliação identificada + uso para retorno individual via e-mail.

`[INTERPRETAÇÃO]` Sem a autodeclaração PcD na primeira versão (decisão D13), o instrumento deixa de tratar dado sensível. O RIPD continua exigido pela identificação e pelo retorno por e-mail, mas com escopo menor. Se o bloco voltar, o relatório precisa ser revisto antes.

## Serviço piloto — critérios de escolha

O piloto precisa reunir:

- **Serviço que nasce no orquestrador X-VIA** (obrigatório desde a decisão SGD de 2026-08-25).
- Volume mensal ≥ 500 conclusões — para obter N estatisticamente relevante em 4 semanas de piloto.
- Fluxo 100% digital (avaliação ao fim do serviço, sem etapa presencial).
- Órgão setorial engajado — dispõe de gestor que vai olhar o painel.
- Baixo risco jurídico — não coleta dado sensível no serviço-mãe.

Candidatos naturais: emissão de 2ª via de documentos, consulta a débitos, agendamento simples.

## Cronograma

| Semana | Ação | Responsável |
|---|---|---|
| 1–2 | Aprovação formal da recomendação | Secretário Executivo SETDIG |
| 1–2 | Escolha do serviço piloto | SGD + órgão setorial |
| 1–2 | Parecer jurídico + aprovação do DPO + RIPD | Jurídico SETDIG + DPO |
| 3–4 | Alocação de time técnico + início dos trabalhos | STI + Xvia |
| 3–4 | Desenho dos painéis | SGD + Xvia (UX) |
| 3–6 | Implantação do widget + API + painel mínimo | STI + Xvia |
| 7 | Testes técnicos + acessibilidade | STI + SGD |
| 8 | Alinhamento com Ouvidoria + moderação | Ouvidoria + SGD |
| 9–12 | Piloto ao vivo (4 semanas) | Todos |
| 13 | Consolidação + decisão go / no-go | Secretário Executivo |

Prazo total ≈ **13 semanas** (aproximadamente 3 meses) até a decisão de implantação em escala.

## Hipóteses a testar no piloto

| Hipótese | Como testar | Critério de aprovação |
|---|---|---|
| Taxa de resposta ≥ 5% dos usuários únicos | Contar avaliações ÷ conclusões | ≥ 5% em 4 semanas |
| Nota média ≥ 4,0 | Média das notas coletadas | ≥ 4,0 no fechamento |
| Abandono do formulário < 30% | (iniciou − enviou) ÷ iniciou | < 30% |
| Comentário aberto útil ≥ 20% das respostas | Amostra manual de 100 comentários | ≥ 20% acionáveis |
| Zero incidente de LGPD | Auditoria do DPO ao fim do piloto | Sem ocorrência |
| Painel do órgão é usado | Nº de acessos únicos no período | ≥ 1 acesso/semana pelo gestor |

## Critérios de aceite

### Aceite técnico (STI + Xvia)

- [ ] Widget renderiza em desktop e mobile (iOS, Android, principais navegadores).
- [ ] API de coleta responde em < 500 ms no p95.
- [ ] Base analítica recebe os dados corretamente.
- [ ] Prevenção de duplicidade por `id_usuario + id_execucao_orquestrador` evita > 95% das duplicatas em teste sintético.
- [ ] Widget não bloqueia a navegação (fechar/pular sempre disponíveis).
- [ ] Acessibilidade WCAG 2.1 AA validada em ferramenta automática + teste com leitor de tela.

### Aceite jurídico (Jurídico / DPO)

- [ ] Base legal LGPD documentada: art. 7º, III (execução de política pública). O art. 11, II, "b" só volta a ser necessário quando a autodeclaração PcD entrar (decisão D13).
- [ ] Aviso de privacidade escrito e aprovado — reflete que a avaliação é identificada via login do Portal.
- [ ] Política de retenção formalizada: 24 meses bruto (nota/motivos/metadados/`id_usuario`), 12 meses comentário aberto, agregado indefinido em forma pseudonimizada.
- [ ] Escopo confirmado: apenas serviços que nascem no orquestrador X-VIA.
- [ ] Publicação em painel público e dados abertos respeita corte mínimo (≥ 10 avaliações por agregação) e só sai em forma agregada.
- [ ] Direitos do titular (LGPD art. 18) endereçados: cidadão logado consegue acessar, retificar ou eliminar suas avaliações via canal do DPO; procedimento documentado com prazo de 15 dias.
- [ ] RIPD elaborado.
- [ ] Política do link único do e-mail definida (validade, opt-out específico).

### Aceite operacional (SGD + órgão piloto)

- [ ] Painel do órgão entregue e testado com pelo menos um gestor real.
- [ ] Cabeçalho contextual mostra corretamente nome do serviço + órgão.
- [ ] Fluxo de moderação de comentários definido e testado.
- [ ] Órgão piloto confirmou por escrito que quer continuar após o piloto.

### Aceite Ouvidoria

- [ ] Painel de triagem entregue e utilizado semanalmente durante o piloto.
- [ ] Regra de encaminhamento (comentário crítico → canal formal) documentada e testada.
- [ ] Zero conflito com a Ouvidoria: cidadão que quer resposta é orientado ao canal formal.

### Aceite de dados (piloto)

Ao longo das 4 semanas, medir:

- [ ] Taxa de resposta ≥ 5% dos usuários únicos.
- [ ] Nota média ≥ 4,0 (ou justificativa se < 4,0 apontar problema real no serviço).
- [ ] Abandono do formulário < 30%.
- [ ] ≥ 20% dos comentários abertos são acionáveis (avaliação manual).
- [ ] Nenhum incidente de LGPD.
- [ ] Painel gestor teve ≥ 1 acesso/semana.

## O que muda depois do piloto

- **Todos os aceites atendidos** → **go**: escala progressiva (5 serviços novos por mês).
- **1–2 critérios em falha** → ajustar item específico e repetir o teste (2 semanas). Não bloqueia decisão.
- **3+ critérios em falha** → revisão da proposta com áreas envolvidas antes de qualquer avanço.

## Governança da validação

- **Comitê semanal** durante o piloto: SETDIG (SGD + STI), órgão setorial, Ouvidoria, Xvia.
- **Painel de acompanhamento** visível a todos.
- **Registro de decisões** no documento [7. Recomendação](07-recomendacao.md).

## Referências

- [Modelo proposto](03-modelo-proposto.md)
- [Dados e privacidade](04-dados-e-privacidade.md)
- [Indicadores](05-indicadores.md)
- [Recomendação](07-recomendacao.md)
