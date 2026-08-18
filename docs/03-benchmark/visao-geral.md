# Benchmark de plataformas digitais — Visão geral

## Objetivo

Investigar como cinco produtos digitais de referência (iFood, Uber, Airbnb, Google Play e Amazon) coletam avaliação dos usuários — momento, gatilho, escala, uso do feedback — para extrair padrões aplicáveis ao Portal de Serviços do MS.

## Cases analisados

| Case | Contexto | Documento |
|------|----------|-----------|
| iFood | Delivery de comida (BR) | [ifood.md](./ifood.md) |
| Uber | Mobilidade urbana (global) | [uber.md](./uber.md) |
| Airbnb | Hospedagem entre pessoas (global) | [airbnb.md](./airbnb.md) |
| Google Play | Loja de apps Android (in-app review) | [google.md](./google.md) |
| Amazon | E-commerce (produto + vendedor) | [amazon.md](./amazon.md) |

Comparativo tabular consolidado: [comparativo.md](./comparativo.md).

## Resumo executivo

### O que os cinco fazem em comum

1. **Escala visual simples.** Todos usam 1–5 estrelas como métrica principal (Amazon, iFood-restaurante, Uber, Airbnb, Google Play). iFood adiciona binário (Sim/Não) para pontualidade e NPS 0–10 para a própria plataforma.
2. **Momento ancorado no evento.** Ninguém pede avaliação "a qualquer hora": Uber pede logo após a viagem; iFood após conclusão do pedido; Airbnb após check-out; Amazon após entrega; Google Play quando o dev julga que o usuário já usou o suficiente.
3. **Campo aberto opcional.** Nenhum dos cinco força o comentário livre. Todos oferecem — vários usam tags/motivos padronizados como caminho principal (Uber, iFood).
4. **Baixa fricção.** Uma tela, uma pergunta principal, submissão em poucos segundos. Airbnb é o mais longo (6 dimensões) e ainda cabe numa sessão curta.
5. **Feedback move algo.** Nota agregada é visível ao próximo consumidor, impacta ranking/exposição e alimenta decisões operacionais (desativação de motorista, ocultação de restaurante mal avaliado).

### O que muda entre eles

- **Obrigatoriedade:** Uber é o único que bloqueia o próximo uso até avaliar (soft-lock). Amazon é totalmente opcional. Airbnb tem prazo (14 dias) e depois trava.
- **Simetria:** Uber e Airbnb são bidirecionais (ambos os lados avaliam). iFood, Amazon e Google Play são unidirecionais (cliente avalia).
- **Anonimato:** Uber é anônimo por design. Amazon expõe o nome do reviewer. Airbnb expõe ambos os lados. iFood expõe o cliente ao restaurante.
- **Retorno ao usuário:** Só iFood e Amazon têm resposta pública explícita do prestador; Airbnb permite resposta do host à review pública; Uber não tem canal de resposta ao passageiro.
- **Regra anti-viés:** Airbnb usa *double-blind* de 14 dias. Google Play proíbe pré-screening ("Está gostando?"). Amazon pondera Verified Purchase e recência (não é média simples).

### Padrões aplicáveis a serviço público

1. **Ancorar no fim do serviço** (analógo ao "após entrega", "após viagem"): pedir avaliação assim que o cidadão conclui a solicitação, não como pop-up aleatório.
2. **Uma pergunta principal + tags** ao invés de formulário longo: se quiser detalhe, usar tags condicionais (só aparecem se nota <4, por exemplo — modelo Uber).
3. **Campo aberto sempre opcional**, nunca gate.
4. **Comunicar o que muda com o feedback:** os cinco cases mostram nota agregada e/ou dão resposta. Se a nota não impacta nada visível, o cidadão para de avaliar.
5. **Evitar pré-screening enganoso** — o Google proíbe explicitamente e o motivo é ético: viés seletivo destrói o valor da amostra.
6. **Skip permitido, sem punição.** Só Uber trava, e ainda assim é a plataforma mais criticada por rating pressure. Serviço público não deveria seguir esse caminho.
7. **Moderação obrigatória** — iFood e Amazon investem pesado em ML + humano para filtrar ofensas, fraudes e spam. Portal MS precisará de política mínima antes de ir ao ar.
8. **Bidirecionalidade não se aplica** ao contexto MS (cidadão-Estado não é peer-to-peer), mas o *double-blind* do Airbnb é interessante como referência de proteção contra retaliação — algo a considerar se servidores puderem ver quem avaliou.

### Aprendizados por case (destaque)

- **iFood:** separar avaliação do serviço (restaurante) da avaliação do canal (iFood/NPS) é útil — no MS, separar "avaliação do serviço público específico" da "avaliação do Portal".
- **Uber:** tags padronizadas capturam 80% do sinal com 20% do esforço do usuário; obrigatoriedade gera resistência.
- **Airbnb:** múltiplas dimensões (6) só funcionam porque o serviço é rico; para serviços transacionais simples, 1–2 dimensões bastam.
- **Google Play:** proibições explícitas (não pré-screenar, não incentivar) são um bom guia ético; quota anti-fadiga é essencial.
- **Amazon:** ponderar por recência e "verified" evita nota congelada por reviews antigas ou fake — no MS, ponderar por "solicitação de fato concluída" tem paralelo direto.

## Fontes

Consolidado em [../../pesquisa/fontes.md](../../pesquisa/fontes.md).
