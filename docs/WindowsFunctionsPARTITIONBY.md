---
layout: default
title: Comando PARTITION BY 
nav_order: 13.2
parent: 'Funções de Janela ou Windows Functions'
---


# Comando PARTITION BY 
{: .no_toc }


O comando `PARTITION BY` é utilizado para dividir uma tabela em partições, permitindo que operações e consultas sejam realizadas de forma mais eficiente em conjuntos de dados específicos. 

Este comando é particularmente útil em bases de dados grandes, onde a gestão e a performance podem ser melhoradas através da divisão de dados em segmentos mais pequenos e maleáveis. 

**Sintaxe básica**

A sintaxe básica do comando `OVER` é a seguinte:

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

Calcular a soma acumulativa das vendas para cada produto.

```sql
SELECT ProductID, OrderQty, SUM(OrderQty) 
OVER (PARTITION BY ProductID ORDER BY SalesOrderID) as CumulativeSum
FROM Sales.SalesOrderDetail;
```

Ao utilizar `PARTITION BY RANGE`, pode-se particionar uma tabela por intervalos, criando partições que contêm algo dentro de certos intervalos. 

Calcular a soma acumulada de vendas para cada produto, mas apenas para pedidos do mesmo dia

```sql
SELECT D.SalesOrderID, H.OrderDate, D.OrderQty,
SUM(D.OrderQty) OVER(PARTITION BY D.ProductID, CAST(H.OrderDate AS DATE) ORDER BY D.SalesOrderID
                   RANGE BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) as CumulativeSum
FROM Sales.SalesOrderDetail AS D
JOIN Sales.SalesOrderHeader AS H ON D.SalesOrderID = H.SalesOrderID;
```

* Cada pedido contém o `SalesOrderID`, a `OrderDate`, e `OrderQty`.
* A soma acumulada do `OrderQty` e fectuada para cada `ProductID` e `OrderDate`.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [SELECT - OVER Clause (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-over-clause-transact-sql)



