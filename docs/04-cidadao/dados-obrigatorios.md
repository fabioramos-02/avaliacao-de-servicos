# Dados coletados — o que é obrigatório, opcional e proibido

Tabela orientadora do que a avaliação do Portal MS pode e não pode capturar, com base legal e retenção. Detalhamento em [LGPD](lgpd.md).

## Tabela

| Dado | Coletado? | Base legal LGPD | Retenção | Forma |
|---|---|---|---|---|
| Nota (1–5 estrelas) | **Obrigatório** para envio | Execução de política pública (art. 7º III) + Lei 13.460/2017 | Bruto: 5 anos. Agregado: indefinido | Inteiro 1–5 |
| Motivos positivos (6 cards, até 3) | Opcional | Consentimento tácito ao enviar (art. 7º I) | Bruto: 5 anos. Agregado: indefinido | Array de códigos |
| Comentário aberto | Opcional | Consentimento (art. 7º I) | Bruto: 5 anos (com moderação) | Texto até 2000 chars |
| Autodeclaração PcD | Opcional | **Consentimento explícito** (art. 11 I) — dado sensível | Bruto: 3 anos | Booleano |
| id_serviço | Sempre (metadado) | Não é dado pessoal | Indefinido | UUID/inteiro |
| id_órgão | Sempre (metadado) | Não é dado pessoal | Indefinido | UUID/inteiro |
| Canal (web/mobile) | Sempre (metadado) | Não é dado pessoal | Indefinido | Enum |
| Timestamp | Sempre (metadado) | Necessário para agregação temporal | Bruto: 5 anos | ISO-8601 |
| id_sessão (hash) | Sempre, para deduplicação | Interesse legítimo — evitar spam | 90 dias | SHA-256 truncado |
| IP do cidadão | **Não coletar** | — | — | — |
| CPF | **Não coletar** | — | — | — |
| E-mail | **Não coletar** | — | — | — |
| Nome | **Não coletar** | — | — | — |
| Município (exato/CEP) | **Não coletar** | — | — | — |
| Município agregado (mesorregião) | Opcional futuro | Anonimizado (art. 12) | Agregado | Enum |

## Princípios

1. **Anônimo por default.** Cidadão nunca precisa se identificar para avaliar. Convergente com gov.br.
2. **Minimização.** Se um dado não vira ação, não coleta (LGPD art. 6º III).
3. **Sensível só com consentimento explícito.** Autodeclaração PcD é o único dado sensível — bloco visualmente separado, com aviso claro de finalidade.
4. **Metadados técnicos não identificam.** id_serviço, id_órgão, canal e timestamp são operacionais, não pessoais.
5. **Retenção proporcional.** Dado bruto 5 anos (auditoria + série histórica); dado sensível 3 anos (uso mais restrito).

## O que fica de fora — e por quê

- **IP:** identifica indiretamente. Não usamos para nada (dedupe é feito por hash de sessão). Não coletar.
- **CPF/e-mail/nome:** quebrariam o anonimato e criariam expectativa de retorno que órgão nem sempre pode cumprir. Se cidadão quer resposta formal, canal é Ouvidoria / Fala.MS.
- **Geolocalização precisa:** sem uso operacional; agrega risco. Se algum dia for útil, coletar só mesorregião (agregado).
- **Perfil demográfico (idade, escolaridade, renda):** não usamos; aumenta drop-off; risco LGPD.

## Compromisso público

O Portal MS assume, na tela de avaliação, aviso claro:

> **Sua avaliação é anônima.** Não coletamos CPF, e-mail ou nome. Seu comentário e sua nota são usados para melhorar este serviço. Você pode não avaliar sem prejuízo ao serviço.

Ver texto completo em [LGPD — Aviso de privacidade no ato](lgpd.md).
