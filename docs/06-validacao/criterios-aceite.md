# Critérios de aceite

O que precisa ser verdadeiro para declararmos a proposta validada e pronta para escala.

## Aceite técnico (STI)

- [ ] Widget renderiza em desktop e mobile (iOS, Android, principais navegadores).
- [ ] API de coleta responde em < 500ms no p95.
- [ ] Schema `fato_avaliacao` está criado no banco analítico e recebe dados corretamente.
- [ ] Dedupe por hash de sessão evita > 95% das duplicatas em teste sintético.
- [ ] Widget não bloqueia navegação (fechar/pular sempre disponíveis).
- [ ] Acessibilidade WCAG 2.1 AA validada em ferramenta automática + teste com leitor de tela.

## Aceite jurídico (Jurídico / DPO)

- [ ] Base legal LGPD documentada: art. 7º III (política pública) + art. 11 I (consentimento para PcD).
- [ ] Aviso de privacidade escrito e aprovado.
- [ ] Política de retenção formalizada: 5 anos bruto (nota/comentário), 3 anos PcD.
- [ ] Anonimização confirmada: nada que identifique cidadão é coletado.
- [ ] Publicação em dados abertos respeita threshold mínimo (≥ 10 avaliações por corte).
- [ ] Direitos do titular endereçados via canal formal (Fala.MS / DPO), já que avaliação é anônima.

## Aceite operacional (SGD + órgão piloto)

- [ ] Painel do gestor entregue e testado com pelo menos um gestor real.
- [ ] Cabeçalho contextual mostra corretamente nome do serviço + órgão.
- [ ] Fluxo de moderação de comentários definido e testado.
- [ ] Órgão piloto confirmou por escrito que quer continuar após piloto.

## Aceite Ouvidoria

- [ ] Painel de triagem entregue e utilizado semanalmente durante piloto.
- [ ] Regra de encaminhamento (comentário crítico → canal formal) documentada e testada.
- [ ] Zero conflito com Fala.MS: cidadão que quer resposta é orientado ao canal formal.

## Aceite de dados (piloto)

Durante as 4 semanas de piloto, medir:

- [ ] Taxa de resposta ≥ 5% dos usuários únicos.
- [ ] Nota média ≥ 4,0 (ou justificativa se < 4,0 apontar problema real no serviço).
- [ ] Drop-off no formulário < 30%.
- [ ] ≥ 20% dos comentários abertos são acionáveis (avaliação manual).
- [ ] Nenhum incidente de LGPD.
- [ ] Painel gestor teve ≥ 1 acesso/semana pelo gestor.

## Decisão final

- **Todos os aceites atendidos** → Secretário Executivo autoriza escala progressiva (5 serviços novos/mês).
- **1–2 critérios em falha** → ajustar item específico e repetir teste; não bloqueia decisão.
- **3+ em falha** → revisão da proposta com stakeholders antes de qualquer avanço.

## Ver também

- [Estratégia](estrategia.md)
- [Stakeholders](stakeholders.md)
- [Modelo proposto](../05-proposta/modelo-proposto.md)
- [Indicadores](../05-proposta/indicadores.md)
