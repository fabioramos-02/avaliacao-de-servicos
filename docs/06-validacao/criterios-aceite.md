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

- [ ] Base legal LGPD documentada: art. 7º III (execução de política pública) + art. 11 II "b" (política pública para dado sensível — PcD). Decisão SGD 2026-08-25.
- [ ] Aviso de privacidade escrito e aprovado — texto reflete que a avaliação é identificada via login do Portal.
- [ ] Política de retenção formalizada: 24 meses bruto (nota/motivos/PcD/metadados/id_usuario), 12 meses comentário aberto, agregado indefinido em forma pseudonimizada.
- [ ] Escopo confirmado: apenas serviços que nascem no orquestrador X-VIA.
- [ ] Publicação em painel público e dados abertos respeita threshold mínimo (≥ 10 avaliações por corte) e só sai em forma agregada.
- [ ] Direitos do titular (art. 18 LGPD) endereçados: cidadão logado consegue solicitar acesso/retificação/eliminação da própria avaliação via canal do DPO estadual; procedimento documentado.
- [ ] RIPD (Relatório de Impacto à Proteção de Dados) elaborado — necessário pela combinação de identificação + dado sensível.
- [ ] Política do link único de e-mail definida (validade, escopo, opt-out específico) — depende da definição da proposta prévia de retorno por e-mail.

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
