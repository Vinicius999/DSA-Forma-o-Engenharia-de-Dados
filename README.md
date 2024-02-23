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
- **Diagrama Entidade-Relacionamento**: abstração visual dos relacionamentos e atributos entre as entidades.

### Definindo o Modelo de Dimensional
- Identificar a tabela FATO
- Identificar as tabelas DIMENSÕES
- Estabelecer links entre Fatos e Dimensões
- Modelar Dimensão Tempo

#### Data Warehouse Schemas: 3FN, Star Schema, Snowflake Schema
- Terceira Forma Normal (3FN)
  
  ![3NF](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/3NF.png)
  
- Star Schema
  
  ![Star Schema](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/star-schema.png)
  
- Snowflake Schema
  
  ![Snowflake Schema](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/snowflake-schema.png)

#### Tabelas FATO e DIMENSÃO
##### Tabela FATO
- Contém métricas numéricas do negócio
- Tabela com maior volume de dados
- Cresce rapidamente
- Pode conter dadso base, derivados e sumarizados
- São relacionadas as tabelas de DIMENSÃO com chaves estrangeeiras que referenciam as chaves primárias nas tabelas DIMENSÃO.

##### Tabelas DIMENSÃO
- Contém informação textual que representa atributos de negócio
- Contém dados relativamente estáticos
- São relacionadas com a Tabela Fato

### Definindo o Modelo Físico
- Traduz do design dimensional para o modelo físico
- Atualiza os metadados
- Determina a arquitetura de hardware
- Define estratédias de armazenamento
- Sizing
- Particionamento
- Indexação
- Segurança

## Características de um bom modelo de dados para DW:
- Reflete a visão que o usuário tem do negócio e suas medidas;
- É simples;
- É facilmente compreensível e memorizável para o usuário;
- Geram esquemas de bancos de dados que permitem bom desempenho para consultas com grandes volume de dados.

## Definição e Objetivo do Modelo Entidade-Relacionamento
O **MER** (Modelo Entidade Relacionamento) é utilizado para descrever os objetos do mundo real através de entidades, com suas propriedades que são os atributos e os seus relacionamentos.

O **DER** (Diagrama Entidade-Relacionamento) é utilizado para representar em forma gráfica o que foi descrito no MER (Modelo Entidade Relacionamento).

Ref.: https://www.alura.com.br/artigos/mer-e-der-funcoes

## Entidades
É um conjunto de **objetos do mundo real** sobre os quais se deseja manter informações no banco de dados, onde cada objeto é distinguível de outros objetos. Uma entidade pode representar **objetos concretos** (uma pessoa, por exemplo) e **objetos abstratos** (um departamento). No **DER**, cada entidade é representada através de um retângulo.

Como exemplo, em um **Sistema Bancário**, podemos ter as seguintes Entidades:
- Cliente
- Conta Corrente
- Conta Poupança
- Agência

Já em um **Sistema de Controle de Produção de Indústria**, temos:
- Produto
- Empregado
- Departamento
- Estoque

### Tipos de Entidades
- **Entidades Fortes (Independentes):** são aquelas cuja existência independe de outras entidades, ou seja, por si só elas já possuem total sentido de existir. Em um sistema de vendas, a entidade **produto**, por exemplo, independe de quaisquer outras para existir.
- **Entidades Fracas (Dependentes):** as fracas são aquelas que dependem de outras entidades para existirem, pois individualmente elas não fazem sentido. Mantendo o mesmo exemplo, a entidade **venda** depende da entidade **produto**, pois uma venda sem itens não tem sentido.
- **Entidades Assossiativas:** esse tipo de entidade surge quando há a necessidade de associar uma entidade a um relacionamento existente. Na modelagem Entidade-Relacionamento não é possível que um relacionamento seja associado a uma entidade, então tornamos esse relacionamento uma entidade associativa, que a partir daí poderá se relacionar com outras entidades. Para melhor compreender esse conceito, tomemos como exemplo uma aplicação de vendas em que existem as entidades Produto e Venda, que se relacionam na forma muitos-para-muitos, uma vez que em uma venda pode haver vários produtos e um produto pode ser vendido várias vezes (no caso, unidades diferentes do mesmo produto). Em determinado momento, a empresa passou a entregar **brindes** para os clientes que comprassem um determinado produto. A entidade **Brinde**, então, está relacionada não apenas com a Venda, nem com o Produto, mas sim com o item da venda, ou seja, com o relacionamento entre as duas entidades citadas anteriormente. Como não podemos associar a entidade Brinde com um relacionamento, criamos então a entidade associativa "Item da Venda", que contém os atributos identificadores das entidades Venda e Produto, além de informações como quantidade e número de série, para casos específicos. A partir daí, podemos relacionar o **Brinde** com o Item da Venda, indicando que aquele prêmio foi dado ao cliente por comprar aquele produto especificamente.




<h4 align="center"> &#128679; Next: ##Bloco005 - Tipos de Entidade ... &#128679; </h4>
<h4 align="center"> &#128679; Em construção... &#128679; </h4>
