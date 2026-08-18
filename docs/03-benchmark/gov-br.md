# Benchmark — gov.br (Brasil)

> Fontes: SGD/MGI, Lei 13.460/2017, Decreto 9.094/2017, Portaria SGD/ME 548/2022, manuais oficiais.

## Contexto da plataforma

**gov.br** é o portal único federal de serviços públicos, mantido pela **Secretaria de Governo Digital (SGD)** do Ministério da Gestão e da Inovação em Serviços Públicos (MGI). Reúne mais de 4.000 serviços federais, integra login único (conta gov.br) e é a principal referência nacional replicada por estados e municípios.

## Modelo de avaliação

`[FATO]` **Universal por serviço**. Cada serviço digital publicado em `gov.br/pt-br/servicos` expõe um componente de avaliação. A plataforma central é `avaliacao.servicos.gov.br` — implementa a *"Ferramenta de Avaliação de Satisfação dos Usuários"* dentro do **Modelo de Qualidade dos Serviços Públicos (Portaria SGD/ME 548/2022)**.

Arquitetura em três camadas:

1. **Widget/link no serviço** — cidadão avalia após uso.
2. **API de Avaliação** — órgãos integram para gerar links de acompanhamento.
3. **Painel de Monitoramento + Ranking + Painel de Gestão da Qualidade** — visualização pública (média por serviço) e privada (gestores).

## Perguntas, escala e momento

`[FATO]` **Escala 1 a 5, representada por estrelas**. Ancoragem textual:

| Nota | Rótulo |
|---|---|
| 1 | Péssimo |
| 2 | Ruim |
| 3 | Satisfatório |
| 4 | Bom |
| 5 | Excelente |

`[FATO]` **Estrutura do formulário**:

- **Nota geral** (1–5 estrelas).
- **Escolha de 3 entre 6 critérios/dimensões** avaliados (a plataforma trabalha com 7 dimensões de qualidade: facilidade, comunicação, atendimento, experiência unificada, acessibilidade, privacidade e segurança, escuta ativa; 6 são apresentadas como critérios ao cidadão).
- `[HIPÓTESE]` Campo de comentário livre — API aceita, UI padrão pode ou não exibir.

`[FATO]` **Momento**: após a conclusão do serviço digital. O órgão pode gerar link de avaliação via API ao encerrar o atendimento; alternativamente o widget fica exposto na página do serviço.

`[FATO]` **Dados coletados**: nota, critérios selecionados. **CPF é opcional** — plataforma foi "projetada para receber avaliações anônimas". API não exige identificação do cidadão.

## Uso pela gestão

`[FATO]` A ferramenta é iniciativa do **LabQ (Laboratório de Qualidade dos Serviços Públicos)** da SGD. Uso pela gestão:

- **Diagnóstico** de qualidade por serviço e por órgão.
- **Elaboração de plano de melhoria** com base nas dimensões piores avaliadas.
- **Ranking de serviços** — comparação entre órgãos.
- **Painel de Gestão da Qualidade** — visão detalhada por gestor.

`[FATO]` A média agregada por serviço aparece publicamente na página do serviço no Portal GOV.BR, junto com o número de avaliações.

## Base legal

- **Lei 13.460/2017** (Código de Defesa do Usuário de Serviços Públicos), **art. 23** — obriga órgãos a avaliar 5 aspectos: satisfação, qualidade do atendimento, cumprimento de prazos, quantidade de manifestações, medidas adotadas. Periodicidade mínima **anual** (ou outro meio com significância estatística). **Resultado deve ser integralmente publicado no sítio do órgão**, incluindo ranking de reclamações.
- **Decreto 9.094/2017** — Carta de Serviços ao Usuário + obrigação de ferramenta de pesquisa de satisfação.
- **Portaria SGD/ME 548/2022** — Modelo de Qualidade dos Serviços Públicos federais (operacionalização técnica).
- **Lei 13.709/2018 (LGPD)** — dados pessoais tratados sob hipótese de execução de políticas públicas (art. 7º VII); anonimização recomendada.

## Aprendizados aplicáveis ao MS

1. **Reaproveitar padrão gov.br 1–5 estrelas + critérios** — MS ganha compatibilidade semântica e não reinventa escala; cidadão já reconhece.
2. **Anonimato por default** — CPF opcional é decisão explícita da SGD; reduz atrito e respeita LGPD (menor superfície de dados).
3. **Publicar média por serviço na própria página** — cumpre art. 23 §2º da Lei 13.460 e cria transparência.
4. **Considerar integração com API gov.br** — se serviços de MS já estão catalogados no gov.br, avaliação pode ser federada (`[HIPÓTESE]` viável tecnicamente, precisa validar com SGD).
5. **Escolha de dimensões** — em vez de várias perguntas, uma nota + seleção de dimensões torna o formulário curto (< 1 min) e mensurável.
6. **Ranking interno** — publicar internamente para gestão gera pressão saudável por melhoria.
7. **Alinhar com Fala.MS/Ouvidoria** — avaliação e ouvidoria devem se conversar (Lei 13.460 exige olhar quantidade de manifestações como parte da avaliação).

## Fontes

- Portal de Avaliação: https://avaliacao.servicos.gov.br/
- Ferramenta de Avaliação (SGD): https://www.gov.br/governodigital/pt-br/plataformas-e-servicos-digitais/ferramenta-de-avaliacao
- Modelo de Qualidade — Avaliação de satisfação: https://www.gov.br/governodigital/pt-br/estrategias-e-governanca-digital/transformacao-digital/ferramentas/modelo-de-qualidade-dos-servicos-digitais/avaliacao-de-satisfacao-dos-usuarios
- Manual da API de Avaliação (FAQ): https://manual-avaliacao.servicos.gov.br/pt-br/latest/faq.html
- Notícia MGI (2024) — nova ferramenta: https://www.gov.br/gestao/pt-br/assuntos/noticias/2024/abril/gestao-lanca-nova-ferramenta-de-avaliacao-dos-servicos-publicos-no-gov.br
- Lei 13.460/2017: https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/lei/l13460.htm
- Decreto 9.094/2017: https://www2.camara.leg.br/legin/fed/decret/2017/decreto-9094-17-julho-2017-785213-normaatualizada-pe.html
- Guia Metodológico de Avaliação (CGU): https://repositorio.cgu.gov.br/bitstream/1/65702/5/Guia_de_Avaliacao_de_Servicos.pdf
