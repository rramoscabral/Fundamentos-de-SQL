---
layout: default
title: Subconsultas
nav_order: 10
has_children: true
---


# Subconsultas
{: .no_toc }


Subconsultas ou Subqueries permite realizar consultas dentro de outras consultas. Este conceito é fundamental para criar consultas complexas e eficientes em bases de dados SQL Server. 

Uma subconsulta é basicamente uma instrução `SELECT` inserida dentro de outra instrução SQL, seja ela `SELECT`, `INSERT`, `UPDATE` ou `DELETE`. `

A utilização de subconsultas é particularmente útil quando se deseja filtrar resultados com base em valores que são obtidos de outra consulta. 

<br>

**Sintaxe básica**


```sql
SELECT ccoluna1, coluna2  
FROM   [esquema].[tabela] 
WHERE  nome_coluna OPERADOR [ANY | ALL]
   (SELECT ccoluna1, coluna2 
   FROM [esquema].[tabela] 
   [WHERE]) 
```

```sql
WHERE expressão operador_comparaçãor [ANY | ALL] (subconsulta)
```


<br>

**Exemplo**

Selecionar todos os produtos que têm um preço superior à média dos preços dos produtos. 
Neste caso, uma subconsulta seria usada para calcular a média dos preços e depois essa média seria usada na consulta principal para filtrar os produtos desejados.


```sql
SELECT *
FROM Production.Product
WHERE ListPrice > (SELECT AVG(ListPrice) FROM Production.Product);
```


* Na cláusula `FROM`, uma subconsulta pode ser usada para definir uma tabela temporária sobre a qual a consulta externa irá operar. 

* Na cláusula `SELECT`, as subconsultas podem ser utilizadas para fornecer valores para as colunas da consulta principal.


## Classificação de subconsultas

As subconsultas podem ser classificadas em diferentes tipos, como subconsultas indepenentes ou não correlacionadas e correlacionadas. 

* As **subconsultas indepenentes ou não correlacionadas** são independentes e podem ser executadas sozinhas, sem a necessidade de referência à consulta externa.
* As **subconsultas correlacionadas** são aquelas em que a subconsulta **depende da consulta externa** para obter os seus valores. 



É importante frisar que as subconsultas correlacionadas podem ser menos eficientes, pois necessitam ser reavaliadas para cada linha processada pela consulta externa.

Além disso, as subconsultas podem ser utilizadas em diferentes partes de uma instrução SQL. Podem aparecer nas cláusulas `WHERE`, `HAVING`, `FROM` ou `SELECT`. Quando utilizadas na cláusula `WHERE` ou `HAVING`, as subconsultas funcionam como filtros que definem condições para a seleção de linhas. 



## Cuidados com as subsconsultas

É crucial ter cuidado ao utilizar subconsultas, pois elas podem aumentar a complexidade da consulta e afetar o desempenho. 

Em alguns casos, é possível substituir uma subconsulta por um `JOIN`, o que pode simplificar a consulta e melhorar o desempenho. 

Contudo, há situações em que as subconsultas são a única maneira de expressar certas lógicas de consulta.



<br>

---

<br>

##  Documentação oficial da Microsoft

- [Subqueries](https://learn.microsoft.com/en-us/sql/relational-databases/performance/subqueries)

