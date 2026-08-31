# Avaliação dos Serviços — Portal MS

Estudo estratégico da **Secretaria-Executiva de Transformação Digital — SETDIG** para definir como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão. Coordenação: Superintendência de Governo Digital (SGD).

## Pergunta central

> Como o Portal MS deve pedir ao cidadão que avalie cada serviço digital que ele usa?

## Referência adotada

**Modelo gov.br** — Central de Qualidade + Ferramenta de Avaliação, normatizado pela Portaria SGD/MGI nº 1.083, de 14/02/2025 (vigente; revisou a Portaria SGD/ME nº 548/2022). Qualquer divergência em relação ao modelo federal é justificada explicitamente ao longo do estudo.

## Recomendação em uma linha

Adotar no Portal MS um **modelo de avaliação simples, voluntário e alinhado ao gov.br**, com adaptação institucional mínima e piloto controlado antes da expansão.

## Documentos do estudo

| # | Documento | Foco |
|---|---|---|
| 1 | [Contexto](docs/01-contexto.md) | Por que avaliar. Escopo. Público. Base legal. |
| 2 | [Referência](docs/02-referencia.md) | gov.br como âncora. Modelos de escala. Cases secundários. |
| 3 | [Modelo proposto](docs/03-modelo-proposto.md) | Desenho: perguntas, escala, fluxo, regras. |
| 4 | [Dados e privacidade](docs/04-dados-e-privacidade.md) | O que coletar, o que não coletar, LGPD, governança. |
| 5 | [Indicadores](docs/05-indicadores.md) | O que a gestão vai acompanhar. |
| 6 | [Validação](docs/06-validacao.md) | Plano para testar antes de escalar. |
| 7 | [Recomendação](docs/07-recomendacao.md) | Decisão, registro, próximos passos. |

## Apresentação executiva

Slides em HTML autocontido para diretoria: [`apresentacoes/avaliacao-servicos-portal-ms.html`](apresentacoes/avaliacao-servicos-portal-ms.html).

## Pesquisa e evidências

- **Fontes:** [`docs/pesquisa/fontes.md`](docs/pesquisa/fontes.md) — bibliografia consolidada.
- **Notas internas:** [`pesquisa/notas/`](pesquisa/notas/) — deep-dives técnicos, pacote TO BE Xvia, notas cruas das ondas de pesquisa. Fora do site público.

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

# 5. Build estrito (falha em warning) — usar antes de publicar
python -m mkdocs build --strict
```

## Identidade visual

Tema **Material for MkDocs** com paleta oficial SEGOV — azul primário `#004F9F`, dark `#003A76`, texto `#30302E`. CSS custom em [`docs/assets/css/segov.css`](docs/assets/css/segov.css), light + dark. Logo oficial SEGOV em [`docs/assets/img/segov-logo.svg`](docs/assets/img/segov-logo.svg).

## Marcadores usados na documentação

- `[FATO]` — informação confirmada por fonte primária.
- `[INTERPRETAÇÃO]` — análise apoiada em evidência.
- `[HIPÓTESE]` — proposição a validar.
- `[RECOMENDAÇÃO]` — sugestão do estudo.
- `**Não identificado**` — buscado sem evidência conclusiva.

## Contato institucional

Secretaria-Executiva de Transformação Digital — SETDIG · Superintendência de Governo Digital — SGD.
