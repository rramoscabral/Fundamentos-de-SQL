---
layout: default
title: Operador EXCEPT
nav_order: 12.3
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador EXCEPT
{: .no_toc }


O operador `EXCEPT` é utilizado para devolver todas as linhas de uma consulta que não existem em outra consulta, funcionando como uma subtração de conjuntos.

Se pretende saber quais os elementos que estão na tabela A mas não estão na tablea B, podemos usar o EXCEPT.

Este operador vai comparar as linhas devolvidas pelas  duas consultas e devolve apenas as que aparecem na primeira consulta.

<br>

**Sintaxe básica** 

```sql
{ <query_specification> | ( <query_expression> ) }   
{ EXCEPT }  
{ <query_specification> | ( <query_expression> ) }  
```

O operador EXCEPT vai comparar as linhas devolvidas pelas duas consultas e devolve apenas as que aparecem na primeira consulta.

<br>

**Exemplo**


Todos as identificações dos produtos da tabela `SalesOrderDetail` não existem existem na tabela `Product`

```sql
SELECT ProductID
FROM Sales.SalesOrderDetail
EXCEPT
SELECT ProductID
FROM Production.Product;
```

Este operador compara as linhas retornadas por duas consultas e devolve apenas aquelas que aparecem na primeira consulta mas não na segunda.


É importante frisar que o `EXCEPT` ignora duplicados e a comparação é feita linha a linha, o que significa que todas as colunas nas linhas correspondentes devem ser iguais para que sejam consideradas duplicaos.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [Set Operators - EXCEPT and INTERSECT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-except-and-intersect-transact-sql)
