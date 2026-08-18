# Benchmark — iFood

Marcadores: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`.

## Contexto

iFood é a maior plataforma de delivery de comida do Brasil. Conecta cliente → restaurante → entregador em um único fluxo. Avaliação existe em três eixos separados (restaurante, entrega, plataforma) e alimenta um sistema de reputação que impacta a exposição comercial do parceiro.

## Como funciona a avaliação

Após concluído o pedido, o iFood abre uma janela de **7 dias** para o cliente avaliar. O fluxo é composto de três blocos sequenciais [FATO]:

1. **Restaurante** — nota de 1 a 5 estrelas + tags opcionais (comida saborosa, boa embalagem, boa quantidade etc.) + comentário livre opcional.
2. **Entrega** — pergunta binária "O pedido chegou no tempo informado?" (Sim/Não) + comentário opcional.
3. **iFood (plataforma)** — pergunta NPS: "De 0 a 10, quanto você nos recomendaria".

## Momento e gatilho

- [FATO] A tela de estrelas aparece na reabertura do app após a finalização do pedido.
- [FATO] Notificações push são enviadas.
- [FATO] Acesso permanente via aba "Pedidos" durante os 7 dias.

## Perguntas e escala

| Bloco | Pergunta | Escala | Obrigatório |
|-------|----------|--------|-------------|
| Restaurante | Estrelas + "o que pode melhorar" (tags) | 1–5 estrelas | Estrelas sim; tags e texto não |
| Entrega | "O pedido chegou no tempo informado?" | Sim / Não | [INTERPRETAÇÃO] Sim |
| iFood (NPS) | "De 0 a 10, quanto você nos recomendaria" | 0–10 | [INTERPRETAÇÃO] Sim |

O comentário livre é sempre opcional [FATO].

## Uso pela plataforma

- [FATO] Nota exibida ao cliente é média dos últimos **90 dias**.
- [FATO] Novo restaurante só tem nota pública após ≥10 avaliações em 21+ dias ativos.
- [FATO] Nota abaixo de **4,5** reduz a exposição do restaurante nas listagens.
- [FATO] Nota mínima **3,0** para participar do Super Restaurante e habilitar iFood Anúncios.
- [FATO] Moderação automática descarta ofensas, linguagem inadequada, reclamações logísticas e fraudes — não contam para a nota.

## Retorno ao usuário

- [FATO] Restaurante tem até 5 dias para responder à avaliação; 10 minutos para editar a resposta.
- [FATO] Cliente é notificado quando o restaurante responde e pode revisar a nota original.
- **Não identificado** thank-you screen após envio (buscado em Central de Ajuda iFood).

## Skip

- **Não identificado** política formal de skip. [INTERPRETAÇÃO] Como o app segue funcional sem avaliar e o prazo é 7 dias, o skip é permitido de fato.

## Aprendizados aplicáveis a serviços públicos

1. **Separar dimensões diferentes de avaliação.** iFood separa "o restaurante", "a entrega" (execução) e "o iFood" (canal). Análogo no MS: separar "avaliação do serviço público específico solicitado" (secretaria/órgão) de "avaliação do Portal" (canal digital). Impede que problema de canal contamine avaliação do serviço.
2. **Tags padronizadas > texto livre** para captura de sinal quantificável ("boa embalagem", "quantidade adequada"). No MS: "atendimento cordial", "prazo cumprido", "informação clara", "resolveu meu problema".
3. **Janela finita para avaliar** (7 dias) evita reviews descoladas do evento. Aplicável ao Portal.
4. **Média móvel de 90 dias** evita que um erro antigo puna eternamente o prestador — princípio útil para avaliar órgãos públicos com sazonalidade de demanda.
5. **Moderação com regra clara** (o que é descartado) protege o prestador contra ataques injustos — essencial em serviço público sensível a ruído político.
6. **Direito de resposta** do prestador humaniza o feedback e cria loop de melhoria. No MS, secretaria poderia responder publicamente a avaliações — modelo Reclame Aqui adaptado.
7. **NPS separado para o canal** dá uma métrica única de saúde do produto digital, útil para gestão do Portal.

## Fontes

1. Central de Ajuda iFood — "Avaliações de Pedidos iFood": https://institucional.ifood.com.br/ajuda/avaliacoes-de-pedidos-ifood/
2. Blog Parceiros iFood — "Como funcionam as avaliações e suas moderações": https://blog-parceiros.ifood.com.br/avaliacoes-e-moderacoes/
3. Blog Parceiros iFood — "Avaliação iFood: saiba como melhorar a sua": https://blog-parceiros.ifood.com.br/avaliacao-ifood/
4. Saipos — "Como Avaliar no iFood: passo a passo e dicas": https://saipos.com/integracoes/ifood/como-avaliar-um-pedido-no-ifood
5. Comunidade iFood — "Como avaliar o delivery do seu pedido no iFood": https://comunidade.ifood.com.br/t/como-avaliar-o-delivery-do-seu-pedido-no-ifood/113
6. A Batata Que Voa — "Como Melhorar Avaliação no iFood": https://abatataquevoa.com.br/como-melhorar-avaliacao-no-ifood/
7. MultiKitchen — "Como conquistar e manter avaliações 5 estrelas no iFood": https://blog.multikitchen.com.br/post/conquistar-manter-avaliacoes-5-estrelas-ifood
