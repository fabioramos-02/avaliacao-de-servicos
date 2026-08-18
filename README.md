# Avaliação dos Serviços — Portal do MS

Estudo estratégico da **Secretaria-Executiva de Transformação Digital — SETDIG** para definir como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão.

**Referência principal:** modelo do gov.br — Central de Qualidade + Ferramenta de Avaliação (Portaria SGD/ME nº 548/2022).

## Estado atual e plano de trabalho

Ver [`contexto.md`](contexto.md) — documento vivo com o status das ondas de pesquisa e onde paramos.

## Como executar a documentação

Pré-requisitos: Python 3.10+.

```bash
# 1. Ambiente virtual (opcional)
python -m venv .venv
.venv\Scripts\activate           # Windows PowerShell

# 2. Instalar dependências
pip install -r requirements.txt

# 3. Servidor local com hot reload
python -m mkdocs serve -a 127.0.0.1:8000

# 4. Build estático
python -m mkdocs build
```

## Estrutura

```
avaliacao-de-servicos/
├── contexto.md                  Plano de trabalho e status
├── CLAUDE.md                    Contexto para Claude Code
├── README.md                    Este arquivo
├── mkdocs.yml                   Configuração da documentação
├── requirements.txt             Dependências Python
├── docs/                        Documentação navegável
│   ├── assets/img/              Logos oficiais SEGOV
│   ├── assets/css/segov.css     Tema visual
│   ├── 01-contexto/             Panorama do estudo
│   ├── 02-modelos/              NPS, CSAT, CES, escalas
│   ├── 03-benchmark/            gov.br (âncora) + secundários
│   ├── 04-cidadao/              O que perguntar + LGPD
│   ├── 05-proposta/             Modelo MS + matriz decisão
│   ├── 06-validacao/            Estratégia com stakeholders
│   └── 07-conclusao/            Recomendação executável
└── pesquisa/                    Notas cruas, evidências, bibliografia
    ├── fontes.md
    ├── evidencias.md
    └── notas/
```

## Principais entregas

| Entrega | Onde encontrar |
|---|---|
| Recomendação final | `docs/07-conclusao/recomendacao.md` |
| Modelo proposto ao MS | `docs/05-proposta/modelo-proposto.md` |
| Detalhe da Ferramenta gov.br | `docs/03-benchmark/gov-br.md` |
| Panorama de modelos (NPS/CSAT/CES) | `docs/02-modelos/` |
| Análise LGPD | `docs/04-cidadao/lgpd.md` |
| Estratégia de validação | `docs/06-validacao/estrategia.md` |
| Bibliografia | `pesquisa/fontes.md` |

## Design visual

Tema Material for MkDocs com paleta oficial SEGOV (azul `#004F9F`), fonte system-ui e logo institucional. CSS customizado em `docs/assets/css/segov.css` para modo claro e escuro.

## Marcadores usados na documentação

- `[FATO]` — informação confirmada por fonte primária.
- `[INTERPRETAÇÃO]` — análise apoiada em evidência.
- `[HIPÓTESE]` — proposição a validar.
- `[RECOMENDAÇÃO]` — sugestão do estudo.
- `**Não identificado**` — buscado sem evidência conclusiva.

## Contato

Secretaria-Executiva de Transformação Digital — SETDIG · Superintendência de Governo Digital — SGD
