# Fluxo da avaliação

## Fluxo do cidadão

```mermaid
graph TD
    A[Cidadão inicia serviço] --> B[Cidadão conclui serviço]
    B --> C[Tela de confirmação com convite discreto:<br/>'Avalie este serviço']
    C --> D{Cidadão clica?}
    D -- Sim --> E[Formulário abre em modal ou tela dedicada]
    D -- Não --> Z1[Fluxo termina. Cidadão prossegue sem prejuízo.]
    E --> F[Bloco 1: nota obrigatória]
    F --> G[Blocos 2, 3, 4 opcionais — cidadão preenche o que quiser]
    G --> H[Botão 'Enviar avaliação']
    H --> I[Registro anônimo gravado]
    I --> J[Tela de agradecimento:<br/>'Obrigado. Sua opinião foi registrada.']
    J --> K[Cidadão sai]
```

## Fluxo do dado

```mermaid
graph LR
    subgraph Coleta
        A1[Frontend widget] -->|POST anônimo| A2[API]
        A2 -->|valida + dedupe hash sessão| A3[fato_avaliacao]
    end

    subgraph Consumo
        A3 --> B1[Cache página do serviço<br/>nota média + N]
        A3 --> B2[Painel do gestor<br/>filtros, drill-down]
        A3 --> B3[Painel Ouvidoria<br/>triagem comentários]
        A3 --> B4[Exportação mensal<br/>dados abertos MS]
    end

    subgraph Melhoria
        B2 --> C1[Reunião mensal qualidade]
        C1 --> C2[Ação corretiva no serviço]
        C2 --> D1[Métrica sobe]
    end
```

## Regras críticas do fluxo

1. **Convite único.** Um serviço concluído = um convite. Sem retry, sem lembrete.
2. **Nunca bloquear.** Fechar/pular sempre disponível. Cumpre art. 7º §3º Portaria 548/2022.
3. **Anônimo.** Nenhum passo do fluxo requer identificação.
4. **Dedupe.** Hash de sessão evita spam mas não identifica cidadão.
5. **Moderação.** Comentário aberto passa por moderação antes de publicação (se publicado). Nota agregada não depende de moderação.
6. **Tempo de resposta da API < 500ms.** Cidadão nunca deve esperar para enviar.

## Onde a avaliação é exibida

| Local | O que aparece | Público |
|---|---|---|
| Página do serviço | Nota média + N + link "ver avaliações" | Cidadão |
| Painel do gestor | Distribuição, comentários, série temporal | Gestor do órgão |
| Painel Ouvidoria | Comentários abertos + tags críticas | Ouvidoria |
| Painel SETDIG | Ranking geral, alertas | Direção SETDIG |
| dados.ms.gov.br | Agregado mensal em CSV | Público geral (fase 2) |

## Cadência

| Ritmo | Ação |
|---|---|
| Tempo real | Coleta + atualização de nota média (com cache curto) |
| Diário | Ouvidoria triaga comentários novos |
| Semanal | Painel gestor gera relatório automático |
| Mensal | Reunião de qualidade por órgão |
| Trimestral | Revisão SETDIG do ranking geral |
| Anual | Publicação de série histórica em dados abertos |
