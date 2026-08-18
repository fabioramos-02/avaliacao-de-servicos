# Benchmark — Amazon

Marcadores: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`.

## Contexto

Amazon é a maior e-commerce global. Reviews de produto são um dos pilares originais da confiança na plataforma — a Amazon foi pioneira em publicar reviews negativos abaixo do próprio produto que vende. O sistema separa **product reviews** (aparecem na página do produto) de **seller feedback** (aparecem no perfil do vendedor). O cálculo do rating agregado é sofisticado: não é média simples.

## Como funciona a avaliação

O comprador pode avaliar um produto após a compra. A submissão inclui:
1. Nota de **1 a 5 estrelas**
2. Headline (título do review)
3. Review body (texto)
4. Opcionalmente: fotos e vídeo

Além do fluxo espontâneo (comprador acessa a página do produto e escreve), há dois canais de solicitação:
- **E-mail automático da Amazon** pós-entrega, tipo "How's your item?"
- **"Request a Review" button** — o seller pode disparar manualmente via Seller Central, entre **5 e 30 dias após a entrega**, uma única vez por pedido, com mensagem padronizada e não editável [FATO].

## Momento e gatilho

- [FATO] Janela útil de solicitação: 5 a 30 dias pós-entrega.
- [FATO] Máximo 1 "Request a Review" por pedido.
- [FATO] E-mail padronizado enviado pela Amazon (seller não customiza texto, e comprador não pode responder).
- [INTERPRETAÇÃO] Widgets pós-compra no app/site ("Rate your recent purchases") também aparecem, canal separado.

## Perguntas e escala

| Item | Detalhe |
|------|---------|
| Nota | 1–5 estrelas |
| Headline | Título curto |
| Body | Texto livre |
| Mídia | Fotos e vídeo opcionais |
| Dimensões | Duas separadas: **produto** e **vendedor** (seller feedback) |

**Não identificado** obrigatoriedade formal de headline/body em fonte oficial. [INTERPRETAÇÃO] Estrelas obrigatórias; texto fortemente incentivado.

## Uso pela plataforma

- [FATO] Rating agregado **não é média simples**: Amazon usa modelos que ponderam recência (reviews recentes pesam mais) e autenticidade (Verified Purchase pesa mais).
- [FATO] Badge **Verified Purchase** só sai se o item foi comprado na própria Amazon a preço não fortemente descontado.
- [FATO] Rating sem Verified Purchase **não conta** para o agregado do produto até que o comprador adicione detalhes (texto/imagem/vídeo).
- [FATO] Amazon analisa **100% dos reviews** via ML + revisores humanos antes de publicar; bloqueia centenas de milhões de reviews falsos por ano.
- [FATO] Seller pode responder publicamente ao review (comentário abaixo do review, visível a todos).

## Retorno ao usuário

- **Não identificado** thank-you screen específica após submissão.
- [FATO] Review aparece publicamente com nome do comprador (ou apelido configurado).
- [FATO] Comprador **não pode** responder ao e-mail "Request a Review" — canal one-way.
- [INTERPRETAÇÃO] Retorno concreto é: seller pode comentar no review, e outros compradores podem marcar o review como "útil".

## Skip

- [FATO] Totalmente opcional. Comprador ignora sem qualquer penalidade.
- [FATO] Máximo 1 solicitação por pedido — sem spam possível pelo seller (via Amazon).

## Aprendizados aplicáveis a serviços públicos

1. **Não é média simples — ponderar!** Peso maior para reviews recentes evita nota congelada por reclamações antigas já resolvidas. Peso maior para "solicitação de fato concluída" (equivalente ao Verified Purchase) evita ruído de quem não usou o serviço.
2. **Verificar que o avaliador de fato usou o serviço.** No MS, só coletar avaliação de quem completou uma solicitação com número de protocolo — impede review-bombing sem base real.
3. **Moderação obrigatória.** Amazon investe pesado (ML + humano) e ainda assim bloqueia centenas de milhões de reviews fake/ano. Portal MS precisará de política mínima: filtro de linguagem ofensiva, discurso de ódio, dados pessoais, spam. Não dá para colocar reviews públicas sem esse filtro.
4. **Separar avaliação do "produto" da avaliação do "vendedor".** Amazon separa product review de seller feedback. Analogia direta: no MS, separar avaliação do **serviço específico** (ex: "2ª via de RG") da avaliação do **órgão prestador** (ex: DETRAN). Um serviço bom pode ter atendimento ruim, e vice-versa.
5. **Janela de coleta pós-evento (5–30 dias).** Não pedir na hora (comprador ainda não usou o produto) nem tarde demais (esqueceu). No MS, análogo: pedir avaliação alguns dias após conclusão da solicitação, quando o cidadão já teve tempo de perceber se resolveu ou não seu problema.
6. **Direito de resposta do prestador.** Seller pode comentar no review; no MS, órgão pode responder publicamente. Melhora o loop e reduz sensação de "avaliação caiu no vazio".
7. **Um pedido de avaliação por evento, não múltiplos.** Amazon limita a 1 request por pedido. No MS, aplicar mesma regra: 1 avaliação por protocolo, sem re-envio.

## Fontes

1. About Amazon — "How Amazon customer reviews and star ratings work": https://www.aboutamazon.com/news/retail/amazon-customer-reviews-star-ratings
2. Amazon Customer Service — Understanding Customer Reviews and Ratings: https://www.amazon.com/gp/help/customer/display.html?nodeId=G8UYX7LALQC8V9KA
3. Trustworthy Shopping at Amazon — How Amazon maintains a trusted review experience: https://trustworthyshopping.aboutamazon.com/how-amazon-maintains-a-trusted-review-experience
4. eComEngine — "What is the Amazon Request a Review Button?": https://www.ecomengine.com/blog/amazon-request-a-review-button
5. Web Retailer — "Amazon's Request a Review Button: Every Question Answered": https://www.webretailer.com/amazon/amazon-request-a-review-button/
6. Channel Reply — "How the Amazon Request a Review Button Works": https://www.channelreply.com/blog/view/amazon-request-a-review-button
7. Goat Consulting — "Amazon Product Review Guidelines: 2026 Rules and FAQs": https://www.goatconsulting.com/merchandising/amazon-product-review-guidelines
