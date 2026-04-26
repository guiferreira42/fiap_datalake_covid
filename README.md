# 📊 PNAD COVID Analytics - Data Lake Project

Projeto de engenharia de dados desenvolvido com base na PNAD COVID-19 (IBGE), com o objetivo de estruturar dados para análise de comportamento da população durante a pandemia.

---

## 🧠 Arquitetura

Este projeto utiliza a arquitetura **Medallion (Bronze → Silver → Gold)**:

- **Bronze**: ingestão de dados brutos
- **Silver**: limpeza, padronização e tipagem
- **Gold**: enriquecimento e modelagem analítica

---

## ☁️ Stack Tecnológica

- AWS S3 (Data Lake)
- AWS Glue (ETL com Spark)
- AWS Athena (consulta SQL)
- Power BI (visualização)
- Python (Pandas + PySpark)

---

## 📁 Estrutura do Projeto
notebooks/
├── etl-bronze-ingestao.ipynb
├── AWS-Glue/
├── etl-silver-covid.ipynb
├── etl-silver-dicionario.ipynb
├── etl-gold-covid.ipynb
---

## 🔄 Pipeline de Dados

1. **Ingestão (Bronze)**
   - Extração de arquivos ZIP
   - Conversão CSV → Parquet
   - Armazenamento no S3

2. **Transformação (Silver)**
   - Seleção de colunas relevantes
   - Padronização de nomes
   - Ajuste de tipos
   - Tratamento de valores nulos

3. **Enriquecimento (Gold)**
   - Integração com dicionário de dados
   - Tradução de códigos para descrições
   - Preparação para consumo analítico

---

## 🧩 Modelagem de Dados

- Base factual com características:
  - Sintomas clínicos
  - Perfil da população
  - Condições econômicas

- Integração com dicionário PNAD para tradução dos códigos

---

## 📊 Visualização

Os dados foram consumidos via **Amazon Athena** e conectados ao **Power BI**, permitindo análises como:

- Frequência de sintomas
- Distribuição por faixa etária
- Comportamento da população
- Indicadores econômicos

---

## 🚀 Como Executar

1. Configurar credenciais AWS
2. Executar notebooks locais para subir dados para o S3
2. Executar notebooks no AWS Glue na ordem:
   - Bronze
   - Silver
   - Gold
3. Criar tabelas no Athena via Glue Crawler
4. Conectar ao Power BI

---

## ⚠️ Observações

- Dados armazenados em formato **Parquet**
- Particionamento por **ano e mês**
- Otimizado para leitura no Athena

---

## 📌 Autor

Guilherme Ferreira
Projeto desenvolvido para o Tech Challenge FIAP
