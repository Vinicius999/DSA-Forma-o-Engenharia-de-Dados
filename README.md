<h1 align="center">Formação Engenharia de Dados</h1>

## Data Warehouses, Business Intelligence, Data Marts e OLTPs

![data-warehouse-business-intelligence-datamart-oltp](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/dw-bi-datamart-oltp.png)


### Business Intelligence (BI)
Business intelligence (BI) refere-se a um conjunto de metodologias e recursos que permite às empresas acessar, analisar e desenvolver insights acionáveis a partir de dados para tomar decisões de negócios.

Ref: https://aws.amazon.com/pt/what-is/business-intelligence/

### OLTP
OLTP (Online Transaction Processing) é um banco de dados relacional que registra transações em tempo real em uma determinada operação organizacional. 

Ex: sistema de transações bancárias que registra todas as operações efetuadas em um banco, caixas de multibanco, reservas de viagens ou hotel on-line, Cartões de Crédito.

Ref: https://aws.amazon.com/pt/compare/the-difference-between-olap-and-oltp/

### Data Warehouse (DW)
O Data Warehouse (DW) é o ponto central de uma estrutura de BI. O DW é um banco de dados relacional usado para armazenar **informações consolidadas** relativas às atividades de uma organização.

Possibilita a análise de grandes volumes de dados, que são coletados a partir de sistemas transacionais OLTP.

O DW é organizado para dar suporte a tomada de decisões estratégicas da empresa.

Ref: https://aws.amazon.com/pt/what-is/data-warehouse/

### Data Marts
Um Data Mart é um Data Warehouse que atende às necessidades de uma equipe ou unidade de negócios específica, como finanças, marketing ou vendas.

Ele contém uma parte pequena e selecionada dos dados contidos no DW.

Ele fornece dados resumidos que as principais partes interessadas podem usar para tomar decisões informadas rapidamente.

Ref: https://aws.amazon.com/pt/what-is/data-mart/

## Vantagens do Data Warehouse
- Dados consolidados de várias fontes
- Qualidade, consistência e precisão de dados
- Análise de dados históricos
- Tomada de decisão adequada
- Separação do processamento analítico dos bancos de dados transacionais, o que melhora o desempenho dos dois sistemas

## Características do Data Warehouse
- Orientado ao negócio
- Não volátil
- Variante no tempo

## OLTP x OLAP

**OLTPs** (Online Transaction Processing) são banco de dados que usam **modelagem relacional**, com dados normalizados, projetados para gerenciar dados de sistemas transacionais, como sistema de ERP, CRM, sistema de vendas e sistemas web em geral. **Os OLTPs são fontes de dados para o Data Warehouse.**

**OLAPs** (Online Analytical Processing) bancos de dados que usam **modelagem dimensional** como Star Schema e Snow Flake, com dados denormalizados, projetados para otimizar consultas e relatórios. Os analistas de dados usam um **cubo OLAP** para mostrar simultaneamente a receita de vendas com base em meses, cidades e produtos. Alguns **Data Marts** podem usar o OLAP para estruturar suas informações, mas outros usam estruturas convencionais e normalizadas

Ref: https://aws.amazon.com/pt/compare/the-difference-between-olap-and-oltp/

## Extraction, Transformation e Loading (ETL)

*image-01*

- **Extração**: Fase em que os dados são extraídos das fonte de dados, como os OLTPs, e são conduzidos para a *staging area* (área de transição ou temporária), onde são convertidos para um único formato.
- **Transformação**: É nesta etapa que realizamos os devidos ajustes, podendo assim melhorar a qualidade dos dados e consolidar dados de duas ou mais fontes.
- **Carga**: Consiste em fisicamente estruturar e carregar os dados para seu destino, sendo ele um Data Warehouse ou Data Mart.

## Business Intelligence vs Data Science

![business-intelligence-vs-data-science](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/business-intelligence-vs-data-science.png)
![business-intelligence-vs-data-science-02](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/business-intelligence-vs-data-science-02.png)


## Fases de Design de um Data Warehouse
- **Modelagem de Negócio**: identificar o preblema a ser resolvido.
- **Modelagem Lógico**: identififar se os dados dados suportam a solução proposta na modelagem de negócio.
- **Modelagem Dimensional**: identificar as tabelas **fato** e **dimensões**.
- **Modelagem Físico**: implementar o modelo dimensional.

### Definindo o Modelo de Negócio
- **Análise Estratégica**
  - Identificar processos de negócios críticos
  - Compreender os processo
  - Priorizar e selecionar os processos
 
- **Criação do Modelo de Negócio**
  - Definição dos requerimentos de negócio
  - Determinar a granularidade
  - Determinar os metadados

- **Documentção dos Metadados**
  - Documentar o design do processo
  - Documentar registros de mudanças
  - Registrar melhorias ao longo do tempo

### Definindo o Modelo de Lógico
- **Modelo Entidade-Relacionamento**
- **Diagrama Entidade-Relacionamento**

### Definindo o Modelo de Dimensional
- Identificar a tabela FATO
- Identificar as tabelas DIMENSÕES
- Estabelecer links entre Fatos e Dimensões
- Modelar Dimensão Tempo

## Data Warehouse Schemas
- Terceira Forma Normal (3FN)
  ![3NF](link)
- Star Schema
  ![Star Schema](link)
- Snowflake Schema
  ![Snowflake Schema](link)
  

<h4 align="center"> &#128679; Em construção... &#128679; </h4>
