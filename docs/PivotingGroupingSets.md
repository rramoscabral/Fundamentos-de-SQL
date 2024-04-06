---
layout: default
title: Subcláusula Grouping Sets
nav_order: 14.3
parent: 'Pivoting'
---


# Subcláusula Grouping Sets
{: .no_toc }


A subcláusula **`Grouping Sets**` é uma extensão da cláusula **`GROUP BY`** que permite realizar consultas agregadas complexas com múltiplos níveis de agrupamento numa única instrução.

É possível especificar um conjunto de colunas para serem agrupadas como um único grupo, permitindo que sejam efetuadas agregações que seriam complexas ou impossíveis de realizar com um simples `GROUP BY`.

Esta funcionalidade é particularmente útil quando se necessita de sumarizar dados em várias dimensões, oferecendo uma alternativa mais flexível e eficiente em comparação com as cláusulas `ROLLUP` e `CUBE` tradicionais.

<br>

**Sintaxe básica**

A sintaxe básica para a utilizar a `GROUP BY Grouping Sets` é a seguinte: 

```sql
SELECT <coluna1>, <coluna2>, <função_agregada(coluna3)> 
FROM <nome_tabela>
GROUP BY GROUPING SETS ( 
	(<coluna1>, <coluna2>), (<coluna1>), (<coluna2>), ()
) 
```
Esta consulta cria quatro conjuntos de agrupamento:

1. (coluna1, coluna2);
1. (coluna1);
1. (coluna2);
1. () é um conjunto vazio que representa a linha total geral.

<br>

**Exemplo**

Existem vários exemplos que são possíveis de realizar com a subcláusula `Grouping Sets`. Podemos calcular a soma das quantidades de produtos por armazém ou por produto sem necessidade de cruzar estas duas dimensões.

<br>

**Utilização do Grouping Sets**

A utilização dos `Grouping Sets` permite um controlo preciso sobre quais totais parciais são calculados, evitando assim o processamento desnecessário de dados e melhorando o desempenho das consultas. 

O custo de execução da consulta é proporcional à quantidade de subtotais solicitados, o que significa que o motor do SQL Server é suficientemente inteligente para calcular apenas o que é necessário.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [GROUP BY GROUPING SETS](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-group-by-transact-sql#group-by-grouping-sets--)

