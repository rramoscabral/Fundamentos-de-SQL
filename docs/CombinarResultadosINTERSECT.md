---
layout: default
title: Operador INTERSECT
nav_order: 12.4
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador INTERSECT
{: .no_toc }

O operador `INTERSECT` é utilizado para devolvver um conjunto de registos que são comuns a duas ou mais consultas. 

Funciona como uma interseção matemática entre conjuntos, onde apenas os elementos que estão presentes em todos os conjuntos são incluídos no resultado final.

O operador `INTERSECT` pode ser particularmente útil quando se deseja encontrar um conjunto de dados que seja estritamente partilhado entre diferentes tabelas ou consultas. 

<br>

**Sintaxe básica** 

```sql
{ <query_specification> | ( <query_expression> ) }   
{ INTERSECT }  
{ <query_specification> | ( <query_expression> ) }  

```

<br>

**Exemplo**

Todos as identificações dos produtos da tabela `SalesOrderDetail` também existem na tabela `Product`

```sql
SELECT ProductID
FROM Sales.SalesOrderDetail
INTERSECT
SELECT ProductID
FROM Production.Product;
```

Outro exemplo era encontrar clientes que fizeram compras tanto em janeiro quanto em fevereiro e obter exatamente esse subconjunto de clientes.


<br>

**Trabalhar corretamente com INTERSECT**

É importante frisar que:
*  As consultas `SELECT` envolvidas devem devolver o mesmo número de colunas e os tipos de dados correspondentes devem ser compatíveis:
* A ordem das colunas deve ser a mesma nas consultas que estão sendo intersectadas. O resultado da interseção é um conjunto de registos sem duplicados, mesmo que as tabelas originais contenham registos duplicados.

O uso do operador INTERSECT deve ser feito com cuidado, pois pode ter um impacto significativo no desempenho da consulta, especialmente se as tabelas envolvidas forem grandes ou se as consultas não forem otimizadas.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [Set Operators - EXCEPT and INTERSECT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-except-and-intersect-transact-sql)

