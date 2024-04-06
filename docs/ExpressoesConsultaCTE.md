---
layout: default
title: Expressões de Tabela ou Common Table Expressions (CTEs)
nav_order: 11.5
parent: 'Expressões de consulta'
---


# Expressões de Tabela ou Common Table Expressions (CTEs)
{: .no_toc }


A Expressão de tabela comum ou common table expression (CTEs) em inglês permite aos utilizadores criarem um conjunto de resultados temporário que é definido dentro do scope de execução de uma instrução `SELECT`, `INSERT`, `UPDATE`, `DELETE` ou `MERGE`.

Este conjunto de resultados permite simplificar as consultas complexas, pois permite dividir consultas complicadas em partes mais simples e reutilizáveis. 

A utilização dos CTEs permite melhorar a legibilidade e a manutenção das suas consultas SQL, além de possibilitar a execução de consultas que seriam complexas ou impossíveis de realizar de outra forma. 

<br>

**Sintaxe básica**

```sql

[ WITH <common_table_expression> [ ,...n ] ]

<common_table_expression>::=
    expression_name [ ( column_name [ ,...n ] ) ]
    AS
    ( CTE_query_definition )

```

* Uma CTE é iniciada com a cláusula `WITH`.
* A seguir por uma expressão de tabela comum que define o nome da `CTE` e o conjunto de colunas que ela irá conter. 
* A definição da CTE inclui uma instrução SELECT que produz o conjunto de resultados que a CTE irá representar. 

Para garantir a precisão e a eficiência das consultas, é importante seguir as diretrizes estabelecidas para a criação e utilização de CTEs, como garantir que o nome da expressão seja único dentro da cláusula `WITH` e que as colunas listadas correspondam ao conjunto de resultados da definição da consulta da CTE. 

<br>

**Características**

Uma característica distinta das CTEs é a sua capacidade de serem auto-referenciais, ou seja, podem referenciar a si mesmas, o que é essencial para a criação de consultas recursivas. 

<br>

**Exemplo**


Ao trabalhar com hierarquias ou dados sequenciais, as CTEs recursivas permitem percorrer os dados de forma iterativa. 

Para garantir a precisão e a eficiência das consultas, é importante seguir as diretrizes estabelecidas para a criação e utilização de CTEs, como garantir que o nome da expressão seja único dentro da cláusula **WITH** e que as colunas listadas correspondam ao conjunto de resultados da definição da consulta da CTE. 

    ```sql
    WITH CTE_SalesOrder_year AS
        (
        SELECT YEAR(orderdate) AS orderyear, CustomerID
        FROM Sales.SalesOrderHeader
        )
    SELECT orderyear, COUNT(DISTINCT CustomerID) AS customer_count
    FROM CTE_SalesOrder_year
    GROUP BY orderyear;
    ```


É importante compreender que uma CTE deve ser seguida por uma instrução `SELECT`, `INSERT`, `UPDATE` ou `DELETE` que referencie algumas ou todas as colunas da CTE. 

As CTEs também podem ser especificadas numa instrução `CREATE VIEW` como parte da instrução `SELECT` que define a vista. 

<br>

---

<br>

##  Documentação oficial da Microsoft

- [WITH common_table_expression (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/with-common-table-expression-transact-sql)

