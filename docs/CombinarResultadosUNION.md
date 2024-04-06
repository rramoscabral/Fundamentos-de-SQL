---
layout: default
title: Operador UNION
nav_order: 12.1
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador UNION
{: .no_toc }

O operador `UNION` é um operador `SET` no T-SQL e permite combinar os resultados de duas ou mais consultas num único conjunto de resultados, que inclui todas as linhas que pertencem a qualquer uma das consultas originais. Ou seja não mostra valores duplicados. 

O `UNION` remove valores duplicados numa consulta, a menos que seja especificado `UNION ALL`, que mantém todas os valores duplicados.

<br>

**Sintaxe básica** 

```sql
{ consulta }   
UNION  
{ consulta } 
```

Ao usar o UNION, cada consulta tem de ter o mesmo número de colunas no conjunto de resultados, com tipos de dados compatíveis e na mesma ordem.

Pode ordenar os resultados do `UNION` utilizando a cláusula `ORDER BY`, que só pode ser colocada após a última consulta do `UNION`.

<br>

**Exemplo**

```sql
SELECT ProductID, Name, ProductNumber 
FROM Production.Product
UNION
SELECT ProductID, Name, ProductNumber FROM
Production.Product WHERE ProductNumber LIKE 'Hex%'
```

O operador `UNION` é frequentemente utilizado em situações onde é necessário consolidar dados de tabelas diferentes, mas relacionadas, proporcionando uma maneira eficiente de visualizar informações combinadas para análises mais complexas ou relatórios agregados.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [Set Operators - UNION (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql)

