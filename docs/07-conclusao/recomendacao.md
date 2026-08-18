# Recomendação

## A recomendação em uma linha

Adotar o **modelo gov.br de avaliação de serviços** no Portal do MS, com adaptação institucional mínima (cabeçalho MS + painel próprio), rodando piloto de 3 meses em serviço de alta demanda antes de escalar.

## Por quê

1. **Padrão nacional.** Portaria SGD/MGI 1.083/2025 (revisora da 548/2022) já formatou o instrumento para toda a Administração Federal. Divergir gera custo sem ganho.
2. **Comparabilidade.** MS entra no mesmo referencial dos demais estados que caminham para adesão.
3. **Aderência legal.** Lei 13.460/2017 exige avaliação; LGPD exige minimização; o modelo gov.br já foi desenhado para atender ambos.
4. **Baixo risco técnico.** Formulário simples, sem integrações complexas, sem dado sensível fora do bloco PcD.
5. **Baixo atrito para o cidadão.** 1 pergunta obrigatória + 3 opcionais; ~5s no mínimo, ~80s no máximo.

## O modelo em uma tela

- Pergunta: **"Como foi a sua experiência com o serviço?"**
- Escala: 5 estrelas rotuladas (Péssima / Ruim / Mais ou menos / Boa / Excelente).
- 3 opcionais: motivos positivos (até 3 de 6 cards) + campo aberto (2000 chars) + autodeclaração PcD.
- Momento: fim do serviço, convite único, **nunca bloqueia**.
- Anônimo por default.
- Métrica: nota média + % Satisfeitos (top-2-box).
- Alvo: nota ≥ 4,0 e % Satisfeitos ≥ 80%.

Detalhamento em [Modelo proposto](../05-proposta/modelo-proposto.md).

## O que muda para o cidadão

- Passa a ter voz sobre cada serviço digital que usa.
- Pode escolher não avaliar sem prejuízo.
- Vê nota agregada dos outros cidadãos na página do serviço.
- Sabe que sua opinião chega ao órgão responsável.

## O que muda para a gestão

- Nota mensal por serviço para acompanhar.
- Ranking interno para priorizar melhoria.
- Comentários abertos triados pela Ouvidoria.
- Alertas automáticos para queda ou nota baixa recorrente.
- Base para atender Lei 13.460/2017 art. 23 (publicação obrigatória).

## O que a SETDIG precisa aprovar para começar

| Decisão | Quem decide | Prazo sugerido |
|---|---|---|
| Adotar modelo gov.br | Secretário Executivo SETDIG | 2 semanas |
| Definir serviço piloto | SGD + órgão setorial | 4 semanas |
| Aprovar aviso LGPD | Jurídico SETDIG + DPO estadual | 2 semanas |
| Alocar time técnico | STI | 4 semanas |
| Alinhar Ouvidoria | Ouvidoria-Geral | 2 semanas |
| Go/no-go pós-piloto | Secretário Executivo | 13 semanas |

## Riscos e mitigações

| Risco | Impacto | Mitigação |
|---|---|---|
| Baixa taxa de resposta | Dado pouco representativo | Convite discreto mas visível; mensuração no piloto |
| Comentários abertos usados como canal de manifestação | Cidadão frustrado sem retorno | Aviso claro + encaminhamento para Fala.MS |
| Divergência entre painel MS e federal | Confusão de indicadores | Publicar mesma fórmula e escala do gov.br |
| Mudança na Portaria federal | Precisa acompanhar | Monitorar SGD/MGI trimestralmente |
| Órgão setorial não usa o painel | Feedback vira ruído | Comitê mensal por Secretaria; acesso obrigatório do gestor |

## O que não recomendamos (e por quê)

- **Não** usar NPS como métrica principal. Serviço público monopolista não faz sentido perguntar se "recomenda".
- **Não** exigir login para avaliar. Anonimato preserva participação.
- **Não** coletar CPF, e-mail ou dados demográficos. Sem uso operacional; risco LGPD.
- **Não** transformar avaliação em canal de reclamação com retorno individual. Isso é a Ouvidoria.
- **Não** bloquear conclusão do serviço em avaliação. Proibido por Portaria 548 art. 7º §3º.

## Próximos passos

Ver [Próximos passos](proximos-passos.md).
