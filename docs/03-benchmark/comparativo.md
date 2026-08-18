# Comparativo — Benchmark de avaliação

Tabela consolidada dos cases estudados. Cada linha resume um modelo diferente de coleta de avaliação. Toda afirmação factual tem fonte em `pesquisa/fontes.md`.

## Tabela

| Case | Momento | Escala | Nº perguntas | Campo aberto | Métrica pública | Uso do feedback |
|---|---|---|---|---|---|---|
| **gov.br (âncora)** | Ao concluir serviço, convite único não bloqueante | 5 estrelas rotuladas (Péssima→Excelente) | 1 obrigatória + 3 opcionais | Sim, opcional, 2000 chars | Nota média + nº avaliações por serviço; ranking público | Painel público + painel restrito do gestor; entra em ranking mensal |
| **GOV.UK** | Botão persistente "Is this page useful?" + surveys eventuais | Sim/Não + rating adicional | Variável por serviço | Sim, obrigatório em surveys | Satisfaction score publicado em `data.gov.uk` | Alimenta Service Standard; equipe do serviço age |
| **iFood** | Pós-entrega, push + tela in-app | 5 estrelas + tags | 3 dimensões (entregador, restaurante, embalagem) | Opcional | Nota média por restaurante (público) | Impacta ranking do restaurante; entregador pode ser desligado |
| **Uber** | Pós-viagem, tela bloqueante | 5 estrelas + tags condicionais (nota < 4) | 1 principal + tags | Opcional | Nota média motorista/passageiro (só para operação) | Motorista abaixo de nota mínima é descredenciado |
| **Airbnb** | 14 dias após checkout, e-mail + tela | Estrelas por dimensão (limpeza, localização etc.) + texto | 6+ dimensões | Sim, obrigatório | Nota pública do imóvel e do hóspede | Impacta ranking e Superhost |
| **Google (Play/Maps)** | In-app após uso; card recorrente | 5 estrelas + comentário | 1 principal | Opcional | Nota média pública | Impacta ranking do app/local |
| **Amazon** | E-mail dias após entrega | 5 estrelas + título + texto | 3 (nota, título, corpo) | Sim, obrigatório | Nota média + reviews públicos | Impacta ranking e compra futura |

## Padrões comuns observados

1. **CSAT dominante.** Todos usam variantes de 1–5 (estrelas ou notas). NPS aparece só em pesquisas relacionais, nunca em avaliação transacional pontual.
2. **Momento = pós-conclusão.** Todos pedem depois que o usuário terminou a tarefa — nunca no meio.
3. **Campo aberto quase sempre presente.** Serviço público (gov.br, GOV.UK) e comércio (Amazon, Airbnb) coincidem.
4. **Convite único.** Ninguém repete pedido no mesmo dia. gov.br e GOV.UK deixam explícito no manual.
5. **Retorno público visível ao próximo usuário.** iFood/Uber/Amazon expõem nota; gov.br também (painel Central de Qualidade). GOV.UK expõe em `data.gov.uk`.

## Diferenças relevantes para governo

- **Governo não bloqueia.** gov.br e GOV.UK **nunca** exigem avaliação para concluir serviço (art. 7º §3º Portaria 548/2022 — princípio jurídico). Uber e iFood podem tornar a tela quase inescapável no app.
- **Governo é anônimo por default.** Cases privados operam com conta logada; gov.br não pede CPF.
- **Governo mostra dimensões qualificadoras.** Os 6 cards do gov.br não têm equivalente direto nos apps privados (que preferem tags livres ou dimensões técnicas como "limpeza").
- **Governo publica em dados abertos.** GOV.UK e gov.br publicam agregados; privados não.

## O que traz para a proposta do MS

- Adotar **CSAT-5 rotulado**: convergente com gov.br e com práticas de mercado.
- **Convite único e não bloqueante**: exigência legal + boa prática universal.
- **Campo aberto opcional**: convergente com todos os cases; usar limite de 2000 chars como gov.br.
- **Anônimo por default**: cumpre LGPD e alinha com gov.br.
- **Publicar nota agregada**: alinha com Lei 13.460/2017 art. 23 e com prática dos cases.

Detalhes em [Modelo proposto](../05-proposta/modelo-proposto.md).
