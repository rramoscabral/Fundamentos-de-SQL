---
layout: default
title: CASE no SELECT
nav_order: 3.2
parent: 'Linguagem de Consulta de dados'
---


# CASE no SELECT
{: .no_toc }


O comando CASE é uma expressão condicional que fornece a capacidade de executar um conjunto de instruções entre várias condições. 

É semelhante a uma série de instruções **IF** em outras linguagens de programação. 

O CASE tem duas formas: 
	* A expressão CASE simples (*CASE*) compara uma expressão de entrada com um conjunto de expressões simples para determinar o resultado.
	* A expressão CASE pesquisada (*CASE WHEN*) avalia um conjunto de expressões booleanas para determinar o resultado.
	

Ambos os formatos suportam um argumento **ELSE** opcional, que é devolvido se nenhuma condição for verdadeira. 

Se o argumento **ELSE** for omitido e nenhuma condição for verdadeira, o CASE devolve **NULL**. Esta expressão pode ser utilizada em várias instruções ou cláusulas que permitam uma expressão válida, como **SELECT**, **UPDATE**, **DELETE** e **SET**, e em cláusulas como <select_list>, **IN**, **WHERE**, **ORDER BY** e **HAVING**.

**Sintaxe básica da expressão CASE simples** 

```sql
CASE expressao_entrada 
	WHEN expressao_comparacao 
	THEN expressao_resultado [ ...n ] 
	[ ELSE expressao_resultado_alternativo ] 
END 
```

<br>

**Sintaxe básica da expressão CASE pesquisada** 

O CASE WHEN está composto por três partes: 
1. a cláusula “CASE“.
1. a cláusula “WHEN”.
1. a cláusula “THEN“.

```sql
CASE WHEN expressao_booleana 
	THEN expressao_resultado [ ...n ] 
	[ ELSE expressao_resultado_alternativo ] 
END
```

É importante garantir que os tipos de dados da expressão de entrada e cada expressão de comparação sejam os mesmos ou que haja uma conversão implícita entre eles. Da mesma forma, os tipos de dados da expressão de resultado alternativo e qualquer expressão de resultado devem ser os mesmos ou permitir uma conversão implícita.

<br>

**Exemplo**

```sql
USE AdventureWorksLT;
GO

SELECT ProductNumber, Name, ListPrice,
	CASE Size
		WHEN 'S' THEN 'Small'
		WHEN 'M' THEN 'Medium'
		WHEN 'L' THEN 'Large' 
		WHEN 'XL' THEN 'Extra Large' 
		ELSE Size
	END AS Size
FROM SalesLT.Product
```

```sql
SELECT ProductNumber, Name, ProductCategoryID, 
	CASE ProductCategoryID
		WHEN 5 THEN 'Mountain Bikes'
		WHEN 7 THEN 'Touring Bikes'
	    WHEN 9 THEN 'SUPER Bikes'
		ELSE  CAST (ProductCategoryID as varchar(5))
	END AS Category
FROM SalesLT.Product
```

<br>

---

<br>

##  Documentação oficial da Microsoft

- [CASE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/case-transact-sql)
