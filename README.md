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
- **Entidades Fortes (Independentes):** são aquelas cuja existência independe de outras entidades, ou seja, por si só elas já possuem total sentido de existir. Em um sistema de vendas, a entidade `produto`, por exemplo, independe de quaisquer outras para existir.
- **Entidades Fracas (Dependentes):** as fracas são aquelas que dependem de outras entidades para existirem, pois individualmente elas não fazem sentido. Mantendo o mesmo exemplo, a entidade `venda` depende da entidade `produto`, pois uma venda sem itens não tem sentido.
- **Entidades Assossiativas:** esse tipo de entidade surge quando há a necessidade de associar uma entidade a um relacionamento existente. Na modelagem Entidade-Relacionamento não é possível que um relacionamento seja associado a uma entidade, então tornamos esse relacionamento uma entidade associativa, que a partir daí poderá se relacionar com outras entidades. Para melhor compreender esse conceito, tomemos como exemplo uma aplicação de vendas em que existem as entidades Produto e Venda, que se relacionam na forma muitos-para-muitos, uma vez que em uma venda pode haver vários produtos e um produto pode ser vendido várias vezes (no caso, unidades diferentes do mesmo produto). Em determinado momento, a empresa passou a entregar `brindes` para os clientes que comprassem um determinado produto. A entidade `Brinde`, então, está relacionada não apenas com a Venda, nem com o Produto, mas sim com o item da venda, ou seja, com o relacionamento entre as duas entidades citadas anteriormente. Como não podemos associar a entidade Brinde com um relacionamento, criamos então a entidade associativa "Item da Venda", que contém os atributos identificadores das entidades Venda e Produto, além de informações como quantidade e número de série, para casos específicos. A partir daí, podemos relacionar o `Brinde` com o Item da Venda, indicando que aquele prêmio foi dado ao cliente por comprar aquele produto especificamente.

## Atributos
Os atributos descrevem as propriedades das entidades. A entidade `pessoa` pode ter como atributo o `nome`, `data de nascimento`, `idade`, `endereço`.

Os atributos podem ser classificados quanto à sua **função** da seguinte forma:

- **Descritivos:** representam característica intrínsecas de uma entidade, tais como `nome` ou `cor`.
- **Nominativos:** além de serem também descritivos, estes têm a função de definir e identificar um objeto. `Nome`, `código`, `número` são exemplos de atributos nominativos.
- **Referenciais:** representam a ligação de uma entidade com outra em um relacionamento. Por exemplo, uma venda possui o `CPF` do cliente, que a relaciona com a entidade `cliente`.
  
Quanto à sua **estrutura**, podemos ainda classificá-los como:

- **Simples:** um único atributo define uma característica da entidade. Exemplos: `nome`, `peso`.
- **Compostos:** quando para definir uma informação da entidade, são usados vários atributos. Por exemplo, o `endereço` pode ser composto por `rua`, `número`, `bairro`, etc.

Quanto à **cardinalidade**, os atributos podem ser:
- **Monovalorado:** possui valor único para cada ocorrência de uma entidade. Exemplo: `nome` é um atributo monovalorado da entidade `Empregado`, pois um empregado pode ter apenas 1 nome.
- **Multivalorado:** pode possuir mais de um valor para cada ocorrência de uma entidade. Exemplo: `telefone` é um atributo multivalorado da entidade `Empregado`, pois um empregado pode ter vários números de telefone.

## Relacionamento
O relacionamento é uma associação entre entidades. Normalmente, são representados por **verbos**. Como, por exemplo, “uma **pessoa** `trabalha` para uma **empresa**”. No DER, os `relacionamentos` são representados através de um losango e linhas que ligam as `entidades` entidades. 

### Tipos de relacionamentos
- **Relacionamento 1:1 (um para um)**: cada uma das duas entidades envolvidas referenciam obrigatoriamente apenas uma unidade da outra. Por exemplo, em um banco de dados de currículos, cada usuário cadastrado pode possuir apenas um currículo na base, ao mesmo tempo em que cada currículo só pertence a um único usuário cadastrado.

- **Relacionamento 1:n ou 1:\* (um para muitos):** uma das entidades envolvidas pode referenciar várias unidades da outra, porém, do outro lado cada uma das várias unidades referenciadas só pode estar ligada uma unidade da outra entidade. Por exemplo, em um sistema de plano de saúde, um usuário pode ter vários dependentes, mas cada dependente só pode estar ligado a um usuário principal. Note que temos apenas duas entidades envolvidas: usuário e dependente. O que muda é a quantidade de unidades/exemplares envolvidas de cada lado.

- **Relacionamento n:n ou \*:\* (muitos para muitos):** neste tipo de relacionamento cada entidade, de ambos os lados, podem referenciar múltiplas unidades da outra. Por exemplo, em um sistema de biblioteca, um título pode ser escrito por vários autores, ao mesmo tempo em que um autor pode escrever vários títulos. Assim, um objeto do tipo autor pode referenciar múltiplos objetos do tipo título, e vice versa.

### Cardinalidade
Cardinalidade representa o **número de ocorrências** de uma entidade **A** com relação a uma outra entidade **B**.
##### Representação
- **(cardinalidade máxima, cardinalidade mínima)**
- Cardinalidade possíveis: `(1, 1)`; `(1, N)`; `(0, 1)`; `(0, N)`; `(N, N)`

Exemplo de relacionamento **obrigatório** (cardinalidade mínima 1) :
- **1 `cliente`** pode ter no **mínimo 1** e no **máximo N `contas`****
- **1 `conta`** pode ter no **mínimo 1** e no **máximo 1 `cliente`**

![cardinality](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/4513b708a647da7b7234c71727e966a737ee25f4/images/cardinality.png)

Exemplo de relacionamento **opcional** (cardinalidade mínima) :
- **1 `empregado`** pode gerenciar no **mínimo 0** e no **máximo 1 `departamento`**
- **1 `departamento`** pode ser gerenciado por no **mínimo 1** e no **máximo 1 `empregado`**

![cardinality-2](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/dd63d3308101a923f2fd8051415570d8712356b8/images/cardinality-2.png)

### Auto-Relacionamento
Auto-Relacionamento é um relacionamento entre ocorrências da mesma entidade

![auto-relationchip](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/c40b004f784137e3a110a16236e48fac6ee2902a/images/auto-relationchip.png)

Os relacionamentos são classificados ainda quanto a quantidade de entidades a se relacionarem. Os Auto-Relacionamentos são do tipo **unário**, já que há somente 1 entidade no relacionamento. Além de **unário**, existem ainda o rlacionamento binário (o mais comum) e o relaciomanento ternário:

![auto-relationchip](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/unario-binario-ternario.png?raw=true)

Ref.1: https://www.alura.com.br/artigos/mer-e-der-funcoes

Ref.2: https://www.devmedia.com.br/mer-e-der-modelagem-de-bancos-de-dados/14332


## Modelagem Dimensional

**Modelagem Dimensional** é uma técnica para construir modelos de negócio como **conjuntos de medidas** (FATOS) descritas através das diferentes **faces do negócio** (DIMENSÕES). 

A origem do termo *dimensional* está relacionada com a ideia de que os dados devem ser agrupados de maneira a formar um cubo, ou hipercubo, que seria a estrutura padrãao para visualizar os dados.

Um modelo dimensional é composto por uma tabela com uma chave composta, denominada tabela de fatos, e um conjunto de tabelas menores conhecidas como tabelas de dimensão, que possuem chaves simples (formadas por uma única coluna). Na verdade, a chave da tabela de fatos é uma combinação das chaves das tabelas de dimensão. Isto faz com que a representação gráfica do modelo dimensional assemelhe-se a uma estrela. Por este motivo, o modelo também é conhecido como modelo estrela (Kimball, 1998).

Benefícios da modelagem dimensional
- Suporte a análise multidimensional
- Cria um design que tem foco na performance
- Permitir otimização
- Design extensivo (mutável)
- Permite acesso de várias ferramentas de análise

### Dimensões

Uma dimensão é uma coleção de atributos textuais que são altamente correlacionados entre si. Os atributos (textuais ou não) que descrevem coisas são organizados dentro das dimensões. Em uma base de dados de varejo são comuns dimensões como produto, armazém, cliente, promoção e tempo.

Ref.: https://medium.com/@aasouzaconsult/modelagem-multidimensional-e65f02bbd60


### Slowly Changing Dimension

> Slowly Changing Dimensions (SCD), ou Dimensões que Mudam Lentamente em português, é um conceito utilizado em Business Intelligence (BI) para gerenciar mudanças em dados de dimensões ao longo do tempo.

> As dimensões representam aspectos de negócios que são importantes para a análise, como clientes, produtos, localizações e tempo. À medida que os dados de dimensão mudam ao longo do tempo, é necessário gerenciar essas mudanças para manter a integridade dos dados históricos e permitir análises precisas.

#### SCD tipo 1

Geralmente é chamado de método “**Sobrescrever**”, nesse método, quaisquer alterações nos dados de dimensão substituem o estado anterior dos dados com a mesma chave. Embora muito simples de implementar, este método sofre de uma grande desvantagem. Devido ao mecanismo de substituição, você não apenas perde o histórico anterior da dimensão, mas também o estado da tabela de fatos à qual ela é anexada. A imagem antes e depois da dimensão do cliente usando o método **SCD tipo 1** é mostrada abaixo.

![scd-tipo-1](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/scd-type-1.png?raw=true)


#### SCD tipo 2

Também conhecido como método “**Adicionar um novo registro**”. Nesse método, o registro de alteração é adicionado como um novo registro à tabela de dimensões e marcado como “**Atual**” ou “**Ativo**”. Além disso, a versão anterior do registro é marcada como “**Expired**” ou “**Inactive**”. As várias versões (atual e histórica) de um registro são ligadas usando uma chave substituta . No nível da tabela, o SCD Tipo 2 é implementado adicionando colunas de carimbo de data/hora `StartDate` e `EndDate` para cada linha na tabela de dimensões. Além disso, uma coluna de status é adicionada para marcar se o registro é atual ou expirado status. A imagem antes e depois da dimensão do cliente usando o método **SCD Tipo 2** é mostrada abaixo.

![scd-tipo-2](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/scd-type-2.png?raw=true)

#### SCD tipo 3

Também conhecido como método “**Adicionar um novo campo**”. Para cada alteração, a versão anterior e a versão atual são armazenadas como duas colunas distintas na mesma linha da tabela de dimensões. O **SCD Tipo 3** é relativamente mais fácil de implementar em comparação com o **SCD Tipo 2**, o histórico inclui apenas as versões atual e anterior.

![scd-tipo-3](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/scd-type-3.png?raw=true)

Abaixo, temos uma ilustração dos **SCDs tipo 1**, **tipo 2** e **tipo 3**:

![scd-all](https://github.com/Vinicius999/DSA-Formacao-Engenharia-de-Dados/blob/main/images/slowly-changing-dimentions-all.png?raw=true)



Ref.: https://medium.com/blog-do-zouza/manipulando-slowly-changing-dimensions-scd-usando-delta-tables-48e16bfb80ad

<h4 align="center"> &#128679; Next: ##Bloco006 - Modelagem Dimensional... &#128679; </h4>
<h4 align="center"> &#128679; Em construção... &#128679; </h4>

