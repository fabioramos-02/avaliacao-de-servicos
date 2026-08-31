# 3. Modelo proposto

> Se o Portal ligar a avaliação amanhã, é isso. Documento principal do estudo.

## Resumo em uma tela

| Item | Definição |
|---|---|
| Pergunta | *"Como foi a sua experiência com o serviço?"* |
| Escala | 5 estrelas rotuladas — Péssima / Ruim / Mais ou menos / Boa / Excelente |
| Perguntas opcionais | Motivos positivos (6 cards, marca até 3) · comentário aberto (2000 caracteres) · autodeclaração PcD |
| Momento | Convite único ao concluir o serviço. **Nunca bloqueia.** |
| Identificação | Cidadão logado no Portal MS. Registram-se id do usuário e município do serviço finalístico. **Nenhum campo novo de identificação no formulário.** |
| Indicador principal | Nota média (1–5) + % Satisfeitos (nota 4 e 5) |

## Escopo — decisão SGD 2026-08-25

Duas decisões da Superintendência de Governo Digital estreitam o escopo original:

1. **Somente serviços que nascem no orquestrador X-VIA.** Serviços legados fora do orquestrador ficam de fora nesta onda. Sem X-VIA, o Portal não tem sinal confiável de conclusão do serviço nem de quem o executou.
2. **Avaliação identificada.** O cidadão está logado no Portal para acessar o serviço via X-VIA — a avaliação usa a mesma sessão e registra `id_usuario` (identificador do IdP gov.br) e município do serviço finalístico. Base legal LGPD deixa de se apoiar em anonimato e passa a se apoiar em **execução de política pública** (art. 7º, III + art. 11, II, "b" para dado sensível). Ver [Dados e privacidade](04-dados-e-privacidade.md).

## As perguntas do formulário

### Bloco 1 — Nota (única obrigatória)

**Enunciado:** *"Como foi a sua experiência com o serviço?"*

**Formato:** 5 estrelas rotuladas.

| Estrelas | Rótulo |
|---|---|
| 1 | Péssima |
| 2 | Ruim |
| 3 | Mais ou menos |
| 4 | Boa |
| 5 | Excelente |

**Justificativa da escala:** ímpar (permite ponto neutro), rotulada (elimina ambiguidade cultural do "3 é bom ou ruim?"), visual (estrelas comunicam rapidamente para público heterogêneo), aderente ao padrão gov.br (Portaria SGD/ME nº 548/2022, art. 7º, §1º prevê "escala de cinco pontos").

**Tempo estimado:** cerca de 5 segundos.

### Bloco 2 — Motivos positivos (opcional)

**Enunciado:** *"O que você mais gostou em nosso serviço? — Marque até 3 opções"*

**Formato:** 6 cards clicáveis, seleção múltipla até 3, ordem fixa:

1. Fácil de usar
2. Site/aplicativo funcionou bem
3. Informações claras
4. Consegui resolver
5. Foi rápido
6. Fácil de encontrar

`[INTERPRETAÇÃO]` Foco em positivo (não em problemas) é escolha metodológica deliberada do gov.br: reduz frustração do cidadão que teve má experiência e dá à gestão sinal acionável sobre o que preservar.

### Bloco 3 — Comentário aberto (opcional)

**Enunciado:** *"Deixe elogio, sugestão ou crítica"*

**Placeholder:** *"Para que possamos melhorar o serviço, conte-nos sobre sua experiência."*

**Formato:** área de texto, limite de **2000 caracteres**, contador visível.

**Moderação:** o texto passa por triagem antes de qualquer uso. Detalhes em [Dados e privacidade](04-dados-e-privacidade.md).

### Bloco 4 — Autodeclaração PcD (opcional)

**Título do bloco:** *"Ajude-nos a melhorar a acessibilidade (opcional)"*

**Aviso:** *"Para garantir que nossos serviços atendam todas as pessoas, gostaríamos de saber mais sobre você."*

**Enunciado:** *"Você se considera uma pessoa com deficiência?"* — Sim / Não.

Bloco visualmente separado do restante. Dado pessoal sensível (LGPD art. 5º, II). Base legal: execução de política pública para dado sensível (art. 11, II, "b").

### Botão de envio

**Rótulo:** *"Enviar avaliação"*. Habilita assim que a nota é escolhida.

### Cabeçalho contextual

**Formato:** *"Avaliação do Serviço — {Nome do Serviço} — {Órgão}"*

**Exemplo:** *"Avaliação do Serviço — Emissão de 2ª via de IPVA — Secretaria de Estado de Fazenda"*

Reduz a chance de nota mal atribuída ao serviço errado.

## Ordem, tempo e impacto na conclusão do formulário

| # | Bloco | Obrigatório | Tempo estimado | Drop-off esperado |
|---|---|---|---|---|
| 1 | Nota (5 estrelas) | Sim | ~5s | Baixo |
| 2 | Motivos positivos | Não | ~10s | Nulo |
| 3 | Comentário aberto | Não | 0–60s | Nulo |
| 4 | Autodeclaração PcD | Não | ~5s | Nulo |
| — | Botão enviar | — | ~1s | — |

`[FATO]` Microsurveys de 2–3 perguntas atingem 86,8% de conclusão; formulários de 4–6 perguntas caem para 77,4% (Survicate 2025). O modelo abaixo tem **1 pergunta obrigatória + 3 opcionais** — cidadão apressado envia em 5 segundos; interessado gasta até 80 segundos. Isso preserva a conclusão sem sacrificar profundidade.

`[HIPÓTESE]` Meta de taxa de resposta esperada para o Portal MS: **entre 5% e 15% dos usuários únicos** que concluem serviço, alinhada ao intervalo típico de instrumentos de satisfação em governo digital. **Não identificada** taxa oficial pública do gov.br para calibração precisa.

## Caminho percorrido pelo cidadão

```mermaid
graph TD
    A[Cidadão logado inicia serviço no Portal MS] --> B[Portal encaminha ao sistema do órgão via orquestrador X-VIA]
    B --> C[Serviço executado no sistema do órgão]
    C --> D[Sistema do órgão avisa X-VIA: serviço concluído]
    D --> E{Cidadão retorna ao Portal?}
    E -- Sim --> F[Tela de retorno com convite: 'Avalie este serviço']
    E -- Não --> G[Portal dispara e-mail com link único de avaliação]
    F --> H{Cidadão aceita?}
    G --> H
    H -- Sim --> I[Formulário: 1 obrigatório + 3 opcionais]
    H -- Não --> Z[Fluxo termina. Cidadão prossegue sem prejuízo.]
    I --> J[Envio]
    J --> K[Tela: 'Obrigado. Sua opinião foi registrada.']
    J --> L[Registro identificado gravado]
    L --> M[Nota agregada atualiza a página do serviço]
    L --> N[Painel do órgão atualiza]
    L --> O[Ouvidoria triaga comentário aberto]
```

### Como o cidadão volta ao formulário — proposta prévia SGD

`[RECOMENDAÇÃO]` Quando o cidadão sai do Portal para o sistema do órgão finalístico e não retorna, o Portal dispara **e-mail transacional com link único** para a página de avaliação. Regras:

1. O sistema do órgão avisa o orquestrador X-VIA que o serviço terminou.
2. O Portal dispara o e-mail em janela curta (5–60 minutos) para preservar a recência da experiência.
3. Link assinado, com validade limitada e uso único.
4. Convite único por execução — tela **ou** e-mail, nunca os dois.

**Pendência técnica:** o sinal de conclusão do serviço vem do sistema do órgão para o X-VIA. **Não identificado** se todos os sistemas finalísticos publicam esse evento com padrão único. Precisa ser confirmado com o time do X-VIA antes de estimar prazo.

**Alternativa considerada e descartada como caminho principal:** tela de retorno ao Portal ao final do serviço no sistema do órgão. Descartada porque exige que cada sistema do órgão implemente a chamada de volta — custo distribuído, prazo imprevisível. E-mail centraliza a orquestração no Portal.

## Regras críticas do fluxo

1. **Convite único.** Uma execução do serviço = um convite. Tela **ou** e-mail, nunca os dois. Sem retry, sem lembrete.
2. **Nunca bloquear.** Fechar/pular sempre disponível. Cumpre art. 7º, §3º da Portaria SGD/ME nº 548/2022.
3. **Identificação vem do login.** Cidadão já está logado no Portal para acessar o serviço via X-VIA — a avaliação usa a mesma sessão. **Nenhum campo novo de identificação é solicitado no formulário.**
4. **Prevenção de duplicidade.** Chave `id_usuario + id_execucao_orquestrador` impede múltiplas avaliações da mesma execução.
5. **Moderação do comentário aberto** antes de qualquer publicação. Nota agregada não depende de moderação.
6. **Tempo de resposta da API < 500 ms no p95.** Cidadão nunca espera para enviar.
7. **Publicação sempre agregada.** A identificação existe no dado bruto para uso interno (retorno, análise, ouvidoria). O painel público e os dados abertos só mostram agregados — ver [Dados e privacidade](04-dados-e-privacidade.md).

## O que replica o gov.br, o que difere e por quê

### Replica integralmente

- Pergunta, escala e rótulos.
- 6 cards de motivos positivos.
- Comentário aberto opcional, 2000 caracteres.
- Bloco de acessibilidade opcional.
- Convite único, nunca bloqueia.

### Difere (com justificativa)

| Item | gov.br | MS proposto | Motivo |
|---|---|---|---|
| Plataforma | Ferramenta central SGD/MGI | Instrumento próprio do Portal MS | Adesão federal para entes subnacionais não formalizada. Replica-se o modelo. |
| Identificação | Anônima por design | **Identificada** — usuário logado + município do serviço finalístico | Decisão SGD 2026-08-25. Permite retorno ao cidadão, análise por perfil/localização e integração com histórico do Portal. Base LGPD: execução de política pública. |
| Escopo | Todo serviço federal integrado | Apenas serviços que nascem no orquestrador X-VIA | Sem orquestrador não há sinal confiável de conclusão. |
| Publicação | Painel Central de Qualidade + dados.gov.br | Painel MS + `dados.ms.gov.br` (fase 2) | Início com painel próprio; explorar conexão com federal em fase 2. |

## Extensibilidade do formulário

O formulário **não é fixo**. A composição de campos é parametrizável — a gestão pode incluir, remover, reordenar ou reetiquetar campos sem alteração de código, seguindo o mesmo princípio já adotado na carta de serviço.

Os campos acima são o **núcleo inicial**: ponto de partida com que o instrumento entra no ar, herdado do modelo federal.

**Regras que qualquer campo novo deve respeitar:**

1. **Opcional sempre.** A nota permanece o único campo obrigatório.
2. **Sem coleta de dado pessoal novo no formulário.** A identificação já vem do login; nenhum campo novo pode pedir CPF, nome, telefone, endereço ou repetir dado disponível.
3. **Uso declarado antes da criação.** Todo campo precisa ter, no ato da criação, um indicador ou decisão de gestão que ele alimenta. Campo sem uso definido não entra.
4. **Dado sensível exige parecer prévio do Encarregado (DPO).**
5. **Custo cognitivo é orçamento fechado.** Recomendação: no máximo 6 campos visíveis simultaneamente.
6. **Aditivo, nunca destrutivo.** Alterar semântica de um campo do núcleo (mudar escala, rótulos ou texto da pergunta 1) **quebra a série histórica e a comparabilidade com o gov.br**. Se necessário, trata-se de campo novo, não da edição do existente.
7. **Versionamento obrigatório.** Toda alteração gera nova `versao_formulario`, gravada em cada avaliação.
8. **Avaliações antigas não são reescritas.** Campo removido preserva dados coletados; campo adicionado nasce vazio para o histórico.

## Fluxo de melhoria contínua

```mermaid
graph LR
    A[Coleta contínua] --> B[Painel do órgão]
    B --> C[Reunião mensal de qualidade]
    C --> D[Ação corretiva no serviço]
    D --> E[Indicador sobe]
    E --> A
```

## Referências

- [Referência adotada](02-referencia.md)
- [Dados e privacidade](04-dados-e-privacidade.md)
- [Indicadores](05-indicadores.md)
- Fontes em [`pesquisa/fontes.md`](pesquisa/fontes.md)
