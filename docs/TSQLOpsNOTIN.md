---
layout: default
title: NOT IN
parent: 'T-SQL operadores'
grand_parent: 'T-SQL'
---


## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## NOT IN

O operador `NOT IN` no Transact-SQL (T-SQL) é utilizado para filtrar os resultados de uma consulta, excluindo os valores que estão contidos numa lista especificada. 

Por exemplo, se quisermos selecionar todos os empregados que não estão em determinados departamentos, podemos usar `NOT IN` para excluir esses departamentos da nossa consulta.

**Sintaxe básica**

```sql
SELECT * FROM tabela 
WHERE coluna NOT IN (valor1, valor2, ...);
```

É importante frisar que o **NOT IN** pode ser particularmente ineficiente com listas grandes ou subconsultas, pois cada valor na lista é avaliado individualmente. Se houver algum valor **NULL** na lista, o resultado da consulta será também **NULL**, o que pode não ser o resultado esperado. 

Para evitar problemas de desempenho e lógica, muitas vezes é preferível utilizar **NOT EXISTS** ou uma junção **LEFT JOIN** com uma cláusula **WHERE** que verifica por valores **NULL**. Estas alternativas podem proporcionar um melhor desempenho e são mais previsíveis no tratamento de valores **NULL**. 

É muito importante testar e otimizar as consultas para cada caso específico, garantindo assim a eficiência e a precisão dos resultados obtidos.

<br>

**Exemplo**

```sql
Select  x.productid, x.orderdate
FROM (
	SELECT DISTINCT d.productid, orderdate
	FROM sales.OrderDetails AS d
	LEFT JOIN sales.Orders AS o ON o.orderid = d.orderid
	WHERE DATEDIFF(week, '2007-01-01',orderdate) BETWEEN 0 AND 10
) x

WHERE x.productid NOT IN 
(
		SELECT DISTINCT d.productid
		FROM Sales.Orders AS o
		INNER JOIN Sales.OrderDetails AS d ON d.orderid = o.orderid
		WHERE DATEPART(week, orderdate) <= 10 AND YEAR(orderdate) = 2007
)
```

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Operators (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/operators-transact-sql)


