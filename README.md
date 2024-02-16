# Formação Engenharia de Dados

## Data Warehouses, Business Intelligence, Data Marts e OLTPs

### Business intelligence

Business intelligence (BI) refere-se a um conjunto de metodologias e recursos que permite às empresas acessar, analisar e desenvolver insights acionáveis a partir de dados para tomar decisões de negócios.

Ref: https://aws.amazon.com/pt/what-is/business-intelligence/

### OLTP

OLTP (Online Transaction Processing) é um banco de dados relacional que registra transações em tempo real em uma determinada operação organizacional. 

Ex: sistema de transações bancárias que registra todas as operações efetuadas em um banco, caixas de multibanco, reservas de viagens ou hotel on-line, Cartões de Crédito.

Ref: https://aws.amazon.com/pt/compare/the-difference-between-olap-and-oltp/

### Data Warehouse

O Data Warehouse (DW) é o ponto central de uma estrutura de BI. O DW é um banco de dados relacional usado para armazenar **informações consolidadas** relativas às atividades de uma organização.

Possibilita a análise de grandes volumes de dados, que são coletados a partir de sistemas transacionais OLTP.

O DW é organizado para dar suporte a tomada de decisões estratégicas da empresa.

Ref: https://aws.amazon.com/pt/what-is/data-warehouse/

### Data Marts

Um Data Mart é um Data Warehouse que atende às necessidades de uma equipe ou unidade de negócios específica, como finanças, marketing ou vendas.

Ele contém uma parte pequena e selecionada dos dados contidos no DW.

Ele fornece dados resumidos que as principais partes interessadas podem usar para tomar decisões informadas rapidamente.

Ref: https://aws.amazon.com/pt/what-is/data-mart/

