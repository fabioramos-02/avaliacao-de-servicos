# Perguntas propostas ao Portal MS

> Lista concreta, na ordem de exibição ao cidadão, com justificativa curta, tempo estimado e impacto esperado em drop-off.

---

## Visão geral

`[FATO]` Formulário total: **4 blocos** (1 obrigatório, 3 opcionais). Tempo mínimo de conclusão ≈ **5 segundos**. Tempo máximo (tudo preenchido, campo aberto detalhado) ≈ **80 segundos**.

`[FATO]` Microsurveys de 2–3 perguntas atingem 86,8% de conclusão; 4–6 perguntas caem para 77,4% ([Survicate 2025](https://survicate.com/reports/survey-completion-rate-benchmarks/)). O modelo abaixo tem **1 pergunta obrigatória + 3 opcionais** — cidadão pressa envia em 5s; interessado gasta até 80s. Isso preserva completion sem sacrificar profundidade.

---

## Bloco 1 — Pergunta principal (obrigatória)

**Enunciado:** *"Como foi a sua experiência com o serviço?"*

**Formato:** 5 estrelas rotuladas.

| Estrelas | Rótulo |
|---|---|
| 1 | Péssima |
| 2 | Ruim |
| 3 | Mais ou menos |
| 4 | Boa |
| 5 | Excelente |

**Justificativa:** replica **exatamente** o padrão gov.br ([Ferramenta de Avaliação](https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao)) e a Portaria SGD/ME 548/2022 art. 7º §1º (*"escala de cinco pontos"*).

**Tempo estimado:** ~5 segundos.

**Impacto em drop-off:** baixo. Escala visual, decisão rápida, sem digitação.

**Regra de acessibilidade:** cada estrela precisa ser um `<button>` ou `<input type="radio">` com `aria-label` legível ("2 estrelas — Ruim"). Navegável por teclado (setas). WCAG 2.1 AA — 4.1.2 Name/Role/Value ([W3C Forms Tutorial](https://www.w3.org/WAI/tutorials/forms/)).

---

## Bloco 2 — Motivos positivos (opcional)

**Enunciado:** *"O que você mais gostou em nosso serviço? (opcional) — Marque até 3 opções"*

**Formato:** 6 cards clicáveis, seleção múltipla até 3, ordem fixa:

1. Fácil de usar
2. Site/aplicativo funcionou bem
3. Informações claras
4. Consegui resolver
5. Foi rápido
6. Fácil de encontrar

**Justificativa:** replica gov.br. `[INTERPRETAÇÃO]` Foco em positivo (não em problemas) é escolha metodológica deliberada — reduz frustração do cidadão que já teve má experiência e dá à gestão sinal acionável sobre o que preservar.

**Tempo estimado:** ~10 segundos (cidadão que engaja).

**Impacto em drop-off:** nulo (opcional). Se cidadão pular, envia mesmo assim.

**Regra de acessibilidade:** cards em `<fieldset>` com `<legend>` explícito. Cada card é `<input type="checkbox">` + label. Estado selecionado indicado por cor **e** ícone (não só cor — WCAG 1.4.1).

---

## Bloco 3 — Campo aberto (opcional)

**Enunciado:** *"Deixe elogio, sugestão ou crítica (opcional):"*

**Placeholder:** *"Para que possamos melhorar o serviço, conte-nos sobre sua experiência."*

**Formato:** `<textarea>`, limite **2000 caracteres**, contador regressivo visível.

**Justificativa:** GOV.UK Service Manual defende como item mais importante — *"pelo menos uma pergunta aberta sobre como melhorar"* ([GOV.UK](https://www.gov.uk/service-manual/measuring-success/measuring-user-satisfaction)). Replica gov.br em limite e comportamento.

**Tempo estimado:** 0 a 60+ segundos, variável.

**Impacto em drop-off:** nulo (opcional). Único risco é se for **obrigatório** — não deve ser.

**Regra de acessibilidade:** `<label>` visível associado por `for`/`id`. Contador de caracteres precisa ser anunciado por leitor de tela (`aria-live="polite"` a cada 100 caracteres, não a cada tecla — evita spam auditivo).

**Regra de moderação:** conteúdo passa por moderação antes de publicação pública. Comentários com dados pessoais (CPF, telefone digitado à mão pelo cidadão) são removidos ou mascarados antes de exposição no painel.

---

## Bloco 4 — Acessibilidade / autodeclaração PcD (opcional)

**Título do bloco:** *"Ajude-nos a melhorar a acessibilidade (opcional)"*

**Aviso "Saiba mais":** *"Para garantir que nossos serviços atendam todas as pessoas, gostaríamos de saber mais sobre você."*

**Enunciado:** *"Você se considera uma pessoa com deficiência?"*

**Formato:** radio Sim/Não.

**Justificativa:** replica gov.br. Permite segmentar satisfação por público PcD sem exigir dado sensível no fluxo principal. Bloco separado sinaliza opcionalidade.

**Tempo estimado:** ~5 segundos.

**Impacto em drop-off:** nulo (opcional e visualmente separado do bloco principal).

**Regra LGPD:** dado sobre deficiência é **dado pessoal sensível** (LGPD art. 5º II). Base legal: consentimento explícito (art. 11 I) — cidadão só responde se quiser, e o campo tem aviso claro de finalidade. Não vincular à identificação (fica anônimo). Ver detalhes em `docs/04-cidadao/dados-obrigatorios.md`.

---

## Botão de envio

**Rótulo:** *"Enviar avaliação"* — botão único, primário, cor azul SEGOV (#004F9F).

**Comportamento:**
- Habilitado assim que a nota (bloco 1) é escolhida.
- Se cidadão clicar sem preencher a nota, exibir mensagem inline em vermelho + `aria-live="assertive"`: *"Por favor, escolha uma nota de 1 a 5 estrelas antes de enviar."* (WCAG 3.3.1 Error Identification).

---

## Cabeçalho contextual (não é pergunta, mas importa)

**Formato:** *"Avaliação do Serviço — {Nome do Serviço} — {Órgão Responsável}"*

**Exemplo MS:** *"Avaliação do Serviço — Emissão de 2ª via de IPVA — Secretaria de Estado de Fazenda"*

**Justificativa:** replica gov.br. Cidadão sabe o que está avaliando. Reduz "nota mal atribuída ao serviço errado".

---

## O que fica de fora (perguntas propostas e recusadas)

| Pergunta considerada | Motivo da recusa |
|---|---|
| "Você recomendaria este serviço?" (NPS) | Não faz sentido em serviço público monopolista. Ver `docs/02-modelos/`. |
| "Quanto esforço foi necessário?" (CES) | Duplica informação da nota geral em serviço simples. Útil só em fluxos longos e transacionais (bancário, checkout). |
| "Qual seu grau de escolaridade / faixa etária?" | Dado de perfil sem uso operacional. Aumenta drop-off e risco LGPD. |
| "Por que você deu essa nota?" com radio de motivos negativos | Piora experiência de quem já teve má experiência. Gov.br pergunta só positivo, deliberadamente. |
| "Deseja ser contatado?" + e-mail | Quebra anonimato, cria expectativa que órgão pode não cumprir. Se cidadão quiser retorno, existe canal formal: Ouvidoria / Fala.MS. |

---

## Ordem, tempo e impacto — resumo

| # | Bloco | Obrigatório | Tempo | Drop-off esperado |
|---|-------|-------------|-------|-------------------|
| 1 | Nota (5 estrelas) | Sim | 5s | Baixo |
| 2 | Motivos positivos | Não | 10s | Nulo |
| 3 | Campo aberto | Não | 0–60s | Nulo |
| 4 | Autodeclaração PcD | Não | 5s | Nulo |
| — | Botão enviar | — | 1s | — |

`[HIPÓTESE]` Meta de taxa de resposta esperada para o Portal MS: **entre 5% e 15% dos usuários únicos** que concluem serviço, alinhada ao intervalo típico de surveys de governo digital ([SurveySparrow — benchmarks](https://surveysparrow.com/blog/survey-response-rate-benchmarks/)). **Não identificada** taxa oficial pública do gov.br para calibração precisa.

---

## Fontes

Ver [`pesquisa/fontes.md`](../pesquisa/fontes.md), seção "UX / Service Design".
