# Delivery Data Platform

Plataforma de engenharia de dados para um
marketplace fictício de delivery.

## Objetivo

Construir uma plataforma capaz de processa,
armazenar e transformar dados transacionais
e eventos de comportamento.

## Arquitetura

PostgreSQL -> Airflow -> ClickHouse -> dbt


## Tecnologias

- Python
- Node.js
- PostgreSQL
- Redis
- ClickHouse
- Apache Airflow
- dbt Core
- Docker

## Estrutura

- infra/: infraestrutura local.
- simulator/: geração de dados.
- services/: serviços Node.js
- orchestration/: pipelines Airflow.
- dbt/: transformações analíticas.
- quality/: validações de dados.
- docs/: documentação ténica.

## Status

Em desenvolvimento.