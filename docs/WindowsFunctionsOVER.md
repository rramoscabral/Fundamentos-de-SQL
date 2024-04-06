---
layout: default
title: Cláusula OVER
nav_order: 13.1
parent: 'Funções de Janela ou Windows Functions'
---


# Cláusula OVER
{: .no_toc }


A cláusula `OVER` permite a realização de cálculos complexos sobre um conjunto de linhas de dados. 

Esta cláusula define uma janela ou conjunto de linhas dentro do resultado de uma consulta, sobre o qual as funções de janela podem operar. 

<br>

**Sintaxe básica**

A sintaxe básica da cláusula `OVER` é a seguinte:

```sql
OVER (
    [PARTITION BY coluna]
    [ORDER BY coluna [ASC|DESC]]
    [ROWS|RANGE entre]
)
```

* A cláusula `PARTITION BY` é opcional e serve para dividir o conjunto de resultados em partições distintas, baseando-se nos valores de uma coluna especificada. 
* A cláusula `ORDER BY` também é opcional e determina a ordem das linhas dentro de cada partição. 
* As cláusulas `ROWS` e `RANGE` definem o conjunto de linhas a ser considerado antes e depois da linha atual para os cálculos da função de janela.

<br>

**Exemplo**

Pode-se utilizar `OVER` para calcular totais acumulados, médias móveis, ou para determinar a classificação de elementos dentro de uma partição específica do conjunto de dados.

Um exemplo prático de utilização da cláusula `OVER` seria calcular a soma acumulativa das vendas para cada produto.

```sql
SELECT ProductID, OrderQty, SUM(OrderQty) 
OVER (PARTITION BY ProductID ORDER BY SalesOrderID) as CumulativeSum
FROM Sales.SalesOrderDetail;
```

A cláusula `OVER` pode ser utilizada com várias funções de janela, como `ROW_NUMBER`, `RANK`, `DENSE_RANK`, `NTILE`, `SUM`, `AVG`, `MIN`, `MAX`, entre outras.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [SELECT - OVER Clause (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-over-clause-transact-sql)


