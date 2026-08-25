# Stakeholders da validação

Quem precisa concordar antes de a avaliação ir a escala.

## Mapa de stakeholders

| Stakeholder | Papel na validação | O que precisa aprovar | Poder de veto? |
|---|---|---|---|
| **Secretário Executivo SETDIG** | Patrocinador executivo | Decisão go/no-go final | Sim |
| **Superintendência de Governo Digital (SGD)** | Dona do Portal e do estudo | Modelo, fluxo, painel | Sim (escopo funcional) |
| **Superintendência de Tecnologia da Informação (STI)** | Executor técnico | Viabilidade, integração, performance | Sim (viabilidade técnica) |
| **Órgão setorial piloto** | Dono do serviço piloto | Fluxo no serviço, comunicação ao cidadão | Sim (no seu serviço) |
| **Ouvidoria-Geral estadual** | Recebe comentários | Fluxo de triagem, moderação, encaminhamento | Sim (fluxo de comentários) |
| **Jurídico SETDIG / DPO estadual** | Guardião LGPD | Base legal, aviso, retenção, dados sensíveis | Sim (LGPD) |
| **CGE (Controladoria)** | Auditoria | Aderência a Lei 13.460/2017 | Não (parecer consultivo) |
| **Cidadão-usuário (piloto)** | Validador prático | — | Não (medido por indicadores) |

## Quem lidera cada validação

- **Técnica:** STI.
- **Jurídica:** Jurídico SETDIG + DPO estadual, com apoio da ANPD como referência.
- **Operacional:** SGD + órgão setorial piloto.
- **Ouvidoria:** Ouvidoria-Geral do estado.
- **Decisão:** Secretário Executivo SETDIG.

## Stakeholders LGPD em detalhe

### DPO estadual
- Valida base legal do tratamento (Lei 13.709/2018 art. 7º III + art. 11 II "b" para PcD — decisão SGD 2026-08-25, avaliação identificada).
- Aprova prazo de retenção.
- Aprova texto do aviso de privacidade.
- Aprova política de pseudonimização em agregados históricos e regra de publicação (só agregado, corte ≥ 10).
- Valida o Relatório de Impacto à Proteção de Dados (RIPD) — necessário pela combinação de identificação + dado sensível (PcD).

### Ouvidoria
- Valida que comentários abertos não substituem canal formal de manifestação (Fala.MS continua sendo o canal para manifestações formais identificadas com garantia de resposta).
- Alinha regra de encaminhamento quando comentário revela problema grave (fraude, discriminação).
- Como a avaliação é identificada, definir com a Ouvidoria se e quando comentário aberto vira insumo para uma tratativa individual (por default, não — segue como sinal agregado para melhoria do serviço).

### ANPD
- Não valida diretamente, mas serve como referência de boas práticas para setor público.

## Referências externas úteis para stakeholders

- Central de Qualidade gov.br — para comparação com padrão federal.
- Portaria SGD/MGI 1.083/2025.
- Lei 13.460/2017 — Código de Defesa do Usuário.
- LGPD — Lei 13.709/2018 art. 6º (princípios), 7º (base legal), 11 (dado sensível), 18 (direitos do titular).

## Ver também

- [Estratégia de validação](estrategia.md)
- [Critérios de aceite](criterios-aceite.md)
- [LGPD](../04-cidadao/lgpd.md)
