# Benchmark — Airbnb

Marcadores: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`.

## Contexto

Airbnb é a maior plataforma global de hospedagem entre pessoas. A reputação (tanto de anfitrião quanto de hóspede) é o principal ativo do sistema — sem confiança bilateral, ninguém aluga ou aluga para ninguém. O sistema de reviews é conhecido por dois mecanismos originais: **double-blind** e prazo rígido de **14 dias**.

## Como funciona a avaliação

Ao check-out, o relógio de 14 dias começa a correr para ambos os lados [FATO]. Hóspede avalia o anfitrião e vice-versa. Nenhum dos dois vê a review do outro até que:

- Ambos submetam, **ou**
- Os 14 dias expirem.

Isso caracteriza o **double-blind review**: cada lado escreve sem saber o que o outro escreveu, o que remove incentivo a retaliação ou reciprocidade forçada [FATO].

Quando a janela fecha (por submissão mútua ou expiração), as reviews são publicadas simultaneamente e passam a ser visíveis nos perfis públicos.

## Momento e gatilho

- [FATO] Cronômetro de 14 dias começa no check-out.
- [FATO] Notificação in-app + e-mail solicitando a avaliação.
- [INTERPRETAÇÃO] Lembretes periódicos durante a janela (padrão do produto).

## Perguntas e escala

| Item | Detalhe |
|------|---------|
| Nota geral | 1–5 estrelas (independente — **não é média** das subcategorias) [FATO] |
| Subcategorias | 6 dimensões: limpeza, precisão do anúncio, check-in, comunicação, localização, custo-benefício — cada uma 1–5 estrelas [FATO] |
| Review pública | Texto livre visível a futuros hóspedes |
| Feedback privado | Texto livre visível apenas ao anfitrião |
| Direção | Bidirecional — host avalia guest também (comunicação, limpeza, cumprimento de regras) |

**Não identificado** obrigatoriedade formal do texto público em fonte oficial. [INTERPRETAÇÃO] Estrelas gerais parecem ser o único campo estritamente obrigatório.

## Uso pela plataforma

- [FATO] Nota geral (não as subcategorias) determina a média do anúncio.
- [FATO] Reviews impactam ranking do anúncio e elegibilidade a status Superhost.
- [FATO] Anfitrião pode responder publicamente à review — sem prazo definido, resposta publica imediatamente.
- [INTERPRETAÇÃO] Guest também acumula reputação no perfil, visível a futuros hosts na hora da aprovação.

## Retorno ao usuário

- [FATO] Guest recebe a review pública do host no seu próprio perfil.
- **Não identificado** thank-you screen específica após submissão.
- [INTERPRETAÇÃO] O "retorno" é estrutural: a review do outro lado só aparece após o guest submeter — cria um incentivo natural para avaliar (se não avaliar, perde a chance de ver a review do host).

## Skip

- [FATO] Se o guest não avaliar em 14 dias, a janela fecha e a review do host (se submetida) publica sozinha.
- [INTERPRETAÇÃO] Skip é permitido tecnicamente, mas tem custo: perde-se a review pública do host e a chance de reciprocidade.

## Aprendizados aplicáveis a serviços públicos

1. **Double-blind é ouro em contexto de retaliação.** Se o Portal MS permitir que o servidor veja quem avaliou, aplicar mecanismo similar: servidor não vê nome do cidadão até responder (ou nunca vê). Isso protege ambos os lados de viés.
2. **Prazo finito** (14 dias) mantém as reviews fresquíssimas ao contexto. Aplicável ao Portal.
3. **Múltiplas dimensões só se o serviço for rico.** As 6 categorias do Airbnb (limpeza, comunicação etc.) fazem sentido porque hospedagem tem muitos atributos. Serviço público geralmente é mais transacional — 1–3 dimensões bastam (ex: facilidade, atendimento, resolutividade).
4. **Nota geral independente das subcategorias** é interessante psicologicamente: obriga o avaliador a pensar duas vezes. "O serviço foi 4 na comunicação e 5 no atendimento — no geral, quanto?" evita nota-média enganosa.
5. **Feedback privado** (visível apenas ao prestador, não público) é canal poderoso para melhoria interna sem expor o órgão a ranking negativo por detalhe operacional pequeno.
6. **Direito de resposta pública do prestador** cria simetria — o cidadão vê que sua reclamação foi lida e respondida, não caiu no vazio.

## Fontes

1. Hostfully — "Airbnb Review Policy Explained (2026)": https://www.hostfully.com/blog/airbnb-review-policy/
2. Uplisting — "Airbnb Review Policy: Tips, Removal, and Host Guidelines": https://www.uplisting.io/blog/airbnb-review-policy-quick-guide
3. Houst — "Airbnb Reviews: How They Work for Hosts (2026)": https://www.houst.com/blog/airbnb-review
4. Comunidade Airbnb — "Reviews: how does the 14 days time frame work": https://community.withairbnb.com/t5/Help-with-your-business/Reviews-how-does-the-14-days-time-frame-work/m-p/2261439
5. STR Assistance — "How to Leave a Review on Airbnb After 14 Days": https://strassistance.com/how-to-leave-a-review-on-airbnb-after-14-days/
6. arXiv — "More Reviews May Not Help: Evidence from Incentivized First Reviews on Airbnb": https://arxiv.org/pdf/2112.09783
7. Touchstay — "50+ Airbnb Guest Review Templates & Examples for Hosts": https://touchstay.com/blog/airbnb-guest-review-templates
