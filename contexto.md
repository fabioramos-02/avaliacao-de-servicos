# Contexto do repositório

Documento vivo do estudo **Avaliação dos Serviços do Portal MS**. Atualiza a cada marco relevante.

---

## Objetivo

Definir como o Portal de Serviços do MS vai avaliar seus serviços digitais junto ao cidadão.

Ponto de partida: **replicar/adaptar o modelo do gov.br** (Central de Qualidade + Ferramenta de Avaliação), padronizado pela Portaria SGD/MGI nº 1.083/2025 (revisora da 548/2022). É o padrão nacional adotado pelo MGI e o que outros entes públicos seguem.

## Referências oficiais

- Central de Qualidade — https://www.gov.br/governodigital/pt-br/estrategias-e-governanca-digital/transformacao-digital/central-de-qualidade
- Ferramenta de Avaliação — https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao
- Portaria SGD/MGI nº 1.083/2025 (vigente).
- Portaria SGD/ME nº 548/2022 (norma anterior; dispositivos herdados).
- Lei nº 13.460/2017 — Código de Defesa do Usuário de Serviços Públicos.
- Lei nº 13.709/2018 — LGPD.

## Estrutura do repositório

```
avaliacao-de-servicos/
├── CLAUDE.md                    Contexto para Claude Code
├── README.md                    Índice executivo do estudo
├── contexto.md                  Este documento — plano vivo
├── mkdocs.yml                   Configuração da documentação
├── requirements.txt             Dependências Python
│
├── docs/                        Documentação navegável (7 documentos)
│   ├── index.md                 Landing
│   ├── 01-contexto.md
│   ├── 02-referencia.md
│   ├── 03-modelo-proposto.md
│   ├── 04-dados-e-privacidade.md
│   ├── 05-indicadores.md
│   ├── 06-validacao.md
│   ├── 07-recomendacao.md
│   ├── assets/img/              Logo SEGOV + brasão MS + capturas gov.br
│   ├── assets/css/segov.css     Tema visual
│   └── pesquisa/fontes.md       Bibliografia consolidada (público)
│
├── pesquisa/                    Pesquisa privada (fora do site)
│   └── notas/
│       ├── auditoria-conteudo.md
│       ├── to-be-xvia.md
│       ├── deep-dives-modelos.md
│       ├── deep-dives-benchmark.md
│       └── (notas cruas: modelos, governo, produtos, dados-analytics)
│
└── apresentacoes/
    ├── avaliacao-servicos-portal-ms.html
    └── assets/                  (logo copiado para renderização standalone)
```

## Marco atual — 2026-08-28

**Consolidação executiva concluída.** Repositório reduzido de 8 subpastas em `docs/` (~25 arquivos) para **7 documentos planos** alinhados à âncora gov.br. Material técnico e deep-dives preservados em `pesquisa/notas/`. Apresentação executiva HTML criada em `apresentacoes/`.

Trilha completa da consolidação em [`pesquisa/notas/auditoria-conteudo.md`](pesquisa/notas/auditoria-conteudo.md).

## Marcos anteriores

- **2026-08-25 — Decisões SGD:** escopo restrito a serviços que nascem no orquestrador X-VIA; avaliação passa a ser identificada (base LGPD: execução de política pública em vez de anonimato); proposta prévia de retorno ao cidadão por e-mail transacional com link único.
- **2026-08-18 — Recomendação inicial:** modelo B (gov.br + adaptação MS leve) escolhido em comparação estruturada. Ver [7. Recomendação](docs/07-recomendacao.md).
- **Ondas 1 a 5:** pesquisa concluída — modelos, referências (gov.br + secundários), UX/Service Design, Dados/Analytics, LGPD/Governança, proposta + validação, empacotamento MkDocs, especificação TO BE Xvia v1.

## Entregas prontas

- Recomendação final: [`docs/07-recomendacao.md`](docs/07-recomendacao.md).
- Modelo proposto: [`docs/03-modelo-proposto.md`](docs/03-modelo-proposto.md).
- Dados e privacidade: [`docs/04-dados-e-privacidade.md`](docs/04-dados-e-privacidade.md).
- Plano de validação: [`docs/06-validacao.md`](docs/06-validacao.md).
- Apresentação executiva: [`apresentacoes/avaliacao-servicos-portal-ms.html`](apresentacoes/avaliacao-servicos-portal-ms.html).
- Pacote TO BE Xvia (contrato com fornecedor, para validação técnica): [`pesquisa/notas/to-be-xvia.md`](pesquisa/notas/to-be-xvia.md).

## Direcionamentos de gestão (ago/2026)

- O MS opera **instrumento próprio** de avaliação, hospedado no Portal Único — não integração direta com a ferramenta federal nesta onda.
- Os dados podem ser cedidos ao gov.br via API quando necessário — escopo de documento separado, fora do pacote TO BE atual.
- As métricas devem **apoiar o contrato de gestão do Governo do Estado** — indicadores propostos em [5. Indicadores](docs/05-indicadores.md) seção "Contrato de gestão", pendentes de pactuação formal.

## Próximos passos (fora deste estudo)

1. Levar recomendação para deliberação da diretoria SETDIG.
2. Escolher serviço piloto conforme critérios em [6. Validação](docs/06-validacao.md).
3. Parecer jurídico e RIPD.
4. Piloto de 3 meses.
5. Go / no-go pós-piloto.

## Como rodar a documentação

```bash
pip install -r requirements.txt
python -m mkdocs serve -a 127.0.0.1:8000
```

Build estático: `python -m mkdocs build`. Build estrito: `python -m mkdocs build --strict`.

## Princípios do estudo

1. **gov.br é a âncora.** Divergir do padrão federal exige justificativa explícita.
2. **Menos é mais.** Cidadão de serviço público não tolera formulário longo.
3. **Coletar só o que será usado.** LGPD art. 6º, III (minimização).
4. **Fechar o ciclo.** Avaliação sem uso vira ruído.
5. **Comparável.** Indicador precisa permitir comparação entre serviços e no tempo.
6. **Linguagem simples.** Documento voltado a decisor, não a especialista.

## Marcadores usados

- `[FATO]` — informação confirmada por fonte primária.
- `[INTERPRETAÇÃO]` — análise baseada em evidência.
- `[HIPÓTESE]` — proposição a validar.
- `[RECOMENDAÇÃO]` — sugestão do estudo.
- `**Não identificado**` — buscado, sem evidência conclusiva.
