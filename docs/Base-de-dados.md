---
layout: default
title: Base de dados
nav_order: 2
has_children: false
---

# Base de dados
{: .no_toc }

Just the Docs has some specific configuration parameters that can be defined in your Jekyll site's \_config.yml file.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


## Base de dados

Uma base de dados é um sistema informático que permite armazenar e organizar dados de um determinado tema ou domínio e gerir os mesmos. Simplificando é uma coleção de de dados que vai crescendo com a sua utilização e pode tronar-se complexo a sua gestão.

Um Data Database Management System (DBMS) em inglês ou Sistemas de Gestão de Bases de Dados (SGBD) também conhecido como Gestor de Bases de Dados é o software que gere uma ou mais base de dados e mantem os dados organizados, acessíveis e seguros.



## ANSI SQL (Structured Query Language)
O SQL padrão, também conhecido como ANSI SQL, é uma linguagem de consulta genérica utilizada para gerir e manipular dados em diferentes sistemas de gestão de bases de dados.




## Transact-SQL (T-SQL)

A sua origem remonta no final dos anos 80 com a parceria entre as duas empresas a [Microsoft](https://www.microsoft.com/pt-pt) e [Sybase](https://www.sap.com/portugal/products/acquired-brands/what-is-sybase.html).

O T-SQL expande o SQL padrão e foi criado para adicionar funcionalidades procedimentais, como variáveis locais, controlo de fluxo e funções de apoio para processamento de strings, datas e matemáticas, que não estavam presentes no SQL padrão. Esta linguagem é central para a utilização do Microsoft SQL Server, pois todas as aplicações que comunicam com uma instância do SQL Server fazem-no enviando instruções T-SQL para o servidor. 

O T-SQL é essencial para a criação de procedimentos armazenados, que são rotinas executáveis no lado do servidor e permitem a passagem de parâmetros, otimizando o desempenho e a segurança das bases de dados. A familiaridade com o T-SQL é, portanto, fundamental para qualquer profissional que trabalhe com bases de dados da Microsoft, sendo uma habilidade valiosa no mundo da análise de dados, engenharia de dados e administração de bases de dados.

Com o passar dos anos, o T-SQL se tornou uma parte integral do ecossistema de base de dados da Microsoft, sendo utilizado não apenas no SQL Server, mas também em outros produtos da empresa, como o Microsoft Azure SQL Database, que suporta a maioria dos recursos do T-SQL.


Em resumo, o Transact-SQL é uma linguagem de programação avançada que facilita a interação com bancos de dados relacionais, oferecendo recursos que vão além do SQL padrão. A sua origem está ligada à necessidade de uma linguagem mais poderosa para a gestão de base de dados da Microsoft, e hoje, é uma ferramenta indispensável para profissionais da área de dados que trabalham com produtos da Microsoft. 





## NoSQL (not only SQL)
O "not only SQL" ou "non-SQL" 


NoSQL, um termo que evoluiu de "non-SQL"(não sql) para "not only SQL"(não apenas SQL), representa uma abordagem alternativa às bases de dados tradicionais relacionais. Surgido em 1998, o conceito foi criado por Carlo Strozzi com a intenção de designar sistemas de armazenamento que não se limitam ao modelo relacional. As bases de dados NoSQL são conhecidas pela sua flexibilidade, permitindo uma modelagem de dados que se adapta melhor a necessidades específicas, como grandes volumes de dados não estruturados ou estruturados de maneira menos rígida que as tabelas tradicionais de SQL.

A popularidade do NoSQL cresceu significativamente no início do século XXI, impulsionada pelas exigências de empresas da Web 2.0, como Facebook, Google e Amazon, que necessitavam de sistemas capazes de armazenar e processar enormes quantidades de dados com rapidez e eficiência. Esta necessidade levou ao desenvolvimento de sistemas que priorizam a escalabilidade horizontal, ou seja, a capacidade de aumentar a capacidade de processamento através da adição de mais máquinas ao sistema, em vez de depender de um único servidor poderoso.

As bases de dados NoSQL são categorizadas conforme o tipo de modelo de dados que utilizam, como chave-valor, colunas largas, documentos ou grafos, cada um oferecendo vantagens específicas dependendo do uso. Por exemplo, bases de dados orientadas a documentos são ideais para armazenar dados semiestruturados como JSON, enquanto sistemas baseados em grafos são excelentes para representar e consultar relações complexas entre dados.

Um dos principais benefícios das bases de dados NoSQL é a consistência eventual, um modelo que permite atualizações rápidas e distribuídas, embora possa levar a leituras obsoletas em certos casos. Este compromisso entre consistência e disponibilidade é muitas vezes aceitável para aplicações que requerem alto desempenho e tolerância a falhas.

Apesar das suas vantagens, as bases de dados NoSQL também apresentam desafios, como a falta de uma linguagem de consulta padronizada, o que pode dificultar a migração de sistemas existentes e a integração com novas aplicações. Muitos sistemas NoSQL não oferecem transações ACID completas, o que é um requisito crítico para certas aplicações empresariais.

Em resumo, as bases de dados NoSQL oferecnuma solução poderosa e flexível para o armazenamento e a gestão de dados na era moderna, onde a quantidade e a variedade de dados continuam a crescer exponencialmente. São uma peça fundamental na infraestrutura de muitas aplicações web de grande escala e sistemas de processamento de dados em tempo real, permitindo que as organizações tirem proveito das oportunidades oferecidas pela big data e pela computação em nuvem. A introdução ao NoSQL numa formação de SQL é essencial para compreender a diversidade e a complementaridade das soluções de bases de dados disponíveis atualmente.



## Quais são as diferenças entre SQL e T-SQL. 
As principais diferenças entre T-SQL e SQL padrão residem nas extensões e funcionalidades específicas que o T-SQL oferece para o ambiente do Microsoft SQL Server. Enquanto o SQL padrão, também conhecido como ANSI SQL, é uma linguagem de consulta genérica utilizada para gerir e manipular dados em diferentes sistemas de gestão de bases de dados, o T-SQL inclui funcionalidades adicionais, como procedimentos armazenados, funções definidas pelo utilizador, triggers e comandos específicos para controlo de transações. Por exemplo, o T-SQL permite o uso de variáveis de tabela e tabelas temporárias, que são extremamente úteis para armazenar dados temporários durante o processamento de consultas complexas. 

O T-SQL suporta a utilização de blocos de código transacionais que permitem ao utilizador controlar as transações de forma mais granular com comandos como BEGIN TRANSACTION, COMMIT e ROLLBACK.

Outra diferença significativa é a sintaxe para a paginação de resultados. O SQL padrão utiliza a cláusula FETCH FIRST, enquanto o T-SQL utiliza a cláusula OFFSET-FETCH. 

O T-SQL tem a cláusula TOP, utilizada para limitar o número de linhas retornadas por uma consulta. No que diz respeito à manipulação de strings, o T-SQL oferece uma gama mais ampla de funções para a gestão de texto, como a função STRING_SPLIT, que facilita a divisão de uma string numa coluna baseada num delimitador específico.

Em termos de desempenho, o T-SQL pode oferecer vantagens devido à sua integração estreita com o SQL Server, permitindo otimizações específicas do sistema que podem não estar disponíveis em outros sistemas de gestão de bases de dados. Por fim, É importante frizar que, embora o T-SQL seja uma extensão do SQL padrão, ele segue a maioria dos princípios fundamentais do SQL, garantindo que os utilizadores com conhecimento em SQL padrão possam adaptar-se rapidamente ao T-SQL com um período de aprendizagem relativamente curto.


## Sistema de gestão de base de dados relacionais

Existem várias sistema de gestão de base de dados relacionais que podem ser locais, centralizadas ou em cloud.

- [Amazon Relational Database Service (RDS)](https://aws.amazon.com/pt/rds/) lançada em 2009, é uma coleção de serviços relacionais na cloud Amazon. 
- [Apache Derby](https://db.apache.org/derby/), lançado em 1997 mantido pela Apache Software Foundation.
- [Firebird](https://firebirdsql.org/), lançado em 2000 foi desenvolvido a partir do código-fonte do InterBase, mantido pela comunidade.
- [Ingres Database](https://www.actian.com/databases/ingres/), lançado em 1970 como um projeto de pesquisa na Universidade da Califórnia.É prioritário e mantido pela Actian Corporation
- [MariaDB](https://mariadb.org/) lançada em 2009, é um projeto independente com base do MySQL é mantido pela MariaDB Corporation Ab e pela comunidade de desenvolvedores.
- [Microsoft Access](https://www.microsoft.com/pt-pt/microsoft-365/access) lançado em 1992 não é centralizado e projetado para ser utilizado em computadores pessoais é mantido pela Microsoft.
- [Microsoft SQL Server](https://www.microsoft.com/pt-pt/sql-server/) lançado em 1989 mantido pela Microsoft tnuma versão gratuita com recursos limitados e várias versões comerciais. A versão 2016 terminará em Julho de 2026.
- [MySQL](https://www.mysql.com/) lançado em 1995 mantido pela Oracle Corporation tem licenciamnete gratuito para WEB e comercial para restantes áreas.
- [Oracle Database](https://www.oracle.com/database/) lançado em 1979 um dos sistemas mais utilzados e mantido pela Oracle Corporation.
- [PostgreSQL](https://www.postgresql.org/) lançado em 1996 mantido por uma comunidade de desenvolvedores e empresas.

## Sistema de gestão de base de dados não relacionais 

Existem várias sistema de gestão de base de dados não relacionais que podem ser locais, centralizadas ou em cloud.

- [Azure Cosmos DB]() lançado em 2017 é mantido pela Microsoft Azure.
- [Amazon DynamoDB]() lançado em 2017 é mantido pela Amazon Web Services.
- [Cassandra]() lançado em 2008 é mantido pela Apache Software Foundation.
- [Google Cloud Datastore]() lançado em 2008 é mantido pelo Google.
- [MongoDB]() lançado em 2007 é mantido pela MongoDB Inc. 
- [Redis]() lançado em 2009 é mantido pela Redis Labs.

>Nota: Este curso não está orientado na utilização de base de dados não relacionais.

<br>