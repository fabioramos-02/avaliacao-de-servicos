# CLAUDE.md — Avaliação dos Serviços do Portal MS

Contexto para futuras sessões do Claude Code neste repositório.

## O que é

Estudo estratégico da **Secretaria-Executiva de Transformação Digital (SETDIG)** para definir como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão. Coordenação: Superintendência de Governo Digital (SGD).

## Regra número 1 — gov.br é a âncora

**A referência principal é o gov.br**, especificamente:

1. Central de Qualidade — https://www.gov.br/governodigital/pt-br/estrategias-e-governanca-digital/transformacao-digital/central-de-qualidade
2. Ferramenta de Avaliação — https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao
3. Portaria SGD/ME nº 548/2022 (padrão nacional do instrumento).

Outros benchmarks (iFood, Uber, Airbnb, GOV.UK) são referências secundárias. Qualquer divergência do modelo gov.br precisa de justificativa explícita no documento.

## Modelo padrão gov.br (memorize)

- Pergunta: **"Como foi a sua experiência com o serviço?"**
- Escala: 5 estrelas rotuladas — **Péssima / Ruim / Mais ou menos / Boa / Excelente**.
- Pergunta 2 (opcional): "O que você mais gostou em nosso serviço?" — 6 cards, marque até 3 (Fácil de usar, Site/app funcionou bem, Informações claras, Consegui resolver, Foi rápido, Fácil de encontrar).
- Campo aberto opcional (até 2000 chars).
- Bloco acessibilidade opcional (autodeclaração PcD).

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
└── pesquisa/
    ├── fontes.md            Bibliografia consolidada
    ├── evidencias.md        Trechos-chave
    └── notas/               Notas cruas dos agentes de pesquisa
```

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
- Estadual: verificar decretos SETDIG específicos em `10-conhecimento/setdig/` do vault do Fabio se necessário.

## Contatos SETDIG (referência)

- Secretaria-Executiva de Transformação Digital — SETDIG (vinculada à SEGOV).
- Superintendência de Governo Digital — SGD (responsável direta pelo Portal).
- Superintendência de Tecnologia da Informação — STI (implementação).
- Secretário Executivo: Robson Roberto Duarte de Alencar.

## Fora de escopo deste estudo

- Implementação técnica (código, integração com serviço).
- Dashboards prontos (só especificação de indicadores).
- Pesquisa qualitativa com cidadãos (recomendada como próximo passo).
- Comparações com sistemas comerciais SaaS (Qualtrics/Medallia) além do necessário.
