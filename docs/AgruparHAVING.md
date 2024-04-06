---
layout: default
title: Cláusula HAVING
nav_order: 9.2
parent: 'Agrupar dados'
---


# Cláusula HAVING

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Cláusula HAVING

A cláusula **HAVING** funciona como um **WHERE** após o agrupamento, permitindo filtrar grupos baseados em condições de agregação. 

<br>

**Sintaxe básica**

É aplicada depois de os dados serem agrupados, ao contrário da cláusula **WHERE**, que filtra as linhas antes da operação de agrupamento. 

```sql
SELECT colunas
FROM [esquena].[tabela]
WHERE condição
GROUP BY agrupar para uma lista
HAVING opera em grupos
ORDER BY ordenar por lista
```

Como pode vereficar o **GROUP BY** é uma ferramenta poderosa para transformar dados brutos em informações estruturadas e úteis.

<br>

**Exemplo**

Consultar apenas os vendedores com um total de vendas superior a 1000.

```sql
USE AdventureWorks
GO

Select Person.FirstName AS Vendedor, SUM(SalesOrderHeader.SubTotal) AS 'Valor Vendas'
FROM Sales.SalesOrderHeader
INNER JOIN Person.Person
ON SalesOrderHeader.SalesPersonID = Person.BusinessEntityID
GROUP BY Person.FirstName
HAVING  SUM(SalesOrderHeader.SubTotal) > 1000
```

<br>

---

<br>

##  Documentação oficial da Microsoft

- [SELECT - HAVING (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-having-transact-sql)
