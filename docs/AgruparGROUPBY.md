---
layout: default
title: Cláusula GROUP BY
nav_order: 9.1
parent: 'Agrupar dados'
---


# Cláusula GROUP BY
{: .no_toc }

O comando GROUP BY no T-SQL é utilizado para agrupar linhas que têm os mesmos valores em colunas especificadas, permitindo realizar operações de agregação, como a soma ou a média, sobre cada grupo de linhas. 

Este comando é essencial em consultas que visam resumir informações em grandes volumes de dados, facilitando a análise e a interpretação dos resultados. 

<br>

**Combinar GROUP BY**

As funções de agregação podem ser combinadas com a cláusula **GROUP BY**, que agrupa os resultados conforme os valores de uma ou mais colunas, permitindo assim uma análise mais detalhada dos dados.

Pode-se utilizar **GROUP BY** para agrupar vendas por região e depois aplicar a função **SUM()** para calcular o total de vendas por região.

<br>

**Sintaxe básica**

```sql
SELECT colunas
FROM [esquena].[tabela]
WHERE condição
GROUP BY agrupar para uma lista
ORDER BY ordenar por lista
```

Se quisermos saber o total de vendas por produto, podemos agrupar os dados pela coluna do produto e aplicar a função de soma na coluna do valor das vendas. 

É importante frisar que todas as colunas selecionadas na cláusula `SELECT` que não estão envolvidas em funções de agregação devem ser listadas na cláusula `GROUP BY`.

<br>

**Exemplo**

Esta consulta irá agrupar os dados pela data da venda e calcular a média do valor de venda para cada grupo. 

```sql

USE AdventureWorks;
GO

SELECT OrderDate as 'Data de Venda', AVG(SubTotal)
FROM Sales.SalesOrderHeader
GROUP BY OrderDate;

```

Outro exemplo em que o `GROUP BY` vai ser utilizado para agrupar `TerritoryID`.

```sql
USE AdventureWorks;
GO

SELECT TerritoryID
FROM Sales.Customer
-- 19820 linhas

SELECT TerritoryID, Count(TerritoryID) 
FROM Sales.Customer
GROUP BY TerritoryID

SELECT DISTINCT(TerritoryID)
FROM Sales.Customer
-- 10 linhas
```

<br>

---

<br>

##  Documentação oficial da Microsoft

- [SELECT - GROUP BY- Transact-SQL](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-group-by-transact-sql)
