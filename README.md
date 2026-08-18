# Avaliação dos Serviços — Portal de Serviços do MS

Estudo, benchmark e proposta de modelo de avaliação para os serviços do Portal de Serviços do Mato Grosso do Sul, conduzido pela **Secretaria-Executiva de Transformação Digital — SETDIG**.

## Objetivo

Investigar e definir a melhor estratégia para avaliação dos serviços do Portal do MS, considerando referências de mercado, necessidades do cidadão e objetivos da gestão. O resultado é uma proposta de modelo de avaliação pronta para validação com stakeholders.

## Estrutura do repositório

```
.
├── contexto.md              # Contexto original da Feature (5 PBIs)
├── README.md                # Este arquivo
├── mkdocs.yml               # Configuração da documentação navegável
├── requirements.txt         # Dependências (MkDocs + Material)
├── docs/                    # Documentação técnica em Markdown
│   ├── 01-contexto/         # Feature e objetivos
│   ├── 02-modelos/          # NPS, CSAT, CES, escalas, comparativo
│   ├── 03-benchmark/        # Cases de mercado e governo
│   ├── 04-cidadao/          # O que coletar, perguntas, LGPD
│   ├── 05-proposta/         # Modelo proposto, matriz de decisão
│   ├── 06-validacao/        # Estratégia, stakeholders, aceite
│   └── 07-conclusao/        # Recomendação e próximos passos
└── pesquisa/                # Notas cruas, evidências, bibliografia
    ├── fontes.md
    ├── evidencias.md
    └── notas/
```

## Como executar a documentação

Pré-requisitos: Python 3.10+.

```bash
# 1. Criar ambiente virtual (opcional, recomendado)
python -m venv .venv
source .venv/bin/activate       # Linux/Mac
.venv\Scripts\activate          # Windows PowerShell

# 2. Instalar dependências
pip install -r requirements.txt

# 3. Servidor local com hot reload
mkdocs serve
# Acessar http://127.0.0.1:8000

# 4. Build estático (para publicar)
mkdocs build --strict
# Saída em site/
```

## Principais entregáveis

| Entregável | Onde |
| --- | --- |
| Panorama de modelos (NPS, CSAT, CES) | `docs/02-modelos/` |
| Benchmark de mercado (iFood, Uber, Airbnb, Google, Amazon) | `docs/03-benchmark/` |
| Benchmark de governo digital (GOV.UK, gov.br) | `docs/03-benchmark/` |
| Definição do que coletar do cidadão | `docs/04-cidadao/` |
| Análise LGPD | `docs/04-cidadao/lgpd.md` |
| Proposta de modelo para o Portal MS | `docs/05-proposta/` |
| Matriz de decisão entre alternativas | `docs/05-proposta/matriz-decisao.md` |
| Estratégia de validação com stakeholders | `docs/06-validacao/` |
| Recomendação final e próximos passos | `docs/07-conclusao/` |
| Bibliografia consolidada | `pesquisa/fontes.md` |

## Metodologia

O estudo seguiu 5 PBIs (Product Backlog Items) definidos em `contexto.md` e foi executado por agentes especializados (modelos, benchmark de produtos, benchmark de governo, UX, dados/analytics, LGPD, product management) que consolidaram evidências antes de propor o modelo. Toda afirmação factual sobre um case tem fonte registrada em `pesquisa/fontes.md`.

Marcadores utilizados nos documentos:

- `[FATO]` — informação confirmada por fonte primária.
- `[INTERPRETAÇÃO]` — análise apoiada em evidência.
- `[HIPÓTESE]` — proposição a validar.
- `[RECOMENDAÇÃO]` — sugestão do estudo.
- `**Não identificado**` — informação buscada mas sem evidência conclusiva.

## Contato

Secretaria-Executiva de Transformação Digital — SETDIG
Superintendência de Governo Digital — SGD
