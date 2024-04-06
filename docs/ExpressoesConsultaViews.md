---
layout: default
title: Visualizações ou Views
nav_order: 11.1
parent: 'Expressões de consulta'
---


# Visualizações ou Views
{: .no_toc }


Uma Visualizações ou Views em inglês é uma espécie de tabela virtual criada através de uma consulta SQL específica.

Uma view pode ser utilizada para análises de dados, previsões e simulações através consultas complexas, mas também melhora a segurança ao restringir o acesso a determinados dados. 

Ao utilizar uma view, está-se na realidade a executar uma consulta pré-definida, que apresenta os dados como se estivessem numa tabela real, sem que estes estejam fisicamente armazenados. 

<br>

**Vantagens**

Vantagens de uma View:
* São dinâmicas;
* Não ocupam espaço físico na base de dados;
* Evita a necessidade de reescrever consultas complexas repetidamente.
* Podem ser utilizadas para proporcionar uma camada de abstração, ocultando a complexidade das operações de base de dados e permitindo que os utilizadores se concentrem nos dados que necessitam.

<br>

## Criar uma view

Para criar uma view no T-SQL, utiliza-se o comando `CREATE VIEW`. 

**Sintaxe básica**

```sql
CREATE VIEW [esquema].[nome_da_view]
AS
SELECT coluna1, coluna2, .....
FROM [esquema].[tabela]

```

Para criar uma view o utilizador tem de ter a permissão **CREATE VIEW** na base de dados.

**Atenção** existem limitações para utilizar e/ou criar uma view.
- Uma View apenas pode ter um máximo de 1024 colunas.
- Uma View não é partilhada entre base de dados.
- Não é possível passar parâmetros para uma View.
- As Views não podem ser criadas em tabelas temporárias
- Não é possível usar uma cláusula `Order By` com Views sem especificar `FOR XML` ou `TOP`.
- Não é possível associar regras e padrões a Views.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [Views (Microsoft SQL Server)](https://learn.microsoft.com/en-us/sql/relational-databases/views/views)
- [CREATE VIEW (Transact-SQL)](https://learn.microsoft.com/pt-pt/sql/t-sql/statements/create-view-transact-sql?view=sql-server-ver16)
- [Create views (Microsoft SQL Server)](https://learn.microsoft.com/en-us/sql/relational-databases/views/create-views)

