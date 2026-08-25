# O que coletar do cidadão

> Princípio único deste estudo: **menos é mais**. Cada campo extra reduz a taxa de resposta e amplia risco LGPD. Coleta-se só o que a gestão vai usar.

---

## 1. Princípio orientador

`[FATO]` Estudos de mercado 2024–2025 mostram que microsurveys de **2 a 3 perguntas** atingem taxa mediana de conclusão de **86,8%**, contra **77,4%** em formulários de 4 a 6 perguntas ([Survicate — Benchmark 2025](https://survicate.com/reports/survey-completion-rate-benchmarks/)).

`[FATO]` A **Portaria SGD/ME 548/2022, art. 7º § 3º** determina: *"a avaliação de satisfação não poderá ser uma etapa obrigatória da jornada do usuário"*. Ou seja: cidadão nunca é bloqueado por não avaliar. Base do modelo gov.br ([Portaria 548/2022](https://legislacao.contabil.business/1643134772)).

`[FATO]` A **LGPD (Lei 13.709/2018), art. 6º III** exige **minimização**: coletar apenas o necessário para a finalidade declarada. Aplicado a avaliação de serviço público, isso reforça o modelo enxuto do gov.br.

`[INTERPRETAÇÃO]` A soma dessas três forças aponta para o mesmo desenho: **uma pergunta obrigatória + poucos qualificadores opcionais + campo livre opcional + nenhum campo novo de identificação no formulário** (a identificação é derivada do login do cidadão no Portal — decisão SGD 2026-08-25; ver [LGPD](lgpd.md)).

---

## 2. O que faz sentido perguntar

### 2.1. Nota geral do serviço (obrigatória, única exigida)

`[RECOMENDAÇÃO]` **"Como foi a sua experiência com o serviço?"** — escala de 5 estrelas rotuladas (Péssima / Ruim / Mais ou menos / Boa / Excelente).

**Por quê:** replica exatamente o padrão gov.br ([Ferramenta de Avaliação](https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao)). Permite comparação direta com serviços federais e entre serviços do próprio MS. Escala rotulada elimina ambiguidade cultural do "3 é bom ou é ruim?".

### 2.2. Motivos positivos (opcional, até 3)

`[RECOMENDAÇÃO]` **"O que você mais gostou em nosso serviço?"** — 6 cards, marcar até 3: *Fácil de usar / Site funcionou bem / Informações claras / Consegui resolver / Foi rápido / Fácil de encontrar*.

**Por quê:** dá à gestão um sinal acionável sobre o que funcionou, sem forçar o cidadão a dissecar problemas. Espelha gov.br.

### 2.3. Campo aberto (opcional)

`[RECOMENDAÇÃO]` **"Deixe elogio, sugestão ou crítica"** — até 2000 caracteres, com contador visível.

**Por quê:** GOV.UK trata como o item mais defendido do Service Manual — *"Include at least one open-ended question about how to improve the service"* ([GOV.UK Service Manual](https://www.gov.uk/service-manual/measuring-success/measuring-user-satisfaction)). Custo de implementação baixo, valor qualitativo alto.

### 2.4. Acessibilidade — autodeclaração PcD (opcional)

`[RECOMENDAÇÃO]` **"Você se considera uma pessoa com deficiência?"** — Sim/Não, em bloco separado com aviso de finalidade.

**Por quê:** permite segmentar satisfação por público PcD sem exigir dado sensível na porta principal do formulário. Modelo gov.br.

---

## 3. O que NÃO faz sentido perguntar

| O que evitar | Por quê |
|---|---|
| **Novos campos de CPF, nome, e-mail, telefone no formulário** | A avaliação é identificada via login do Portal (decisão SGD 2026-08-25). Não há por que pedir de novo no formulário — é ruído, atrito e risco LGPD sem contrapartida. Dado de contato existente na conta gov.br é usado apenas pelo disparador de e-mail transacional. |
| **Idade, gênero, escolaridade, renda** | Dados sensíveis ou de perfil que não serão usados para decisão operacional. Pertencem a pesquisa qualitativa pontual, não a survey contínua. |
| **NPS ("Você recomendaria?")** | Serviço público não tem lógica de recomendação — cidadão não "escolhe" a Receita Estadual. `[INTERPRETAÇÃO]` NPS mede intenção comercial, não satisfação com política pública. Ver `docs/02-modelos/`. |
| **Múltiplas escalas simultâneas (CSAT + CES + Likert)** | Aumenta cansaço sem ganho de sinal. Escolher uma escala e sustentar. |
| **Perguntas de múltipla escolha longas (>6 opções)** | Sobrecarga cognitiva mobile. Máximo 6 cards, como faz o gov.br. |
| **Campos livres obrigatórios** | Fonte principal de abandono. Livre é sempre opcional. |
| **"Por que você deu essa nota?" seguido de radio-buttons** | Empurra cidadão insatisfeito a justificar frustração — piora experiência de quem já teve má experiência. Gov.br pergunta só o positivo, deliberadamente. |

---

## 4. Alinhamento com gov.br

`[FATO]` A recomendação replica **integralmente** o formulário federal descrito em `docs/03-benchmark/ferramenta-de-avaliacao.md`. Não há divergência.

`[INTERPRETAÇÃO]` Replicar tem três ganhos: (a) evita reinventar roda validada nacionalmente, (b) permite comparabilidade MS × federal × outros estados que adotarem o padrão, (c) reduz curva de aprendizado do cidadão que já viu o mesmo formulário no gov.br.

`[RECOMENDAÇÃO]` Um único ajuste possível para MS: adicionar **nome do órgão estadual responsável** no cabeçalho contextual (ex.: *"Avaliação do Serviço — Emissão de 2ª via de IPVA — Secretaria de Estado de Fazenda"*). Padrão gov.br já faz isso; MS só precisa mapear a estrutura estadual.

---

## 5. Compromisso com o cidadão (uso do feedback)

`[RECOMENDAÇÃO]` Após envio, exibir mensagem curta: **"Obrigado. Sua avaliação vai para o painel público do Portal MS e ajuda a definir o que melhorar."**

**Três compromissos que sustentam a mensagem:**

1. **Publicar** — nota agregada por serviço na página do próprio serviço (visível ao próximo cidadão), replicando gov.br.
2. **Publicar em dado aberto** — dataset em `dados.ms.gov.br`, replicando modelo `data.gov.uk` ([GDS Blog](https://gds.blog.gov.uk/2024/01/29/how-we-are-improving-gov-uk-pay-with-user-satisfaction-feedback/)).
3. **Ciclo de melhoria** — cada superintendência responsável revisa mensalmente comentários e notas do próprio serviço; ações vão para plano de melhoria publicado.

`[INTERPRETAÇÃO]` Sem esses três compromissos, o formulário vira "caixinha de sugestões que ninguém lê" — pior do que não coletar, porque gera frustração e cai a taxa de resposta em ondas futuras.

---

## 6. Resumo executivo

| Item | Obrigatório? | Tempo estimado |
|---|---|---|
| Nota (5 estrelas rotuladas) | Sim | ~5 segundos |
| Motivos positivos (até 3) | Não | ~10 segundos |
| Campo aberto | Não | 0–60 segundos |
| Autodeclaração PcD | Não | ~5 segundos |
| **Total mínimo (só obrigatório)** | — | **~5 segundos** |
| **Total máximo (tudo preenchido)** | — | **~80 segundos** |

`[RECOMENDAÇÃO]` **Nenhum campo novo de identificação. Nenhum dado de perfil pedido no formulário.** A identificação vem do login já existente no Portal (obrigatório para acessar o serviço via X-VIA). Isso preserva a taxa de resposta alta sem quebrar o princípio de minimização.

---

## Fontes

Referências consolidadas em [`pesquisa/fontes.md`](../pesquisa/fontes.md), seção "UX / Service Design".
