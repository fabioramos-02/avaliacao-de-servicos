# Notas cruas — Benchmark de produtos digitais

Marcadores: `[FATO]` (fonte primária/secundária confirma), `[INTERPRETAÇÃO]` (inferência apoiada em fonte), `[HIPÓTESE]` (plausível, sem fonte direta).

---

## iFood

### Momento
- [FATO] Avaliação fica aberta por até 7 dias após conclusão do pedido. Fonte: Central de Ajuda iFood (institucional).
- [FATO] Aparece assim que o app é reaberto após finalização do pedido, com as estrelas visíveis na tela. Fonte: Central de Ajuda iFood.

### Gatilho
- [FATO] Reabertura do app (tela de estrelas), acesso à página "Pedidos" e notificações push. Fonte: Central de Ajuda iFood.

### Pergunta
- [FATO] Fluxo com três blocos: (1) estabelecimento — estrelas; (2) entrega — "O pedido chegou no tempo informado?" Sim/Não; (3) iFood — "De 0 a 10, quanto você nos recomendaria" (NPS). Fontes: Central de Ajuda iFood; Saipos.
- [INTERPRETAÇÃO] O texto exato do prompt inicial ("Como foi a sua experiência?") aparece em Saipos; não localizado literalmente na fonte oficial.

### Escala
- [FATO] Restaurante: 1–5 estrelas. Entrega: binária (Sim/Não). iFood: NPS 0–10. Fontes: Central de Ajuda iFood; Saipos.
- [FATO] Nota exibida ao usuário/parceiro é média dos últimos 90 dias. Fonte: Blog Parceiros iFood; Saipos.

### Nº perguntas
- [FATO] Três dimensões sequenciais (restaurante, entrega, iFood/NPS). Fonte: Central de Ajuda iFood.
- [FATO] Após dar estrelas ao restaurante, usuário pode "selecionar o que pode melhorar" (tags condicionais). Fonte: Central de Ajuda iFood.

### Campo aberto
- [FATO] Comentário é opcional em todos os blocos ("Você também pode deixar um comentário"). Fonte: Central de Ajuda iFood.

### Dimensões avaliadas
- [FATO] Restaurante (comida, embalagem, quantidade — via tags), entrega (pontualidade) e a própria plataforma iFood (NPS). Fontes: Central de Ajuda iFood; Saipos.

### Uso do feedback
- [FATO] Nota abaixo de 4,5 reduz exposição do restaurante nas listagens. Fonte: Saipos.
- [FATO] Nota mínima 3,0 para participar de Super Restaurante e habilitar iFood Anúncios. Fonte: Saipos.
- [FATO] Moderação automática filtra ofensas, linguagem inadequada, reclamações logísticas e fraudes — não contam para a nota. Fonte: Blog Parceiros iFood.
- [FATO] Restaurante pode responder em até 5 dias; tem 10 minutos para editar. Cliente é notificado e pode revisar a avaliação. Fonte: Blog Parceiros iFood.
- [FATO] Novo restaurante precisa de ≥10 avaliações em 21+ dias ativos antes da nota ser exibida publicamente. Fonte: Blog Parceiros iFood.

### Retorno ao usuário
- [FATO] Cliente é notificado quando o restaurante responde à avaliação. Fonte: Blog Parceiros iFood.
- **Não identificado** confirmação/thank-you screen após envio. Buscado em Central de Ajuda iFood.

### Skip
- **Não identificado** política explícita de skip. Buscado em Central de Ajuda iFood. [INTERPRETAÇÃO] Como o prazo é 7 dias e o app permanece funcional sem avaliar, o skip é implícito.

### Fontes (5+)
1. https://institucional.ifood.com.br/ajuda/avaliacoes-de-pedidos-ifood/
2. https://blog-parceiros.ifood.com.br/avaliacoes-e-moderacoes/
3. https://blog-parceiros.ifood.com.br/avaliacao-ifood/
4. https://saipos.com/integracoes/ifood/como-avaliar-um-pedido-no-ifood
5. https://comunidade.ifood.com.br/t/como-avaliar-o-delivery-do-seu-pedido-no-ifood/113
6. https://abatataquevoa.com.br/como-melhorar-avaliacao-no-ifood/
7. https://blog.multikitchen.com.br/post/conquistar-manter-avaliacoes-5-estrelas-ifood

---

## Uber

### Momento
- [FATO] Imediatamente após a viagem: "Riders are prompted to rate each trip before they can book another." Fonte: Uber Help — Understanding driver ratings.
- [FATO] Prompt bloqueia próxima corrida — usuário precisa avaliar para pedir outra Uber. Fonte: Uber Help.

### Gatilho
- [FATO] Tela in-app pós-viagem (mesma tela contém rating + gorjeta). Fonte: Uber Help — Rating a driver.
- [INTERPRETAÇÃO] Push também é enviado (padrão do app), mas não confirmado em fonte primária.

### Pergunta
- **Não identificado** texto literal em fonte oficial. [HIPÓTESE] Screenshots recorrentes na imprensa mostram "How was your trip with [Driver]?" — não citado como oficial em fonte que checamos.
- [FATO] Uber Help refere-se genericamente a "rate your trip". Fonte: Uber Help.

### Escala
- [FATO] 1–5 estrelas, bidirecional (motorista avalia passageiro e vice-versa). Fonte: Uber Help; Uber Blog.

### Nº perguntas
- [FATO] Uma pergunta principal (estrelas). Se 5★ → oferece "compliment" (elogio pré-definido). Se <5★ → oferece lista de "common issues" (motivos). Fontes: Uber Help — Rating a driver; Ridester.
- [FATO] Após rating: tela de gorjeta (opcional). Fonte: Uber Help.

### Campo aberto
- [FATO] Comentário livre é opcional; tags/motivos padronizados são o mecanismo principal para nota <5. Fonte: Uber Help.

### Dimensões avaliadas
- [FATO] Uma dimensão: a viagem como um todo (motorista + experiência). Fonte: Uber Help.
- [INTERPRETAÇÃO] Sem sub-scores separados por limpeza, direção, cortesia — tudo colapsa em uma nota.

### Uso do feedback
- [FATO] Nota do motorista = média dos últimos 500 ratings. Fonte: Uber Help; Ridester.
- [FATO] Ratings anônimos — motorista/passageiro não vê rating individual por viagem. Fonte: Uber Help — Rating FAQs.
- [FATO] Sistema exclui automaticamente ratings de passageiros que "frequentemente dão notas baixas" e viagens afetadas por fatores externos (trânsito). Fonte: Uber Help — Understanding ratings (driver side).
- [FATO] Notas consistentemente baixas → menos corridas e possível desativação; notas altas → benefícios Uber Pro. Fonte: Ridester; Uber Help.
- **Não identificado** threshold numérico exato de desativação em fonte oficial (imprensa cita ~4,6, mas Uber não confirma publicamente).

### Retorno ao usuário
- **Não identificado** thank-you screen ou resposta ao passageiro. [INTERPRETAÇÃO] Passageiro apenas volta à Home após submeter.

### Skip
- [FATO] Passageiro pode adiar, mas não pode reservar próxima viagem sem avaliar. Fonte: Uber Help — Understanding driver ratings.
- [INTERPRETAÇÃO] Efetivamente obrigatório para uso continuado — soft-lock, não hard-lock.

### Fontes (5+)
1. https://help.uber.com/riders/article/rating-a-driver?nodeId=478d7463-99cb-48ff-a81f-0ab227a1e267
2. https://help.uber.com/en/riders/article/rating-faqs/?nodeId=0539e772-747c-49a7-8c26-f28c65e6f14d
3. https://help.uber.com/en/driving-and-delivering/article/understanding-ratings?nodeId=9e240708-a894-43d7-b19d-13061a4fbe5a
4. https://www.uber.com/us/en/drive/basics/how-ratings-work/
5. https://www.uber.com/en-EG/blog/how-the-uber-rating-system-works
6. https://www.ridester.com/uber-driver-ratings/
7. https://www.ridester.com/uber-rider-ratings/

---

## Airbnb

### Momento
- [FATO] Janela de 14 dias contados a partir do check-out. Fontes: Hostfully; Uplisting; Comunidade Airbnb.
- [FATO] Reviews só são publicadas quando ambos submetem OU quando o prazo de 14 dias expira. Fonte: Hostfully.

### Gatilho
- [FATO] E-mail + notificação in-app após check-out. Fonte: Hostfully; Uplisting.
- [INTERPRETAÇÃO] Lembretes ao longo da janela de 14 dias (comum em sistemas double-blind).

### Pergunta
- **Não identificado** texto literal das perguntas em fonte oficial Airbnb (páginas oficiais não abertas nesta rodada). Referências secundárias descrevem as 6 dimensões.

### Escala
- [FATO] 1–5 estrelas para nota geral e para cada uma das 6 subcategorias. Fonte: Hostfully.
- [FATO] Nota geral é independente — não é média computada das 6 subcategorias. Fonte: Hostfully.

### Nº perguntas
- [FATO] 6 subcategorias + 1 nota geral + campo aberto público + campo privado ao host. Fonte: Hostfully.

### Campo aberto
- [FATO] Review pública em texto livre + feedback privado ao anfitrião. Fonte: Hostfully; Uplisting.
- **Não identificado** obrigatoriedade do texto público em fonte oficial.

### Dimensões avaliadas
- [FATO] Seis dimensões: limpeza (cleanliness), precisão (accuracy), check-in, comunicação, localização, custo-benefício (value). Fonte: Hostfully.
- [FATO] Sistema é bidirecional: host também avalia guest (comunicação, limpeza, cumprimento de regras). Fonte: Hostfully.

### Uso do feedback
- [FATO] Sistema double-blind: nenhum lado vê a review do outro até ambos submeterem ou o prazo terminar. Fonte: Hostfully; Uplisting.
- [FATO] Designed para evitar retaliação/tit-for-tat. Fonte: Uplisting.
- [FATO] Reviews impactam ranking do anúncio e status Superhost. Fonte: Hostfully.
- [FATO] Host pode responder publicamente sem prazo definido — resposta aparece imediatamente. Fonte: Hostfully.

### Retorno ao usuário
- [FATO] Guest recebe review pública do host no seu perfil (visível para futuros hosts). Fonte: Hostfully.
- **Não identificado** thank-you screen específica após submissão.

### Skip
- [FATO] Se guest não avaliar em 14 dias, a janela fecha e review do host (se submetida) publica sozinha. Fonte: Hostfully.
- [INTERPRETAÇÃO] Skip permitido, mas com custo social (guest perde chance de review pública do host).

### Fontes (5+)
1. https://www.hostfully.com/blog/airbnb-review-policy/
2. https://www.uplisting.io/blog/airbnb-review-policy-quick-guide
3. https://www.houst.com/blog/airbnb-review
4. https://community.withairbnb.com/t5/Help-with-your-business/Reviews-how-does-the-14-days-time-frame-work/m-p/2261439
5. https://strassistance.com/how-to-leave-a-review-on-airbnb-after-14-days/
6. https://arxiv.org/pdf/2112.09783 (estudo acadêmico sobre reviews Airbnb)
7. https://touchstay.com/blog/airbnb-guest-review-templates

---

## Google Play (In-App Review API)

### Momento
- [FATO] Desenvolvedor escolhe o momento; Google recomenda "após o usuário ter experimentado o app o suficiente para dar feedback útil". Fonte: Android Developers Blog; Developer docs.
- [FATO] Não interromper tarefas críticas. Fonte: Android Developers Blog.

### Gatilho
- [FATO] Chamada da API `launchReviewFlow()` dentro do app — sem sair para Play Store. Fonte: Developer docs.

### Pergunta
- [FATO] Interface padrão do Google — desenvolvedor não pode customizar. UI mostra 1–5 estrelas + campo de comentário opcional. Fonte: Developer docs.
- [FATO] Card não pode ter overlay, ser redimensionado, opacidade alterada, etc. Fonte: Developer docs.

### Escala
- [FATO] 1–5 estrelas. Fonte: Developer docs.

### Nº perguntas
- [FATO] Uma tela: estrelas + comentário opcional. Fonte: Developer docs.

### Campo aberto
- [FATO] Comentário opcional. Fonte: Developer docs.

### Dimensões avaliadas
- [FATO] Uma única dimensão: o app. Fonte: Developer docs.

### Uso do feedback
- [FATO] Vira review público na Play Store; alimenta rating agregado. Fonte: Play Console docs.
- [FATO] Desenvolvedor pode responder aos reviews via Play Console. Fonte: Play Console.

### Retorno ao usuário
- [FATO] App continua exatamente como estava — "the app must continue without altering the user flow". Fonte: Android Developers Blog.
- [FATO] Se dev responder via console, usuário recebe notificação por e-mail. Fonte: Play Console.

### Skip
- [FATO] Usuário pode fechar o card a qualquer momento — dev não deve tratar como falha. Fonte: Developer docs.
- [FATO] Quota rígida do Google Play: chamar mais de uma vez em curto período (menos de ~1 mês) pode simplesmente não mostrar o dialog. Fonte: Developer docs.
- [FATO] **PROIBIDO** pré-screening tipo "Está gostando do app?" antes do prompt. Fonte: Google Play Developer Program Policies; Developer docs.
- [FATO] **PROIBIDO** criar botão call-to-action que dispara a API (usuário pode ter batido a quota). Fonte: Developer docs.

### Fontes (5+)
1. https://developer.android.com/guide/playcore/in-app-review
2. https://android-developers.googleblog.com/2020/08/in-app-review-api.html
3. https://play.google.com/console/about/reviews/
4. https://www.xda-developers.com/google-in-app-review-api-play-store-reviews-without-leaving-app/
5. https://www.alchemer.com/resources/blog/google-play-in-app-ratings-and-reviews-api-changes-whats-new-and-how-to-adapt-your-strategy/
6. https://blog.jakelee.co.uk/play-store-rating-prompt/

---

## Amazon

### Momento
- [FATO] Seller pode disparar "Request a Review" apenas entre 5 e 30 dias após a data de entrega. Fonte: eComEngine; Web Retailer.
- [FATO] Exatamente uma solicitação por pedido. Fonte: eComEngine.
- [INTERPRETAÇÃO] Amazon também envia e-mails próprios pós-entrega ("How's your item?") — canal separado do "Request a Review".

### Gatilho
- [FATO] E-mail padronizado enviado pela Amazon (seller não customiza texto). Fonte: eComEngine; Channel Reply.
- [INTERPRETAÇÃO] Também há prompts na Home do app/site pós-compra e widgets "Rate your recent purchases".

### Pergunta
- **Não identificado** texto literal do e-mail em fonte oficial. Sabe-se que o e-mail combina "seller feedback" + "product review" em uma mensagem. Fonte: eComEngine.

### Escala
- [FATO] 1–5 estrelas para produto. Fonte: About Amazon (oficial).
- [INTERPRETAÇÃO] Seller feedback também 1–5 estrelas, canal separado.

### Nº perguntas
- [FATO] Nota (estrelas) + headline + review body. Fonte: About Amazon.
- **Não identificado** se headline/body são obrigatórios ou opcionais em fonte oficial.

### Campo aberto
- [FATO] Amazon só considera rating sem texto para o agregado *quando* o comprador adiciona detalhes (texto/imagem/vídeo) OU quando é Verified Purchase. Fonte: About Amazon.
- [INTERPRETAÇÃO] Texto é fortemente incentivado; sem texto o rating vale menos ou não conta.

### Dimensões avaliadas
- [FATO] Duas dimensões separadas: produto (aparece na página do produto) e seller feedback (aparece no perfil do vendedor). Fonte: eComEngine.

### Uso do feedback
- [FATO] Rating agregado NÃO é média simples — usa modelos que ponderam recência e autenticidade (Verified Purchase pesa mais). Fonte: About Amazon.
- [FATO] Amazon analisa 100% dos reviews via ML + revisores humanos antes de publicar; bloqueia centenas de milhões de reviews falsos/ano. Fonte: About Amazon.
- [FATO] Verified Purchase badge só sai se o item foi comprado na Amazon a preço não fortemente descontado. Fonte: About Amazon.
- [FATO] Seller pode responder publicamente ao review (comentário abaixo). Fonte: eComEngine.

### Retorno ao usuário
- **Não identificado** thank-you screen específica. Review aparece publicamente com nome do comprador (ou apelido).
- [FATO] Buyer não pode responder à mensagem "Request a Review" — canal one-way. Fonte: eComEngine.

### Skip
- [FATO] Totalmente opcional — buyer ignora o e-mail sem qualquer penalidade. Fonte: eComEngine.
- [FATO] Seller pode enviar no máximo 1 solicitação por pedido — sem spam. Fonte: eComEngine.

### Fontes (5+)
1. https://www.aboutamazon.com/news/retail/amazon-customer-reviews-star-ratings
2. https://www.amazon.com/gp/help/customer/display.html?nodeId=G8UYX7LALQC8V9KA
3. https://trustworthyshopping.aboutamazon.com/how-amazon-maintains-a-trusted-review-experience
4. https://www.ecomengine.com/blog/amazon-request-a-review-button
5. https://www.webretailer.com/amazon/amazon-request-a-review-button/
6. https://www.channelreply.com/blog/view/amazon-request-a-review-button
7. https://www.goatconsulting.com/merchandising/amazon-product-review-guidelines
