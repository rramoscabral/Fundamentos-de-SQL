---
layout: default
title: Operador CROSS APPLY
nav_order: 12.6
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador CROSS APPLY
{: .no_toc }


O operador `APPLY` têm duas variantes principais o `CROSS APPLY` e `OUTER APPLY`. 

O `CROSS APPLY` é utilizado quando se deseja devolver apenas as linhas que correspondem ao resultado da consulta da tabela referenciada. 

<br>

**Sintaxe básica**

```sql
FROM <Tabela_A> AS <alias>
CROSS APPLY 
    <Tabela_B> AS <alias>;
```

<br>

**Exemplo**

Consultar os cinco principais pedidos para cada cliente com base no valor a pagamento por cada cliente.

```sql
SELECT C.CustomerID, O.SalesOrderID, O.TotalDue
FROM Sales.Customer AS C
CROSS APPLY (
    SELECT TOP 5 SalesOrderID, TotalDue
    FROM Sales.SalesOrderHeader
    WHERE CustomerID = C.CustomerID
    ORDER BY TotalDue DESC
) AS O;

```

<br>

**CROSS APPLY ou OUTER APPLY**

A escolha entre o operador `CROSS APPLY` e `OUTER APPLY` depende do resultado desejado. 

* Se a intenção é obter todas as linhas da tabela referenciada, independentemente de haver correspondência, então `OUTER APPLY` é a escolha adequada. 
* Se o objetivo é restringir os resultados apenas às linhas que têm correspondência, então `CROSS APPLY` será mais apropriado.




<br>



