# Estratégia de validação

Como a proposta será testada e ajustada antes de virar implementação.

## Objetivo da fase de validação

Confirmar que o modelo proposto:

1. **É viável tecnicamente** no stack atual do Portal MS.
2. **É aderente ao marco legal** (Lei 13.460/2017, LGPD, Portaria SGD federal).
3. **Serve às áreas usuárias** (órgãos setoriais, ouvidoria, direção SETDIG).
4. **Funciona com o cidadão** (mínimo teste piloto qualitativo).

## Etapas

| # | Etapa | Prazo estimado | Responsável | Saída |
|---|---|---|---|---|
| 1 | Validação técnica | 2 semanas | STI + arquitetura | Nota técnica de viabilidade |
| 2 | Validação jurídica/LGPD | 2 semanas | Jurídico SETDIG + DPO estadual | Parecer aprovando base legal |
| 3 | Validação com órgãos setoriais | 3 semanas | SGD + órgãos piloto | Ata com ajustes solicitados |
| 4 | Validação com ouvidoria | 1 semana | SGD + Ouvidoria-Geral | Ajustes de moderação e fluxo |
| 5 | Piloto com cidadão | 4 semanas | SGD + serviço piloto | Relatório com nota média, taxa de resposta, comentários |
| 6 | Consolidação e go/no-go | 1 semana | Direção SETDIG | Decisão formal |

Prazo total ≈ **13 semanas** (~3 meses) até decisão de implantação em escala.

## Serviço piloto — critérios de escolha

O piloto precisa de:

- Volume mensal ≥ 500 conclusões (para obter N estatisticamente relevante em 4 semanas).
- Fluxo 100% digital (avaliação ao fim do serviço, sem etapa presencial).
- Órgão setorial engajado (dispõe de gestor que vai olhar o painel).
- Baixo risco jurídico (não coleta dado sensível no serviço-mãe).

Candidatos naturais: emissão de 2ª via de documentos, consulta a débitos, agendamento simples.

## Hipóteses a testar no piloto

| Hipótese | Como testar | Critério de aprovação |
|---|---|---|
| Taxa de resposta ≥ 5% dos usuários únicos | Contar avaliações ÷ conclusões | ≥ 5% em 4 semanas |
| Nota média ≥ 4,0 | Média das notas coletadas | ≥ 4,0 no fechamento |
| Drop-off no formulário < 30% | (iniciou − enviou) ÷ iniciou | < 30% |
| Comentário aberto útil ≥ 20% das respostas | Amostra manual de 100 comentários | ≥ 20% acionáveis |
| Zero incidente de LGPD | Auditoria DPO ao fim do piloto | Sem ocorrência |
| Painel do gestor é usado | Nº de acessos únicos no período | ≥ 1 acesso/semana pelo gestor |

## O que muda depois do piloto

- Se todas as hipóteses passam → **go** para escala progressiva (5 serviços/mês).
- Se 1–2 hipóteses falham → ajustar ponto específico + repetir piloto (2 semanas).
- Se falham 3+ → revisão da proposta com stakeholders.

## Governança da validação

- **Comitê semanal** durante piloto: SETDIG (SGD + STI), órgão setorial, Ouvidoria.
- **Painel de acompanhamento** visível a todos.
- **Registro de decisões** em [Decisões](../07-conclusao/decisoes.md).

## Ver também

- [Stakeholders](stakeholders.md)
- [Critérios de aceite](criterios-aceite.md)
- [Modelo proposto](../05-proposta/modelo-proposto.md)
