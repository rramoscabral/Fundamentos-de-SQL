---
layout: default
title: Operador UNION ALL
nav_order: 12.2
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador UNION ALL
{: .no_toc }

O operador `UNION ALL` é um operador `SET` no T-SQL e permite combinar os resultados de duas ou mais consultas num único conjunto de resultados.

O `UNION ALL` mantém os valores duplicados numa consulta.

<br>

**Sintaxe básica** 

```sql
{ consulta }   
UNION ALL
{ consulta } 
```


Ao usar o UNION, cada consulta tem de ter o mesmo número de colunas no conjunto de resultados, com tipos de dados compatíveis e na mesma ordem.

Pode ordenar os resultados do `UNION ALL` utilizando a cláusula `ORDER BY`, que só pode ser colocada após a última consulta do `UNION ALL`.

<br>

**Exemplo**

```sql
SELECT ProductID, Name, ProductNumber 
FROM Production.Product
UNION ALL
SELECT ProductID, Name, ProductNumber 
FROM Production.Product 
WHERE Name LIKE 'Hex%'
```

O operador `UNION ALL` é frequentemente utilizado em situações onde é necessário consolidar dados de tabelas diferentes, mas relacionadas, proporcionando uma maneira eficiente de visualizar informações combinadas para análises mais complexas ou relatórios agregados.




<br>

---

<br>

##  Documentação oficial da Microsoft

- [Set Operators - UNION (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql)
