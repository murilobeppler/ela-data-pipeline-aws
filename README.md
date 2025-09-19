# ela-data-pipeline-aws
Compass UOL (SQUAD 5) - Pipeline de dados em AWS para análise da Esclerose Lateral Amiotrófica (ELA/ALS). Projeto em sprints, com foco em construção de Data Lake, ETL com Glue e análises exploratórias com Athena e QuickSight.

# ELA Data Pipeline AWS

Este repositório contém o desenvolvimento de um pipeline de dados em nuvem (AWS) para análise da **Esclerose Lateral Amiotrófica (ELA/ALS)**.  
O objetivo é construir um **Data Lake** organizado em camadas, processar e analisar os dados, e gerar visualizações que ajudem a identificar padrões e tendências da doença.

---

## 🎯 Objetivo Geral
- Construir um **pipeline de dados completo** utilizando serviços da AWS.
- Organizar os dados em camadas (`Raw`, `Trusted`).
- Processar, limpar e padronizar os dados com **AWS Glue (PySpark)**.
- Habilitar consultas exploratórias com **Athena**.
- Criar visualizações com **QuickSight** para gerar insights.

---

## 🗂️ Arquitetura Planejada
A arquitetura geral do projeto será composta por:

1. **Armazenamento** → AWS S3 (camadas Raw e Trusted).  
2. **Catálogo de Dados** → AWS Glue Data Catalog.  
3. **ETL** → AWS Glue Job (PySpark).  
4. **Consulta** → AWS Athena.  
5. **Visualização** → AWS QuickSight.  
6. **Logs** → AWS CloudWatch (monitoramento e acompanhamento dos jobs).  

```mermaid
flowchart TD
    A[CSV Local] -->|Upload boto3| B[S3 Raw]
    B --> C[Glue Crawler]
    C --> D[Glue Data Catalog]
    D --> E[Athena Query]
    B --> F[Glue Job - PySpark]
    F --> G[S3 Trusted - Parquet]
    G --> H[Athena Query Trusted]
    H --> I[QuickSight Dashboards]

