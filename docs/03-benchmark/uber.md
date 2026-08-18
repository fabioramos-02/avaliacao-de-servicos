# Benchmark — Uber

Marcadores: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`.

## Contexto

Uber é a maior plataforma global de mobilidade urbana on-demand. O sistema de rating é bidirecional (motorista avalia passageiro e vice-versa), anônimo e com peso operacional real: motoristas com nota baixa perdem acesso à plataforma; passageiros mal avaliados podem ser desativados.

## Como funciona a avaliação

Ao final de cada viagem, uma tela in-app pede que o passageiro atribua **1 a 5 estrelas**. A tela é bloqueante: o passageiro **não pode reservar outra corrida sem avaliar a última** [FATO — Uber Help].

Após dar a nota:
- **Se 5 estrelas** → o app oferece uma lista de "compliments" (elogios pré-definidos: "Great conversation", "Clean car", "Expert navigation" etc.).
- **Se menos de 5 estrelas** → o app oferece uma lista de "common issues" para especificar o problema. Comentário livre é opcional.

Em seguida, aparece a tela de gorjeta (opcional, disponível por até 30 dias após a corrida).

## Momento e gatilho

- [FATO] Tela in-app aparece imediatamente após o término da viagem.
- [FATO] Se o usuário fechar o app sem avaliar, a avaliação será exigida antes da próxima corrida (soft-lock).
- [INTERPRETAÇÃO] Notificação push também é comum (padrão do app), embora não confirmado em fonte primária consultada.

## Perguntas e escala

| Item | Detalhe |
|------|---------|
| Pergunta principal | Referida como "rate your trip" nas fontes oficiais; texto literal não confirmado |
| Escala | 1–5 estrelas |
| Perguntas condicionais | Sim: compliment (5★) ou motivo (<5★) |
| Campo aberto | Opcional em todos os casos |
| Dimensões | Uma única — a viagem/motorista como um todo (sem sub-scores) |

## Uso pela plataforma

- [FATO] Nota do motorista = média dos últimos **500 ratings** de passageiros.
- [FATO] Ratings são **anônimos** — nem motorista nem passageiro vê o rating individual de uma viagem específica.
- [FATO] Sistema exclui automaticamente ratings de passageiros que "frequentemente dão notas baixas" e viagens afetadas por fatores externos (trânsito, cancelamento etc.).
- [FATO] Notas consistentemente baixas → menos corridas e possível desativação.
- [FATO] Notas altas → benefícios (Uber Pro, categorias premium).
- **Não identificado** threshold numérico oficial de desativação. Imprensa cita ~4,6, mas Uber não confirma publicamente.
- [FATO] Rider (passageiro) só passa a ter nota exibida após 5 viagens; drivers começam com 5,00 e a nota flutua até acumular 100+ ratings.

## Retorno ao usuário

- **Não identificado** thank-you screen ou resposta ao passageiro após submissão.
- [INTERPRETAÇÃO] Passageiro apenas volta à Home após avaliar. Não existe canal para o motorista responder à nota do passageiro (e vice-versa) — ratings são anônimos por design.

## Skip

- [FATO] Passageiro pode **adiar**, mas não pode reservar próxima viagem sem avaliar.
- [INTERPRETAÇÃO] Efetivamente obrigatório para uso continuado. Único case do benchmark com essa característica.

## Aprendizados aplicáveis a serviços públicos

1. **Ancorar no momento do evento.** A avaliação aparece na hora em que a experiência ainda está fresca — passa a taxa de resposta é alta porque não depende de o usuário lembrar de voltar depois. Aplicável ao Portal: mostrar a avaliação na tela final de conclusão do serviço.
2. **Uma pergunta principal + tags condicionais.** O fluxo Uber é radicalmente simples: uma nota, depois um refinamento *só se necessário*. No MS: nota geral (1–5), depois motivos padronizados (só se <4).
3. **NÃO copiar o soft-lock.** Bloquear próxima solicitação até avaliar é rating pressure — gera respostas apressadas, viés positivo (5★ automático para se livrar da tela) e ressentimento. Serviço público não pode se dar ao luxo de forçar avaliação. Uber é criticado justamente por isso.
4. **Anonimato do avaliador é essencial em contexto sensível.** No MS, cidadão precisa ter garantia de que a avaliação negativa não vai gerar retaliação do órgão avaliado. Adotar anonimato pelo menos para o servidor final (agregado por órgão, sim; nome do cidadão, não).
5. **Ponderação inteligente.** Uber exclui ratings de usuários abusivos e de contextos externos. No MS, ponderar: excluir avaliação de solicitações canceladas por erro do cidadão, ou reduzir peso de avaliadores que só dão 1 ou 5 sistematicamente.
6. **Compliments** (o lado positivo do rating condicional) valorizam bons prestadores. No MS: se cidadão dá 5★, oferecer "elogios" pré-definidos ("atendimento cordial", "prazo rápido") para acumular reconhecimento para o órgão/servidor.

## Fontes

1. Uber Help — Rating a driver: https://help.uber.com/riders/article/rating-a-driver?nodeId=478d7463-99cb-48ff-a81f-0ab227a1e267
2. Uber Help — Rating FAQs: https://help.uber.com/en/riders/article/rating-faqs/?nodeId=0539e772-747c-49a7-8c26-f28c65e6f14d
3. Uber Help — Understanding ratings (driver): https://help.uber.com/en/driving-and-delivering/article/understanding-ratings?nodeId=9e240708-a894-43d7-b19d-13061a4fbe5a
4. Uber Driver App Basics — How ratings work: https://www.uber.com/us/en/drive/basics/how-ratings-work/
5. Uber Blog — How the Uber rating system works: https://www.uber.com/en-EG/blog/how-the-uber-rating-system-works
6. Ridester — Uber Driver Ratings: https://www.ridester.com/uber-driver-ratings/
7. Ridester — What Your Uber Rider Rating Means: https://www.ridester.com/uber-rider-ratings/
