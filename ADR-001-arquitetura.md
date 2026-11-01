# ADR-001: Monorepo e Clickhouse como Data Warehouse

## Status

Aceito.

## Contexto

O projeto consiste em uma plataforma de dados para um marketplace fictício de delivery.

A solução possui diferentes componentes:

- API transacional.
- Simulador de dados.
- Processamento de eventos.
- Orquestração de pipelines.
- Transformação de dados.
- Camada analítica.

Precisamos organizar esses componentes de maneira
que o desenvolvimento e a manutenção sejam simples.

## Decisão 1: Monorepo

Utilizaremos uma arquitetura monorepo.

Todos os serviços ficarão dentro de um único repositório Git, separados por responsabilidade.

### Justificativa

- Facilita o desenvolvimento local.
- Centraliza a documentação.
- Simplifica o versionamento.
- Facilita a integração entre serviços.
- Permite CI centralizada

## Decisão 2: Clickhouse como Data Warehouse

Utilizaremos Clickhouse para armazenamento analítico.

O PostgreSQL continuará sendo banco operacional.

### Justificativa 

O postgreSQL será responsável pelas operações transacionais, enquanto o ClickHouse será utilizado 
para consultas analíticas e agregações em grande volume.

### Consequências

- Existirá uma separação entre OLTP e OLAP.
- Será necessário implementar processos de ingestão.
- Precisaremos tratar deduplicação e idempotência.
- O dbt será responsável pelas transformações analíticas.

## Arquitetura inicial

PostgreSQL -> Airflow -> ClickHouse -> dbt

## Tecnologias futuras

- Python
- Node.js
- Redis
- Apache Airflow
- dbt Core
- ClickHouse
- Docker
