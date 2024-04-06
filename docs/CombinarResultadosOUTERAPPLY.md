---
layout: default
title: Operador OUTER APPLY
nav_order: 12.7
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador OUTER APPLY
{: .no_toc }


O operador `APPLY` têm duas variantes principais o `CROSS APPLY` e `OUTER APPLY`. 

O `OUTER APPLY` devolve todas as linhas da tabela A, incluindo aquelas que não têm correspondência, apresentando NULL nas colunas da consulta do operador APPLY que não possuem valores correspondentes.

Este comportamento é idêntico ao `LEFT OUTER JOIN`, onde todas as linhas da tabela A são retornadas, independentemente de haver correspondência na tabela B.

<br>

**Sintaxe básica**

```sql
FROM <Tabela_A> AS <alias>
OUTER APPLY 
    <Tabela_B> AS <alias>;
```

<br>

**Exemplo**

Consultar todos os clientes que realizaram pedidos, todos os clientes que não realizaram nenhum pedido o valor será desconhecido (NULL).

```sql
SELECT C.CustomerID, O.SalesOrderID, O.TotalDue
FROM Sales.Customer AS C
OUTER APPLY (
    SELECT SalesOrderID, TotalDue
    FROM Sales.SalesOrderHeader
    WHERE CustomerID = C.CustomerID
) AS O;

```

<br>

**CROSS APPLY ou OUTER APPLY**

A escolha entre o operador `CROSS APPLY` e `OUTER APPLY` depende do resultado desejado. 

* Se a intenção é obter todas as linhas da tabela referenciada, independentemente de haver correspondência, então `OUTER APPLY` é a escolha adequada. 
* Se o objetivo é restringir os resultados apenas às linhas que têm correspondência, então `CROSS APPLY` será mais apropriado.



<br>



