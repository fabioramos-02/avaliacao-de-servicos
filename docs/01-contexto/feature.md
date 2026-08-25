# O que este estudo investiga

## Pergunta central

Como o Portal de Serviços do MS deve pedir ao cidadão que avalie cada serviço digital que ele usa?

Não é uma pergunta de design isolada. Ela mistura política pública (Lei 13.460/2017), padrão federal (gov.br), experiência do usuário, LGPD e capacidade operacional do estado.

## Ponto de partida assumido

**O padrão nacional é o gov.br.** A Central de Qualidade coordenada pelo MGI padronizou a Ferramenta de Avaliação de Serviços via Portaria SGD/ME 548/2022. Órgãos federais já usam. Estados que se conectam à plataforma gov.br têm acesso ao mesmo instrumento.

Por consequência, o padrão do estudo é: **adotar o modelo gov.br como base e justificar qualquer divergência.**

## Recorte

- Serviços **digitais** publicados no Portal MS (não engloba atendimento presencial).
- **Somente serviços que nascem no orquestrador da X-VIA.** Serviços legados fora do orquestrador ficam de fora desta primeira onda — decisão SGD de 2026-08-25. Justificativa: o orquestrador é o único ponto em que o Portal tem sinal confiável de que o serviço foi acessado e de quem o acessou; sem esse sinal, não há como fechar o ciclo cidadão → avaliação.
- Avaliação **transacional** — após o cidadão usar um serviço específico.
- Avaliação **relacional** do Portal como marca fica separada (candidata a NPS periódico).

## O que sai deste estudo

1. **Modelo proposto** — pergunta, escala, opcionais, fluxo.
2. **Especificação de indicadores** — o que a gestão passa a ver.
3. **Corte LGPD** — quais dados podem/devem/não devem ser coletados.
4. **Estratégia de validação** — quem valida, com que critério, em quanto tempo.
5. **Recomendação executável** — se o Portal fosse ligar isso amanhã, como seria.

## O que não sai deste estudo

- Código, contrato, integração técnica.
- Painel de BI pronto (só especificação).
- Pesquisa qualitativa com cidadãos (é um próximo passo recomendado).

## Como o estudo foi feito

Pesquisa dividida em ondas por agentes especializados: modelos de avaliação, benchmark gov.br (âncora), benchmark de mercado (referência secundária), UX/Service Design, Dados/Analytics, LGPD/Governança e consolidação. Toda afirmação factual tem fonte registrada em `pesquisa/fontes.md`.
