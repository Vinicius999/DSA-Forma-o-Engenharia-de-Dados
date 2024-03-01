Design e Implementação de Data Warehouses
# Lab 01 - Construindo um Diagrama ER com Ferramenta Case


Você foi contratado como consultor e em seu primeiro projeto você deve
criar um modelo lógico de um novo cliente da empresa. O cliente XPZ Corporation
possui processos manuais, mas pretende começar a usar sistemas de Business
Intelligence e para isso, gostaria de implementar um sistema de informação para
o departamento de RH.

O Analista de Negócios visitou o cliente, conduziu uma série de entrevistas
com stakeholders, revisou os processos da empresa, consultou algumas planilhas
e gerou uma descrição de alto nível que pode ser considerada como uma etapa
inicial da modelagem de negócio. O resultado deste trabalho você encontra
abaixo e será sua função construir um Diagrama Entidade-Relacionamento que
melhor represente o cenário.


## Modelagem de Negócio

A empresa XPZ Corporation é uma empresa que oferece serviços de
Outsourcing e vem crescendo consideravelmente em todo Brasil. A empresa
contrata seus funcionários, registra nos respectivos departamentos de acordo
com suas especialidades (desenvolvimento, banco de dados, infraestrutura e
análise de dados) e então aloca o funcionário em projetos. Alguns funcionários
trabalham remotamente e outros são alocados fisicamente em clientes da
empresa. Funcionários com perfil generalista podem trabalhar em mais de um
projeto simultaneamente e quando isso ocorre, o custo do funcionário é alocado
de acordo com o percentual trabalhado em cada projeto.

Todos os funcionários passam por uma avaliação anual, que define as
promoções ou mesmo desligamento da empresa, caso o funcionário tenha
avaliações ruins por dois anos consecutivos. Cada funcionário da empresa possui
um supervisor responsável pelas avaliações anuais, por atribuir tarefas e ajudar
em caso de dúvidas.

Cada departamento possui um gerente responsável pela organização dos
projetos naquele departamento. Cada departamento controla diversos projetos.

Todos os empregados são contratados e todas as informações são
registradas em planilhas Excel. Como a empresa fornece plano de saúde aos
funcionários e extensivo aos familiares em primeiro grau, os dados de
dependentes também são registrados.

Códigos de identificação únicos são usados em todos os registros e datas
são usadas no registro de empregados, gerentes e supervisores. Como os projetos
ocorrem em clientes em todo Brasil, a localização de cada projeto também é
registrada. Cada funcionário tem apenas um supervisor e cada departamento tem
apenas um gerente.

A empresa pretende implementar um sistema de informação que no futuro
permita extrair relatórios sobre o funcionamento dos departamentos, como
funcionários alocados por projeto e supervisores das equipes de alta
performance.

Seu trabalho agora é criar um Diagrama Entidade-Relacionamento que
represente o modelo de negócio acima.