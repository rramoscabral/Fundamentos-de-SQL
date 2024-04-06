---
layout: default
title: Função GROUPING_ID
nav_order: 14.6
parent: 'Pivoting'
---


# Função GROUPING_ID
{: .no_toc }


A função **`GROUPING_ID`** permite identificar os níveis de agrupamento em consultas que utilizam a cláusula **`GROUP BY`**.

Esta função devolve um número inteiro que representa um bitmap.

Um bitmap é vetor de bits que representa uma estrutura de dados interna com o objetivo de otimizar consultas. Cada bit representa a presença ou ausência de um valor específico.

No `GROUP BY` cada bit corresponde a uma coluna na lista `GROUP BY`. Se um bit estiver definido como 1 significa que a coluna correspondente não é uma coluna de agrupamento.

<br>

**Sintaxe básica**

A sintaxe básica para a utilizar o `GROUPING_ID` é a seguinte: 

```sql
GROUPING_ID ( <expressão_coluna>[ ,...n ] )
```

<br>

**Exemplo**

Se efectuar um conjunto de agrupamento com a lista do `GROUP BY`com a seguinte definição `(SalesPersonID, YEAR(OrderDate)), (SalesPersonID), (YEAR(OrderDate)), ()` vai obter quatro grupos de agrupamentos.

 * O grupo 0 em binário 00 representa 0: conjunto de agrupamento SalesPersonID e Year (binário 00).
 * O grupo 1 em binário 10 representa conjunto de agrupamento que apenas inclui o Year.
* O grupo 2 em binário 11 representa conjunto de agrupamento que apenas inclui o SalesPersonID.
* O grupo 3 em binário 010 representa a linha total geral.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [GROUPING_ID (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/grouping-id-transact-sql)

