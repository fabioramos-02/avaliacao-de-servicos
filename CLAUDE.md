# CLAUDE.md — Avaliação dos Serviços do Portal MS

Contexto para futuras sessões do Claude Code neste repositório.

## O que é

Estudo estratégico da **Secretaria-Executiva de Transformação Digital (SETDIG)** para definir como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão. Coordenação: Superintendência de Governo Digital (SGD).

## Regra número 1 — gov.br é a âncora

**A referência principal é o gov.br**, especificamente:

1. Central de Qualidade — https://www.gov.br/governodigital/pt-br/estrategias-e-governanca-digital/transformacao-digital/central-de-qualidade
2. Ferramenta de Avaliação — https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao
3. Portaria SGD/MGI nº 1.083, de 14/02/2025 (norma vigente; revisou a 548/2022).
4. Portaria SGD/ME nº 548/2022 (norma anterior; artigos-chave herdados).

Outros benchmarks (iFood, Uber, Airbnb, GOV.UK) são referências secundárias. Qualquer divergência do modelo gov.br precisa de justificativa explícita no documento.

## Modelo padrão gov.br (memorize)

- Pergunta: **"Como foi a sua experiência com o serviço?"**
- Escala: 5 estrelas rotuladas — **Péssima / Ruim / Mais ou menos / Boa / Excelente**.
- Pergunta 2 (opcional): "O que você mais gostou em nosso serviço?" — 6 cards, marque até 3 (Fácil de usar, Site/app funcionou bem, Informações claras, Consegui resolver, Foi rápido, Fácil de encontrar).
- Campo aberto opcional (até 2000 chars).
- Bloco acessibilidade opcional (autodeclaração PcD).

**Princípio jurídico crítico** (art. 7º §3º Portaria 548/2022): a avaliação nunca pode ser etapa obrigatória da jornada do cidadão. Nunca bloquear o serviço.

## Onde o modelo MS já diverge do gov.br (decisões vigentes)

Toda divergência tem justificativa em `docs/07-recomendacao.md`, seção "Registro de decisões". As vigentes:

| # | Decisão | Efeito |
|---|---|---|
| **D10** | Avaliação **identificada** (não anônima), via login gov.br no Portal | Base LGPD passa a ser execução de política pública |
| **D11** | Escopo restrito a serviços que nascem no orquestrador X-VIA | Sem X-VIA, não há sinal de conclusão |
| **D13** | **Autodeclaração PcD fica fora da primeira versão** | v1 não trata dado sensível; o bloco volta com o painel da Fase 3 |
| **D14** | **Convite nos dois canais** — tela do Portal **e** e-mail, sempre; quem já avaliou recebe agradecimento, sem link. Em troca, **reavaliação do mesmo serviço só depois de 10 dias** | Revoga a parte de canal único da D7; a vedação de bloquear permanece |

Ao editar qualquer doc, conferir se o texto ainda bate com essas decisões antes de escrever.

**Framework técnico gov.br**: 7 dimensões × 5 atributos = 35 padrões (Autodiagnóstico do gestor, não confundir com os 6 cards mostrados ao cidadão).

**Referência de escala**: em 2026-08, gov.br publica média 4,39/5 sobre 1.047 serviços integrados.

## Como falar nos docs

- **Não** usar "PBI", "Feature", "backlog", "sprint", "epic".
- **Sim** usar "estudo", "modelo", "proposta", "recomendação", "referência".
- Linguagem simples, direta, macro estratégica. Escrever como Superintendente Sênior para diretoria.
- Marcadores obrigatórios: `[FATO]`, `[INTERPRETAÇÃO]`, `[HIPÓTESE]`, `[RECOMENDAÇÃO]`, `**Não identificado**`.
- pt-BR sempre.
- Nunca copiar mais que 25 palavras seguidas de uma fonte.
- Toda afirmação factual sobre um case tem fonte em `pesquisa/fontes.md`.

## Estrutura

```
avaliacao-de-servicos/
├── contexto.md              Plano vivo + status (atualizar a cada onda)
├── CLAUDE.md                Este arquivo
├── README.md                Como rodar e navegar
├── mkdocs.yml               Config MkDocs Material + tema SEGOV
├── requirements.txt         mkdocs + mkdocs-material + pymdown
├── docs/
│   ├── assets/img/          Logos (segov-logo.svg)
│   ├── assets/css/segov.css Tema SEGOV (light + dark)
│   ├── 01-contexto/         Panorama do estudo
│   ├── 02-modelos/          NPS/CSAT/CES/escalas
│   ├── 03-benchmark/        gov.br (âncora) + secundários
│   ├── 04-cidadao/          O que perguntar + LGPD
│   ├── 05-proposta/         Modelo MS + matriz decisão
│   ├── 06-validacao/        Estratégia com stakeholders
│   └── 07-conclusao/        Recomendação
├── apresentacoes/
│   └── avaliacao-servicos-portal-ms.html   Apresentação executiva (10 slides, tokens do DS)
├── Avaliacao de Servicos  TO BE v1.docx    Pacote de entrega da Fase 1 — gerado pelo vault, não editar à mão
└── pesquisa/
    ├── fontes.md            Bibliografia consolidada
    ├── evidencias.md        Trechos-chave
    └── notas/               Notas cruas dos agentes de pesquisa
```

Os nomes reais dos arquivos em `docs/` são planos: `01-contexto.md`, `02-referencia.md`, `03-modelo-proposto.md`, `04-dados-e-privacidade.md`, `05-indicadores.md`, `06-validacao.md`, `07-recomendacao.md`.

## Design system

- Paleta SEGOV: primário `#004F9F`, dark `#003A76`, light `#1A67B5`, texto `#30302E`.
- Fonte: system-ui stack (mesma do gov.br).
- Logo oficial SEGOV em `docs/assets/img/segov-logo.svg` — filtro CSS aplica branco no header azul.
- Tema light + dark ambos configurados em `docs/assets/css/segov.css`.

## Comandos

```bash
# Instalar deps
pip install -r requirements.txt

# Servir local (hot reload)
python -m mkdocs serve -a 127.0.0.1:8000

# Build estático
python -m mkdocs build

# Build estrito (falha em warning) — usar antes de publicar
python -m mkdocs build --strict
```

## Estratégia de agentes

Estudo executado em ondas de agentes especializados (`general-purpose`), max 3 em paralelo. Cada agente entrega notas cruas em `pesquisa/notas/*.md` e docs finais em `docs/*/*.md` + acréscimos em `pesquisa/fontes.md`.

Sequência:
1. **Onda 1** (paralelo): modelos, benchmark mercado, benchmark governo, deep dive gov.br.
2. **Onda 2** (paralelo): UX/Service Design, Dados/Analytics, LGPD/Governança.
3. **Onda 3** (sequencial): Product/Superintendente consolida → proposta + validação.
4. **Onda 4**: empacotamento MkDocs.

Status atual sempre em `contexto.md`.

## Base legal aplicável (não esquecer)

- Lei 13.460/2017 — Código de Defesa do Usuário de Serviço Público (obriga avaliação).
- Lei 13.709/2018 — LGPD (base legal: execução de política pública, art. 7º III; minimização, art. 6º III).
- Decreto federal 9.094/2017 — simplificação de serviços.
- Lei 15.263/2025 — linguagem simples nos textos ao cidadão (telas e e-mails).
- Estadual: decretos SETDIG em `10-conhecimento/setdig/` do vault (ver seção do vault acima).

## Contatos SETDIG (referência)

- Secretaria-Executiva de Transformação Digital — SETDIG (vinculada à SEGOV).
- Superintendência de Governo Digital — SGD (responsável direta pelo Portal).
- Superintendência de Tecnologia da Informação — STI (implementação).
- Secretário Executivo: Robson Roberto Duarte de Alencar.

## Vault Obsidian do Fabio — contexto que vive fora deste repo

Caminho: `C:\Users\framos\Documents\SETDIG\conhecimento-obsidian`

Este repo é o **estudo**. O vault guarda o **projeto**: o que foi combinado com a Xvia, o que virou entrega e o histórico das reuniões. Consultar antes de assumir que algo não está decidido.

| Nota | O que tem |
|---|---|
| `20-projeto/xvia-migracao-eds/XviaMigracaoEDS.md` | MOC do projeto Xvia — módulos, contrato, marco legal, reuniões |
| `20-projeto/xvia-migracao-eds/pacotes-to-be/00-pacotes-to-be.md` | Método dos pacotes de entrega TO BE, feedback da Xvia e decisões de formato |
| `20-projeto/xvia-migracao-eds/pacotes-to-be/insumos-avaliacao-servicos.md` | Insumos e decisões desta funcionalidade, do lado do projeto |
| `20-projeto/xvia-migracao-eds/pacotes-to-be/gerar-avaliacao-servicos.py` | **Gera o DOCX** `Avaliacao de Servicos  TO BE v1.docx` e copia para a raiz deste repo |
| `20-projeto/xvia-migracao-eds/pacotes-to-be/Template - Pacote de Entrega TO BE v2.docx` | Template dos pacotes entregues à Xvia |
| `40-reunioes/[X-VIA] 28-07-26 ...md` | Reunião que definiu o modelo anterior (positivo/negativo), depois superado |

### Estudo x pacote de entrega — não confundir

- **Este repo (estudo):** por que o modelo é assim, o que diz o gov.br, base legal, indicadores, plano de validação. Linguagem de diretoria.
- **DOCX TO BE (vault):** o que a Xvia precisa construir na Fase 1 — campos, regras numeradas (RN-XX), pendências (P-XX). Linguagem de especificação para fornecedor.

Os dois contam a mesma história. Mudou regra aqui, conferir o DOCX; mudou no DOCX, conferir aqui. **O DOCX não se edita à mão** — altera-se o script no vault e roda-se de novo; ele salva no vault e copia para este repo.

### Fases do projeto (o DOCX cobre só a Fase 1)

1. **Fase 1** — formulário de avaliação e suas regras, online e presencial.
2. **Fase 2** — sincronização das avaliações com o gov.br.
3. **Fase 3** — gestão dos dados e indicadores (painéis, moderação, leitura por órgão).

## Fora de escopo deste estudo

- Implementação técnica (código, integração com serviço).
- Dashboards prontos (só especificação de indicadores).
- Pesquisa qualitativa com cidadãos (recomendada como próximo passo).
- Comparações com sistemas comerciais SaaS (Qualtrics/Medallia) além do necessário.
