# Decisões

Registro das decisões tomadas ao longo do estudo. Cada linha responde: **o que foi decidido, quando, por quem, com base em quê**.

## Decisões do estudo

| # | Data | Decisão | Quem decidiu | Base |
|---|---|---|---|---|
| D1 | 2026-08-18 | Adotar gov.br como referência principal do estudo | Chefia SGD | Portaria SGD/MGI 1.083/2025 é padrão nacional |
| D2 | 2026-08-18 | Manter linguagem simples, macro estratégica, sem jargão de backlog | Chefia SGD | Público-alvo é diretoria e gestão sênior |
| D3 | 2026-08-18 | Escala 5 estrelas rotuladas (não NPS, não emojis) | Estudo (Onda 2a) | Aderência gov.br + comparabilidade nacional |
| D4 | 2026-08-18 | Anônimo por default; sem CPF, e-mail ou nome | Estudo (Onda 2c) | LGPD art. 6º III + prática gov.br |
| D5 | 2026-08-18 | Métrica principal: nota média + % Satisfeitos | Estudo (Onda 2b) | Duplo indicador cobre cidadão e gestor |
| D6 | 2026-08-18 | Recomendação: alternativa B (gov.br + adaptação MS leve) | Estudo (matriz de decisão) | Score 163/195 na matriz |
| D7 | 2026-08-18 | Convite único, nunca bloquear | Estudo (Onda 2a) | Portaria 548 art. 7º §3º |
| D8 | 2026-08-18 | Retenção: 5 anos bruto, 3 anos dado sensível PcD | Estudo (Onda 2c) | LGPD art. 6º III + proporcionalidade |
| D9 | 2026-08-18 | Piloto de 3 meses antes de escalar | Estudo (Onda 3) | Reduz risco + gera dado para calibração |
| D10 | 2026-08-25 | **Revoga D4.** Avaliação passa a ser identificada (usuário logado no Portal + município do serviço finalístico). Base LGPD: execução de política pública (art. 7º III + art. 11 II "b"), não mais anonimato. | SGD | Permite retorno ao cidadão, análise por perfil/localização e integração com histórico do Portal |
| D11 | 2026-08-25 | Escopo restrito a serviços que nascem no orquestrador X-VIA. Serviços fora ficam de fora desta onda. | SGD | Sem orquestrador não há sinal confiável de conclusão do serviço |
| D12 | 2026-08-25 | Ajuste da retenção: 24 meses no estado identificado, 12 meses comentário aberto, pseudonimização em agregado histórico. Revoga D8. | SGD | Combina exercício de direitos do titular, análise anual e redução de risco |

## Decisões pendentes (a tomar na validação)

| # | Decisão pendente | Quem decide | Prazo sugerido |
|---|---|---|---|
| P1 | Adotar formalmente o modelo | Secretário Executivo SETDIG | 2 semanas |
| P2 | Escolher serviço piloto (obrigatoriamente entre os que nascem no orquestrador X-VIA) | SGD + órgão setorial | 4 semanas |
| P3 | Aprovar texto do aviso LGPD (versão identificada) + validar RIPD | Jurídico + DPO | 2 semanas |
| P4 | Definir Secretaria responsável pelo painel gestor | SETDIG | 4 semanas |
| P5 | Definir se integração futura com API gov.br entra em fase 2 (nota: divergência de identificação exige alinhamento) | Direção SETDIG | Pós-piloto |
| P6 | Definir cadência de publicação em dados abertos MS (somente agregado) | SETDIG + órgão de dados abertos estadual | Pós-piloto |
| P7 | **Reunião com Maycon:** entender como o sistema do órgão sinaliza ao X-VIA que o serviço foi concluído. Bloqueia proposta prévia de retorno por e-mail. | SGD + X-VIA | Imediato |
| P8 | Definir caminho de retorno do cidadão ao Portal após uso do serviço: **proposta prévia é envio de e-mail com link único de avaliação** (alternativa considerada e menos preferida: tela de retorno ao Portal). Confirmar após P7. | SGD | Após P7 |
| P9 | Publicar ato normativo estadual instituindo o Modelo de Qualidade dos Serviços Digitais do MS com previsão expressa de coleta identificada | SETDIG + PGE-MS | Antes do go-live |
| P10 | Publicar contato do DPO estadual (bloqueio para aviso de privacidade) | SETDIG + PGE-MS | Antes do go-live |

## Formato de registro

Toda nova decisão tomada durante validação e implementação deve ser registrada aqui, com:

- Número sequencial (D10, D11, ...)
- Data ISO (AAAA-MM-DD)
- Descrição objetiva
- Quem decidiu
- Base (norma, dado do piloto, deliberação)

Para decisões técnicas que exigem trilha maior, referenciar Diário de Decisões separado quando existir.
