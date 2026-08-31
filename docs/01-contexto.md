# 1. Contexto

## Por que o Estado precisa avaliar seus serviços digitais

O Estado do Mato Grosso do Sul opera um Portal Único de Serviços do cidadão. Serviços digitais entram em produção sem um instrumento padronizado para medir se atenderam bem quem os usou. Sem essa medição, três coisas não acontecem: (a) o gestor não sabe onde priorizar melhoria; (b) o cidadão não vê que sua opinião foi registrada; (c) o Estado descumpre o art. 23 da Lei nº 13.460/2017, que obriga avaliação continuada de qualidade dos serviços.

## Pergunta central

> **Como o Portal MS deve pedir ao cidadão que avalie cada serviço digital que ele usa?**

## Ponto de partida

`[FATO]` O padrão nacional para esse tipo de instrumento é o **gov.br**. A Central de Qualidade coordenada pela Secretaria de Governo Digital (SGD) do Ministério da Gestão e da Inovação em Serviços Públicos (MGI) padronizou a Ferramenta de Avaliação por meio da Portaria SGD/MGI nº 1.083, de 14/02/2025 (norma vigente; revisou a Portaria SGD/ME nº 548/2022). O modelo federal opera em escala real: **1.047 serviços integrados e nota média 4,39/5** publicados pela Central de Qualidade em ago/2026.

`[RECOMENDAÇÃO]` Adotar o gov.br como referência principal do estudo. Qualquer divergência entre o desenho do MS e o modelo federal precisa ser justificada explicitamente.

## Oportunidade

O momento é favorável por três razões objetivas:

1. **Instrumento nacional consolidado.** Não é necessário reinventar formulário, escala ou fluxo — o gov.br já validou tudo isso em cinco anos de operação.
2. **Orquestrador X-VIA em operação.** Serviços que nascem no orquestrador têm sinal confiável de conclusão, o que permite fechar o ciclo cidadão → convite → avaliação sem depender de cada sistema finalístico implementar retorno próprio.
3. **Marco legal maduro.** Lei nº 13.460/2017 (Código de Defesa do Usuário) obriga a avaliação; Lei nº 13.709/2018 (LGPD) enquadra o tratamento em execução de política pública; Portaria SGD/MGI nº 1.083/2025 dá o modelo. Os três se reforçam.

## Objetivo do estudo

Entregar à SETDIG uma **proposta pronta para validação** de como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão, alinhada ao padrão gov.br e à LGPD.

## Escopo

**Coberto pelo estudo:**

- Serviços **digitais** publicados no Portal MS.
- **Somente serviços que nascem no orquestrador X-VIA.** Serviços legados fora do orquestrador ficam de fora nesta onda — decisão SGD de 2026-08-25. Sem o orquestrador não há sinal confiável de conclusão do serviço nem de quem o executou.
- Avaliação **transacional** — feita ao final da utilização de um serviço específico.
- Modelo, dados a coletar, indicadores, regras de privacidade, plano de validação e recomendação executável.

**Fora do escopo:**

- Implementação técnica (código, contrato com fornecedor, integração fina).
- Painel de gestão pronto (o estudo entrega especificação de indicadores; a construção do painel é próxima etapa).
- Pesquisa qualitativa com cidadãos — recomendada como passo posterior.
- Avaliação **relacional** do Portal como marca — instrumento distinto, tratado em iniciativa separada.

## Público a quem o estudo se dirige

| Público | O que encontra aqui |
|---|---|
| Diretoria SETDIG | Recomendação, riscos, decisão a tomar |
| Comitê de Governança de Serviços | Referência adotada, justificativas, plano de validação |
| Órgãos setoriais donos de serviços | Como o serviço deles será avaliado |
| Equipe do Portal (SGD + STI + Xvia) | Modelo, indicadores, regras a implementar |
| Encarregado (DPO) do Estado | Enquadramento LGPD |

## Princípios que orientam o estudo

1. **gov.br é a âncora.** Divergir do padrão federal exige justificativa explícita.
2. **Menos é mais.** Cidadão de serviço público não tolera formulário longo — cada campo a mais reduz a taxa de resposta.
3. **Coletar só o que será usado.** LGPD art. 6º, III (minimização).
4. **Fechar o ciclo.** Avaliação que não vira ação vira ruído — a proposta precisa dizer como a gestão age sobre o dado coletado.
5. **Comparável.** O indicador precisa permitir comparação entre serviços, órgãos, municípios e no tempo.
6. **Aderente ao marco legal.** Lei nº 13.460/2017 exige avaliação; o desenho precisa cumprir.
7. **Acessível.** Modelo deve funcionar para público heterogêneo, incluindo pessoas com deficiência e cidadãos com baixa alfabetização digital.
8. **Linguagem simples.** Documento voltado a decisor, não a especialista.

## Base legal aplicável

- **Lei nº 13.460/2017** — Código de Defesa do Usuário de Serviços Públicos. Art. 23 obriga avaliação continuada e publicação de resultados.
- **Lei nº 13.709/2018 (LGPD)** — enquadra o tratamento dos dados coletados.
- **Decreto federal nº 9.094/2017** — simplificação de serviços e Carta de Serviço.
- **Portaria SGD/MGI nº 1.083, de 14/02/2025** — vigente; dispõe sobre avaliação de satisfação e padrões de qualidade.
- **Portaria SGD/ME nº 548, de 24/01/2022** — norma anterior; ainda referenciada por dispositivos herdados (art. 7º §3º sobre não obrigatoriedade da avaliação).

Fontes completas em [`pesquisa/fontes.md`](pesquisa/fontes.md).

## Marcadores usados no estudo

- `[FATO]` — informação confirmada por fonte primária.
- `[INTERPRETAÇÃO]` — análise apoiada em evidência.
- `[HIPÓTESE]` — proposição a validar.
- `[RECOMENDAÇÃO]` — sugestão do estudo.
- `**Não identificado**` — buscado sem evidência conclusiva.
