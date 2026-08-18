# Notas — Dados & Analytics (cruas)

Agente Onda 2b. Foco: quais dados a avaliação vai gerar, como organizar, quais indicadores a gestão vai olhar.
Marcadores: `[FATO]` (fonte primária), `[INTERPRETAÇÃO]`, `[HIPÓTESE]`, `**Não identificado**`.
Acesso: 2026-08-18.

---

## 1. Como o gov.br opera hoje (âncora)

1. `[FATO]` A escala é de 1 a 5 estrelas com rótulos (Péssima → Excelente); pergunta única "Como foi sua experiência com o serviço?". Fonte: Portal Gov.br / LabQ.
2. `[FATO]` Após a nota, o cidadão qualifica em até 6 dimensões pré-definidas: **Privacidade, Transparência, Segurança, Resolutividade, Agilidade, Inclusão**. Fonte: LabQ.
3. `[FATO]` Avaliação **voluntária e anônima**; CPF é opcional; a plataforma é "projetada para receber avaliações anônimas". Fonte: Manual API / FAQ.
4. `[FATO]` Existe **Painel de Avaliação de Serviços Federais**, público, com nota média mensal, filtros por órgão, serviço e período. Fonte: Painel Central de Qualidade.
5. `[FATO]` Existe também Painel de Gestão da Qualidade **restrito** (gestor do serviço vê detalhamento). Fonte: notas onda 1 governo.
6. `[FATO]` Métrica pública principal por serviço = **nota média (1–5) + nº de avaliações** exibida na página do serviço. Fonte: notas onda 1.
7. `[FATO]` API expõe endpoints de consulta: `porCidadao`, `porOrgao`, `porServico`, `porProtocolo` — permite agregação externa. Fonte: manual-avaliacao.servicos.gov.br FAQ.
8. `[HIPÓTESE]` Retenção/anonimização não documentada publicamente pela SGD; provável seguir LGPD art. 6º (necessidade) e art. 16 (eliminação após finalidade). `**Não identificado**` prazo formal.
9. `[FATO]` GOV.UK publica satisfação **no mínimo mensalmente** por serviço em `data.gov.uk`. Referência de cadência.
10. `[FATO]` Lei 13.460/2017 art. 23 exige publicação **integral** dos resultados de satisfação no sítio do órgão, com ranking de mais reclamados.

---

## 2. Métrica principal — opções

**Opção A — Nota média (1–5).** Simples, é o que o gov.br publica na página do serviço. Fácil de comunicar ("4,3 estrelas"). Sensível a outliers em N baixo.

**Opção B — % satisfeitos (top-2-box: notas 4+5).** Padrão CSAT clássico. Reporta como "% dos cidadãos satisfeitos com o serviço". Aderente ao Estado (RS reporta 89% muito satisfeitos+satisfeitos). Perde granularidade acima do 4.

**Opção C — CSAT + qualificadores (o modelo gov.br).** Nota média como headline + distribuição das 6 dimensões marcadas. Espelha o federal. Comparável nacionalmente.

**Opção D — Índice composto (ACSI-like).** Requer modelo econométrico. `[INTERPRETAÇÃO]` Fora do escopo de capacidade analítica atual da SETDIG.

`[RECOMENDAÇÃO]` **Opção C**. Reportar dois números: **nota média (1–5)** como headline e **% satisfeitos (4+5)** como leitura complementar. Publicar distribuição das dimensões qualificadoras como diagnóstico. Justificativa: aderente ao gov.br (comparabilidade nacional), duplo indicador cobre público leigo (estrelas) e técnico (%).

---

## 3. Indicadores mínimos (rascunho)

| # | Indicador | Fórmula | Uso |
|---|-----------|---------|-----|
| 1 | Nota média do serviço | Σ notas ÷ N | Headline público na página do serviço |
| 2 | % Satisfeitos | (n₄ + n₅) ÷ N × 100 | Comparação entre serviços, meta ≥ 80% |
| 3 | Distribuição das notas | %n₁, %n₂, %n₃, %n₄, %n₅ | Diagnóstico (bimodal? cauda ruim?) |
| 4 | Nº total de avaliações no período | count() | Volume / confiabilidade da amostra |
| 5 | Taxa de resposta | avaliações ÷ conclusões do serviço × 100 | Saúde do instrumento (baixa = viés) |
| 6 | Top dimensões positivas | ranking das 6 marcadas em notas 4+5 | O que está funcionando |
| 7 | Top dimensões negativas | ranking das 6 marcadas em notas 1+2 | Onde focar melhoria |
| 8 | Variação mensal | (nota mês − nota mês-1) | Alerta de queda |
| 9 | % comentários com termo crítico | regex simples em campo livre | Sinal qualitativo |
| 10 | % avaliações de PcD (autodeclarado) | n_pcd ÷ N × 100 | Recorte de acessibilidade |

`[INTERPRETAÇÃO]` Indicadores 1–4 obrigatórios (mínimo viável). 5–7 desejáveis desde o dia 1. 8–10 evolutivos.

---

## 4. Dimensões analíticas (para BI)

Cada avaliação vira uma linha em fato_avaliacao com chaves:

- **Serviço** (id_servico → dim_servico com nome, categoria, órgão responsável)
- **Órgão** (id_orgao → dim_orgao com sigla, secretaria, poder)
- **Canal** (web, mobile, presencial-com-QR)
- **Tempo** (data, hora, mês, trimestre, ano)
- **Etapa da jornada** (opcional: início / durante / fim — a Portaria gov.br recomenda "ao concluir")
- **Município do cidadão** (opcional, agregado, nunca CEP exato — LGPD)
- **Origem UTM** (opcional: veio de campanha, busca orgânica, portal)

`[RECOMENDAÇÃO]` Manter dim_servico e dim_orgao alinhadas com o cadastro do Portal MS (chave = mesmo id do catálogo de serviços). Evita duplicidade e permite join com métricas de uso.

---

## 5. Schema mínimo (conceitual)

```
fato_avaliacao
├── id_avaliacao         PK, uuid
├── id_servico           FK → dim_servico
├── id_orgao             FK → dim_orgao
├── canal                enum: web | mobile | qr_presencial
├── timestamp            datetime
├── nota                 int 1..5, NOT NULL
├── dimensoes_marcadas   array[enum] das 6 dimensões
├── comentario           text nullable, max 2000
├── pcd_autodeclarado    bool nullable
├── id_sessao_hash       string (hash SHA-256 de sessão + salt), para dedupe
├── protocolo_servico    string nullable (link com o serviço concluído)
└── origem_utm           jsonb nullable {source, medium, campaign}

dim_servico
├── id_servico, nome, slug, categoria, orgao_responsavel, ativo_desde

dim_orgao
├── id_orgao, sigla, nome, secretaria, esfera
```

`[RECOMENDAÇÃO]` **Nunca** guardar CPF, IP bruto ou user_agent completo. `id_sessao_hash` = SHA-256(session_id + salt_diário) — permite deduplicar cliques repetidos no mesmo dia sem identificar o cidadão. Salt roda diário para impedir reidentificação retroativa.

`[RECOMENDAÇÃO]` `comentario` guardado como texto livre com **classificador de PII** antes de expor em dashboard (remover CPF/telefone/email por regex se cidadão colar por engano — LGPD art. 6º VII, princípio de segurança).

---

## 6. Retenção

| Categoria | Retenção | Justificativa |
|-----------|----------|---------------|
| Dado bruto (linha completa) | **24 meses** | Cobre série histórica anual + comparação ano-a-ano |
| Comentário aberto | **12 meses** | Risco maior de PII inadvertida; após, deletar texto e manter só flag "teve comentário" |
| Agregados mensais (nota média, %, contagens) | **indefinido** | Anonimizados por natureza; alimentam série histórica |
| id_sessao_hash | **90 dias** | Suficiente para dedupe; depois vira NULL |
| PcD flag | mesma retenção da linha | Dado sensível (art. 11 LGPD); usar só agregado |

`[RECOMENDAÇÃO]` Publicar política de retenção junto com a Política de Privacidade do Portal.

---

## 7. Dashboards — 3 audiências

1. **Alta gestão SETDIG (semanal, 1 tela):** nota média do Portal (todos serviços), Top 10 e Bottom 10 serviços, volume total, variação semana-anterior, alerta de queda > 0,5 estrela. Referência: Painel Federal.
2. **Gestor do serviço (diário):** série diária, distribuição de notas, dimensões negativas do serviço, últimos 20 comentários abertos. Filtro por canal.
3. **Ouvidoria (contínuo):** fila de comentários com notas 1–2 para triagem, integração com Fala.BR (canal manifestação). `[HIPÓTESE]` Fala.BR aceita ingestão via API; validar com CGU.

---

## 8. Integração e publicação

- `[RECOMENDAÇÃO]` **Integrar com API gov.br** (endpoints por servico/orgao) desde o dia 1 — MS recebe URL de avaliação padronizada e seus dados entram no ranking nacional. Custo: aderir à Portaria 548/2022; ganho: comparabilidade + evita duplicar solução.
- `[RECOMENDAÇÃO]` Publicar **CSV mensal em dados.ms.gov.br** (se existir) com agregados por serviço: id_servico, mês, N, nota_media, pct_satisfeitos, dimensoes. Cumpre Lei 13.460 art. 23 (publicação integral).
- `[RECOMENDAÇÃO]` Página pública `/servicos/{slug}/avaliacoes` com nota + N + distribuição — espelho do que gov.br faz.

---

## 9. Alertas automáticos (mínimos)

1. **Queda súbita**: nota semanal < nota das 4 semanas anteriores − 0,5 → e-mail ao gestor.
2. **Nota baixa recorrente**: 3 meses consecutivos com média < 3,0 → escalar SGD.
3. **Volume zero**: serviço com > 100 conclusões/mês e 0 avaliações → verificar integração quebrada.
4. **Comentário com termo crítico**: regex `("processo"|"corrupção"|"denúncia"|"impossível")` → triagem Ouvidoria.

`[INTERPRETAÇÃO]` Todos implementáveis com SQL agendado; não precisa ferramenta específica.

---

## 10. Lacunas / a validar

- `**Não identificado**` prazo formal de retenção usado pela SGD federal.
- `**Não identificado**` schema exato exposto pela API federal (só endpoints listados no FAQ).
- `[HIPÓTESE]` Portal MS terá volume suficiente para ranking mensal significativo — depende de nº de serviços digitalizados.
- `[HIPÓTESE]` Integração com Fala.BR viável tecnicamente — validar com CGU/Ouvidoria estadual.
- **Ferramenta de BI**: MS já tem Power BI/Metabase corporativo? `**Não identificado**` neste estudo.
