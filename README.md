<img src="./assets/faixa-portfolio-v1.svg" alt="Alan Joffre — portfólio" width="100%">

<p>
<a href="https://alanjoffre.github.io/my-profile/assets/curriculo_alanjoffre_ptbr.pdf"><img src="./assets/btn-curriculo-v1.svg" alt="Baixar currículo (PDF)" width="194" height="52"></a>
<a href="https://www.linkedin.com/in/alanjoffre"><img src="./assets/btn-linkedin-v1.svg" alt="LinkedIn" width="106" height="52"></a>
<a href="https://alanjoffre.github.io/my-profile/"><img src="./assets/btn-pagina-v1.svg" alt="Página pessoal" width="148" height="52"></a>
<a href="https://github.com/alanjoffre"><img src="./assets/btn-github-v1.svg" alt="GitHub" width="97" height="52"></a>
</p>

**Engenheiro de Dados** · [Noron.dev](https://noron.dev) · São Paulo, SP

## Em 30 segundos

- **Dados:** lakehouse em Databricks e dbt em cliente real, com o tempo de apuração reduzido de até 20 para 2 dias; aqui, a mesma abordagem (Medallion, dbt, qualidade de dados) em projetos open source com dados públicos ou sintéticos, com testes e CI.
- **IA aplicada com avaliação:** RAG, fine-tuning e Text-to-SQL medidos com intervalo de confiança (IC) e avaliação como gate de CI.
- **Back-end:** Python/FastAPI em produção na Aira, produto de IA da Noron.dev, e um banco digital fictício em Java com concorrência medida.

Cada projeto abaixo segue o mesmo molde: o problema, a decisão principal, o resultado medido, a stack e os links. Os números vêm de testes ou de medições versionadas no repositório. Os projetos abertos são feitos com apoio de assistente de IA; o escopo, as decisões de arquitetura e as medições são meus, e revisei o resultado.

## Engenharia de dados

### oss-lakehouse — lakehouse sobre dados reais do GitHub

<p>
<img src="./assets/selo-lakehouse-notebooks-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-lakehouse-testes-v1.svg" alt="" width="68"" height="68">
</p>

- **Problema:** aprender e mostrar engenharia de dados em Databricks sem depender de conta de nuvem, sobre dados reais.
- **Decisão:** o mesmo código roda localmente (PySpark e Delta Lake) e no Databricks (job em Declarative Automation Bundles, antes Databricks Asset Bundles). A infraestrutura Azure está em Terraform, verificada com `terraform validate`, sem `apply`.
- **Resultado:** 18 notebooks executados, com o resultado na própria célula, e um pacote Python com mais de 180 testes e CI. Cobre ingestão incremental, MERGE e SCD2, Structured Streaming, modelagem dimensional, qualidade e contratos, performance no Spark com data skew real, governança e LGPD, e IA dentro do pipeline avaliada contra gabarito.
- **Stack:** PySpark · Delta Lake · Databricks · Terraform · GitHub Actions
- **Links:** [repositório do oss-lakehouse](https://github.com/alanjoffre/oss-lakehouse) · [guia de estudo com 199 perguntas respondidas](https://github.com/alanjoffre/oss-lakehouse/blob/main/GUIA_DE_ESTUDO.md)

### toll-analytics-platform — plataforma de dados de ponta a ponta

<p>
<img src="./assets/selo-toll-workflows-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-toll-duckdb-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-toll-databricks-v1.svg" alt="" width="68"" height="68">
</p>

- **Problema:** construir do zero, com ferramentas abertas e dados sintéticos, uma plataforma de dados completa. O repositório não contém código, dado nem regra de empregador ou cliente.
- **Decisão:** desenvolvimento em DuckDB, sem custo e reprodutível; desenhado para Databricks sem alterar o SQL (infraestrutura em Terraform, verificada com `terraform validate`, sem `apply`).
- **Resultado:** modelagem Medallion com contracts, unit tests, Semantic Layer e dbt Mesh; CI/CD com 10 workflows (Slim CI, gate de Data Quality, promoção de staging para produção); [dashboard ao vivo](https://alanjoffre.github.io/toll-analytics-platform/).
- **Stack:** dlt · dbt · Airflow com Cosmos · Soda · OpenLineage · Evidence.dev · Kafka (Redpanda) · Terraform
- **Links:** [repositório do toll-analytics-platform](https://github.com/alanjoffre/toll-analytics-platform) · [dashboard ao vivo](https://alanjoffre.github.io/toll-analytics-platform/)

```mermaid
flowchart TB
  SRC["CSV e eventos"] --> ING["dlt"]
  ING --> LAND[("landing<br/>DuckDB (executado)<br/>Databricks (desenhado, sem apply)")]
  LAND --> T["dbt<br/>Medallion · contracts<br/>Semantic Layer · Mesh"]
  T --> DQ["Data Quality<br/>Soda · Elementary"]
  T --> BI["BI<br/>Evidence.dev"]
  ORCH["Airflow com Cosmos"] -.->|orquestra| ING
  ORCH -.->|orquestra| T
  OBS["OpenLineage<br/>Prometheus e Grafana"] -.->|observa| ORCH
```

## Engenharia de IA

### RodoIA — engenharia de IA de ponta a ponta

<p>
<img src="./assets/selo-rodoia-f1-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-rodoia-hit5-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-rodoia-gate-v1.svg" alt="" width="68"" height="68">
</p>

- **Problema:** ir além de "chamar a API de um modelo": do backpropagation escrito à mão ao serving em produção, sobre a regulação e os dados abertos da ANTT.
- **Decisão:** motor de dados escolhido por benchmark (DuckDB 6,7 vezes mais rápido que o Spark, sem divergências) e avaliação como gate de CI, que barra a entrega quando a qualidade cai.
- **Resultado:** RAG com hit@5 de 0,62 (IC 0,48 a 0,74) e precisão de citação de 0,92; fine-tuning QLoRA em NER jurídico (reconhecimento de entidades) com F1 de 0,13 para 0,77, servido com vLLM a 205 tokens/s; agente em LangGraph com roteamento de 0,95 (n=21); gate 30/30 e 302 testes (285 no CI).
- **Stack:** PyTorch · Hugging Face · Qdrant · LangGraph · vLLM · DuckDB · MLflow · DVC
- **Links:** [repositório do RodoIA](https://github.com/alanjoffre/rodoia) · [demo ao vivo](https://huggingface.co/spaces/alanjoffre/rodoia-rag) · [a história do projeto](https://github.com/alanjoffre/rodoia/blob/main/docs/HISTORIA.md)

O diferencial não são os números altos, e sim o rigor de corrigir os próprios números: o conjunto held-out desfez a memorização, o backtest desfez uma escolha a dedo e a auditoria humana encontrou 16% dos rótulos de referência errados.

```mermaid
flowchart TB
  Q["Pergunta do usuário"] --> AG["Agente (LangGraph)<br/>guardrail → roteador<br/>→ síntese"]
  AG --> RAG["RAG<br/>regulatório<br/>E5 + BM25<br/>+ RRF"]
  AG --> FT["Modelo com<br/>fine-tuning<br/>QLoRA ·<br/>vLLM fp8"]
  AG --> DADOS["Dados<br/>estruturados<br/>DuckDB ·<br/>previsão"]
  RAG & FT & DADOS --> BASE["Fundamentos de ML<br/>backpropagation e<br/>attention à mão"]
  MLOPS["MLOps: gate de CI<br/>MLflow · DVC<br/>drift · custo"] -.->|governa| AG
```

### RodoQuery — Text-to-SQL sobre camada semântica

<p>
<img src="./assets/selo-rodoquery-exec-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-rodoquery-testes-v1.svg" alt="" width="68"" height="68">
</p>

- **Decisão:** o agente consulta a camada semântica (Semantic Layer) em vez de escrever SQL cru, com avaliação por execução e guardrails.
- **Resultado:** 100% (IC 97,4 a 100) contra 44,5% do SQL direto, n=146, em dados reais da ANTT; 251 testes.
- **Links:** [repositório do RodoQuery](https://github.com/alanjoffre/rodoquery)

### NãoConsta — RAG contratual avaliado pelo que recusa

<p>
<img src="./assets/selo-naoconsta-perguntas-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-naoconsta-semresposta-v1.svg" alt="" width="68"" height="68">
</p>

- **Decisão:** medir o agente pela capacidade de responder "não consta no contrato" quando a resposta não existe.
- **Resultado:** benchmark CUAD com 510 contratos e 20.910 perguntas, 68% delas sem resposta no contrato.
- **Links:** [repositório do NãoConsta](https://github.com/alanjoffre/naoconsta)

## Back-end em Java

### Ledgerly Bank — banco digital fictício em Java

<p>
<img src="./assets/selo-ledgerly-saques-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-ledgerly-mutacao-v1.svg" alt="" width="68"" height="68">
<img src="./assets/selo-ledgerly-testes-v1.svg" alt="" width="68"" height="68">
</p>

- **Problema:** mostrar back-end de sistema financeiro com consistência de saldo sob concorrência, construído do zero e em público.
- **Decisão:** razão contábil em partidas dobradas e Pix com Saga, Outbox e Kafka; extrato em CQRS (MongoDB).
- **Resultado:** saldo sem gasto duplo sob 1.500 saques simultâneos; 1.141 testes, 96,7% de mutação no domínio, 92,6% de cobertura e contratos com Pact; 47 ADRs (registros de decisão de arquitetura).
- **Stack:** Java 25 · Spring Boot · Quarkus · Kafka · MongoDB · Keycloak · ONNX · React
- **Links:** [repositório do Ledgerly Bank](https://github.com/alanjoffre/ledgerly-bank)

## Em produção: Aira

<p>
<img src="./assets/selo-aira-producao-v1.svg" alt="" width="68"" height="68">
</p>

**Aira**, produto de IA da Noron.dev, em produção na AWS desde maio/2026. Sou o responsável técnico pelo desenvolvimento e pela operação. Código fechado.

- **IA com permissão e fonte:** conduzi o desenho para que a IA consulte os arquivos da empresa só com ferramentas de leitura (recuperação agêntica), responda só com o que aquela pessoa tem permissão de ver e cite as fontes.
- **Avaliação e custo:** respostas avaliadas (mais de 30 casos em 7 categorias, dados fictícios, conferência determinística) antes de mudar prompt, modelo ou esforço; fila, limite por minuto, cota mensal e teto de gasto que bloqueia ou passa ao modelo mais econômico.
- **Operação:** Python/FastAPI e PostgreSQL em Docker na AWS; mais de 5.000 testes de back-end, trilha de auditoria encadeada por hash, backup diário cifrado (o deploy só segue com o backup externo confirmado) e mais de 60 versões publicadas.

## Trabalhos anteriores: machine learning

<details>
<summary><b>Ver uma seleção de 4 projetos de ML aplicado</b></summary>
<br>

- [Detecção de anomalias em tarifas](https://github.com/alanjoffre/data-science/tree/master/projetos/logistica_transporte/4_deteccao_de_anomalias_em_tarifas) — modelos supervisionados e não supervisionados em tarifas de viagens compartilhadas.
- [Clusterização de séries temporais](https://github.com/alanjoffre/data-science/tree/master/projetos/logistica_transporte/3_analise_desempenho_viagens_agrupadas_clusterizacao_series_temporais) — janelas sobrepostas e clusterização (K-Shape, DBSCAN), com Optuna e MLflow.
- [Detecção de fraude em cartão](https://github.com/alanjoffre/data-science/tree/master/projetos/creditcard_fraud_detection) — Random Forest para detectar fraude, servido em streaming com Flask e Kafka.
- [Reconhecimento facial e detecção de objetos](https://github.com/alanjoffre/data-science/tree/master/projetos/reconhecimento_facial_e_deteccao_de_objetos) — visão computacional em tempo real, integrada a uma aplicação web.

Os demais projetos de ciência de dados estão no repositório [data-science](https://github.com/alanjoffre/data-science).

</details>
