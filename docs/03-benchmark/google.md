# Benchmark — Google Play (In-App Review API)

Marcadores: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`.

## Contexto

Google Play é a loja oficial de apps Android. Rating de app (1–5 estrelas + comentário) é peça central da descoberta e da confiança na loja. Em 2020, o Google lançou a **In-App Review API**: um card nativo que aparece dentro do app, sem redirecionar para a Play Store, e cuja UI/UX é rigidamente controlada pelo Google — o dev não pode customizar aparência, texto ou momento sem seguir regras estritas.

## Como funciona a avaliação

O desenvolvedor invoca `launchReviewFlow()` no momento que julgar apropriado. O Google exibe um card nativo com:
- Nome do app + ícone
- **1 a 5 estrelas**
- Campo de comentário opcional
- Botão de submit

O usuário pode fechar o card a qualquer momento. Após interagir (submetendo ou fechando), o controle volta ao app **sem mudar o fluxo do usuário** — o dev não sabe nem se o usuário avaliou nem qual foi a nota [FATO].

## Momento e gatilho

- [FATO] O desenvolvedor escolhe quando chamar. Google recomenda: "após o usuário ter experimentado o app o suficiente para dar feedback útil".
- [FATO] **PROIBIDO** interromper tarefas críticas do usuário.
- [FATO] **PROIBIDO** criar botão do tipo "Avalie o app" que dispare a API — porque o usuário pode já ter batido a quota e ficar frustrado com um card que não aparece.

## Perguntas e escala

| Item | Detalhe |
|------|---------|
| Pergunta | UI padrão do Google, não customizável |
| Escala | 1–5 estrelas |
| Nº perguntas | Uma tela — estrelas + comentário opcional |
| Campo aberto | Opcional |
| Dimensões | Uma — o app |
| Customização | **Zero** — dev não pode alterar tamanho, opacidade, forma do card |

## Uso pela plataforma

- [FATO] Rating alimenta a nota agregada do app na loja.
- [FATO] Comentário vira review público na página do app.
- [FATO] Desenvolvedor pode responder aos reviews via Play Console; usuário recebe notificação por e-mail quando o dev responde.

## Retorno ao usuário

- [FATO] O app "continua sem alterar o fluxo do usuário" — nenhum thank-you, nenhum bloqueio.
- [FATO] Se o dev responder ao review pela Play Console, o usuário recebe e-mail.

## Skip

- [FATO] Usuário pode fechar o card a qualquer momento; o dev **não pode** tratar isso como falha nem tentar novamente logo em seguida.
- [FATO] **Quota rígida do Google**: chamar `launchReviewFlow()` mais de uma vez em curto período (< ~1 mês por usuário) simplesmente não exibe o dialog. O Google enforça isso para evitar fadiga.
- [FATO] **PROIBIDO pré-screening**: o app **não pode** perguntar "Você está gostando?" ou "Você daria 5 estrelas?" antes de mostrar o card. Isso está explicitamente vedado pelas Google Play Developer Program Policies.
- [INTERPRETAÇÃO] A quota + a proibição de pré-screening juntas eliminam dois abusos comuns: bombardear o usuário e viés seletivo (só pedir review para quem parece feliz).

## Aprendizados aplicáveis a serviços públicos

1. **Anti-fadiga por design.** Quota máxima por usuário/período evita que o cidadão seja bombardeado toda vez que abre o Portal. Simples de implementar: cookie/registro de "última solicitação de avaliação" com cool-down de X dias.
2. **Proibir pré-screening é uma regra ética direta.** Portais governamentais **não devem** perguntar "Você teve uma boa experiência?" antes de mostrar o formulário — isso enviesa a amostra, filtra descontentes e destrói o valor da nota agregada. Google já fez o trabalho de justificar essa política; copiar.
3. **UI padronizada** reduz decisão do dev e uniformiza a experiência. No MS, definir um componente único de avaliação usado em **todos** os serviços do Portal — não deixar cada secretaria inventar o próprio.
4. **Não bloquear o fluxo.** Card leve, dispensável, sem consequência. Cidadão que fecha volta exatamente pra onde estava. Fundamental para não gerar ódio ao Portal.
5. **Não usar como CTA.** Botão "Avalie o Portal!" no menu é anti-padrão — quem clica é minoria polarizada (muito feliz ou muito irritado), enviesando a amostra. Melhor mostrar contextualmente após uso de fato.
6. **Responder ao review notifica o cidadão por e-mail** — canal simples de fechar o ciclo e mostrar que a nota foi lida. No MS: cidadão avalia, órgão responde, cidadão recebe e-mail. Fecha loop com custo baixo.

## Fontes

1. Android Developers — In-App Review API guide: https://developer.android.com/guide/playcore/in-app-review
2. Android Developers Blog — "Leverage the In-App Review API": https://android-developers.googleblog.com/2020/08/in-app-review-api.html
3. Google Play Console — Reviews: https://play.google.com/console/about/reviews/
4. XDA Developers — "Google's new In-App Review API": https://www.xda-developers.com/google-in-app-review-api-play-store-reviews-without-leaving-app/
5. Alchemer — "Google Play In-app Ratings and Reviews API Changes": https://www.alchemer.com/resources/blog/google-play-in-app-ratings-and-reviews-api-changes-whats-new-and-how-to-adapt-your-strategy/
6. Jake Lee — "Rapidly improving Play Store rating with an Android in-app review prompt helper": https://blog.jakelee.co.uk/play-store-rating-prompt/
7. ExtensionBooster — "How to Increase Android App Reviews: In-App Review API Playbook 2026": https://extensionbooster.net/blog/how-to-increase-android-app-reviews-in-app-review-api-playbook-2026/
