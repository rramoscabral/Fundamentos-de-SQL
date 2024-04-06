---
layout: default
title: Laboratório
nav_order: 14.7
parent: 'Pivoting'
---

# Exercício 14 – Pivoting e as subcláusulas de extensão da cláusula GROUP BY.
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório
A empresa AdvanceWorks requer uma análise de vendas com os dados que estão na tabela **Sales.SalesOrderHeader**.

<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:

* Criar consultas que utilizam os operadores PIVOT e UNPIVOT.
* Criar consultas que utilizam as subcláusulas GROUPING SETS, CUBE e ROLLUP da extensão da cláusula GROUP BY.


<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 40 minutos

<br>

## Tarefa 1 - Criar consultas com pivoting e as subcláusulas de extensão da cláusula GROUP BY  (40 minutos)

1. Com o operador **PIVOT** crie uma pesquisa que mostre o total devido anual por cliente desde o ano 2005 ao 2008 com os dados da tabela **Sales.SalesOrderHeader**. 

    Resultado final esperado

    | Cliente | 2005 | 2006 | 2007 | 2008 |
    | --- | --- | --- | --- | --- |
    | 14324	| NULL | NULL|| 2264.2536 | 3394.9247|
    | 22814	| NULL | NULL | 5.514 | NULL |
    | 11407	| NULL | NULL | 59.659 | NULL |
    | 28387	| NULL | NULL | NULL | 645.2869 |
    | 19897	| NULL | NULL | NULL | 659.6408 |
    | 15675 | NULL | 2699.9018 | 2682.9953 | 2580.1529 |
    | ...   | ...  | ... | ... | ... |


1. Utilizado a consulta do **PIVOT** execute o **UNPIVOT** ordene por **Cliente**.


1. Com operadores de agregação como o **SUM** é possível criar o mesmo resultado do operador **PIVOT** mas requer mais lógica.

    Experimente a seguinte consulta:

    ```sql
    SELECT 
        CustomerID,
        SUM(CASE WHEN Year(OrderDate) = 2005 THEN TotalDue ELSE 0 END) AS "2005",
        SUM(CASE WHEN Year(OrderDate) = 2006 THEN TotalDue ELSE 0 END) AS "2006",
        SUM(CASE WHEN Year(OrderDate) = 2007 THEN TotalDue ELSE 0 END) AS "2007",
        SUM(CASE WHEN Year(OrderDate) = 2008 THEN TotalDue ELSE 0 END) AS "2008"
    FROM Sales.SalesOrderHeader
    GROUP BY CustomerID;
    ```

1. Analise as vendas utilizando a tabela **Sales.SalesOrderHeader** com a subcláusula **GROUPING SETS**.

    Resultado esperado:

    | SalesPersonID | Year | TotalDue |
    | --- | --- | --- |
    | NULL | 2005 | 3609342.9456 |
    | 274 | 2005 | 32567.9155 |
    | 275 | 2005 | 846580.2377 |
    | ... | ... | ... |
    

1. Analise as vendas utilizando a tabela **Sales.SalesOrderHeader** com a subcláusula **CUBE** e verifique se o conjunto de resultados é semelhante ao **GROUPING SETS**.

    
    Resultado esperado:

    | SalesPersonID | Year | TotalDue |
    | --- | --- | --- |
    | NULL | 2005 | 3609342.9456 |
    | 274 | 2005 | 32567.9155 |
    | 275 | 2005 | 846580.2377 |
    | ... | ... | ... |



1. Analise o total de vendas utilizando a tabela **Sales.SalesOrderHeader** com a subcláusula **CUBE**.

    Resultado esperado:

    | SalesPersonID | Year | TotalDue |
    | --- | --- | --- |
    | NULL | 2005 | 3609342.9456 |
    | NULL | 2006 | 7216029.7246 |
    | NULL | 2007 | 10819121.9238 |
    | ... | ... | ... |



<br>