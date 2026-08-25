# Dados coletados — o que é obrigatório, opcional e proibido

> Decisão SGD 2026-08-25: avaliação passa a ser **identificada**. O cidadão já está logado no Portal para acessar o serviço via orquestrador X-VIA; a avaliação usa a mesma sessão e registra id do usuário + município do serviço finalístico. Base LGPD sai de "anonimato + consentimento" e vai para **execução de política pública** (art. 7º III + art. 11 II "b").

Tabela orientadora do que a avaliação do Portal MS pode e não pode capturar, com base legal e retenção. Detalhamento em [LGPD](lgpd.md).

## Tabela

| Dado | Coletado? | Base legal LGPD | Retenção | Forma |
|---|---|---|---|---|
| Nota (1–5 estrelas) | **Obrigatório** para envio | Execução de política pública (art. 7º III) + Lei 13.460/2017 | Bruto: 24 meses. Agregado: indefinido | Inteiro 1–5 |
| Motivos positivos (6 cards, até 3) | Opcional | Execução de política pública (art. 7º III) | Bruto: 24 meses. Agregado: indefinido | Array de códigos |
| Comentário aberto | Opcional | Execução de política pública (art. 7º III) | Bruto: 12 meses (com triagem) | Texto até 2000 chars |
| Autodeclaração PcD | Opcional | **Execução de política pública para dado sensível** (art. 11 II "b") | Bruto: 24 meses | Booleano |
| id_usuario (Portal / gov.br) | **Sempre** (vem do login) | Execução de política pública (art. 7º III) | Bruto: 24 meses. Após: pseudonimizado em agregados históricos | Identificador do IdP |
| Município do serviço finalístico | **Sempre** (vem do orquestrador X-VIA) | Execução de política pública (art. 7º III) | Bruto: 24 meses. Agregado: indefinido | Código IBGE do município |
| id_servico | Sempre (metadado) | Não é dado pessoal | Indefinido | UUID/inteiro |
| id_orgao | Sempre (metadado) | Não é dado pessoal | Indefinido | UUID/inteiro |
| id_execucao_orquestrador (X-VIA) | Sempre (metadado) | Necessário para vincular avaliação à execução do serviço e evitar duplicidade | 24 meses | UUID |
| Canal (web/mobile) | Sempre (metadado) | Não é dado pessoal | Indefinido | Enum |
| Timestamp | Sempre (metadado) | Necessário para agregação temporal | Bruto: 24 meses | ISO-8601 |
| IP completo | **Não coletar** | — | — | — |
| CPF | **Não coletar** (o vínculo com o cidadão é feito pelo id do IdP, não pelo CPF em claro) | — | — | — |
| Nome | **Não coletar** no formulário (vem por referência via id do IdP, se necessário para retorno) | — | — | — |
| E-mail | **Não coletar** no formulário (usado apenas pelo disparador de e-mail transacional, via id do IdP) | — | — | — |
| Telefone | **Não coletar** | — | — | — |
| Endereço | **Não coletar** | — | — | — |
| Geolocalização precisa (GPS) | **Não coletar** | Município do serviço finalístico já cobre a necessidade | — | — |
| Tipo específico de deficiência | **Não coletar** | Autodeclaração fica em Sim/Não | — | — |

## Princípios

1. **Identificação vem do login, não de campo extra.** Cidadão já está logado no Portal para acessar o serviço via X-VIA — o formulário não pede CPF, nome ou e-mail. A identificação é derivada do id do IdP.
2. **Minimização.** Se um dado não vira ação ou indicador, não coleta (LGPD art. 6º III). A identificação existe para permitir retorno ao cidadão, análise por perfil/localização e prevenção de duplicidade — não para expor dado pessoal em painel.
3. **Sensível com base específica.** Autodeclaração PcD entra por execução de política pública para dado sensível (art. 11 II "b"), em bloco visualmente separado, com aviso claro de finalidade.
4. **Metadados técnicos não identificam sozinhos.** id_servico, id_orgao, canal e timestamp são operacionais, não pessoais.
5. **Retenção proporcional.** Dado bruto 24 meses; agregado indefinido; comentário aberto 12 meses (janela mais curta pelo risco maior de reidentificação por texto livre).
6. **Publicação sempre agregada.** Painel público e dados abertos só exibem agregados com corte mínimo de amostra (≥10 avaliações).

## O que fica de fora — e por quê

- **IP completo:** sem uso; a prevenção de duplicidade usa `id_usuario + id_execucao_orquestrador`.
- **CPF em claro no formulário:** o vínculo com o cidadão vem do id do IdP; não há necessidade de circular CPF no payload de avaliação.
- **Geolocalização precisa:** município do serviço finalístico é suficiente para a análise regional; GPS é excessivo.
- **Perfil demográfico (idade, escolaridade, renda):** não usamos; aumenta drop-off; risco LGPD sem contrapartida.

## Compromisso público

O Portal MS assume, na tela de avaliação, aviso claro:

> **Sua avaliação é identificada.** Como você está logado no Portal MS para acessar este serviço, sabemos que é você quem está avaliando e sabemos em qual município o serviço foi prestado. Usamos isso para melhorar o serviço, entender diferenças regionais e — se você quiser — voltar a falar com você sobre esta avaliação. Não pedimos CPF, telefone ou endereço novos. Base legal: execução de política pública (LGPD art. 7º III e art. 11 II "b") em cumprimento à Lei 13.460/2017. Você pode não avaliar sem prejuízo ao serviço.

Ver texto completo em [LGPD — Aviso de privacidade no ato](lgpd.md).
