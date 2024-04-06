---
layout: default
title: Subcláusula ROLLUP
nav_order: 14.5
parent: 'Pivoting'
---


# Subcláusula ROLLUP
{: .no_toc }


A subcláusula **`ROLLUP`** é uma extensão da cláusula **`GROUP BY`** que permite permite a criação de conjuntos de agrupamentos múltiplos, facilitando a criação de subtotais e o total geral em consultas. 

O `ROLLUP`asume uma hierarquia entre as colunas de entrada, o que significa que, se as colunas forem (c1, c2), então a hierarquia será c1 > c2. 

Com o `ROLLUP` é possível criar todos os conjuntos de agrupamentos lógicos considerando essa hierarquia. 

Por exemplo, a sintaxe ROLLUP(c1, c2) cria três conjuntos de agrupamentos: (c1, c2), (c1) e (). 

<br>

**Sintaxe básica**

A sintaxe básica para a utilizar o `GROUP BY ROLLUP` é a seguinte: 

```sql
SELECT <coluna1>, <coluna2>, <função_agregada(coluna3)> 
FROM <nome_tabela>
GROUP BY ROLLUP (<coluna1>, <coluna2>)
ORDER BY <coluna1>, <coluna2> 
```


<br>

**Exemplo**

É comum usar o `ROLLUP` para relatórios que necessitam de subtotais e totais.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [GROUP BY ROLLUP](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-group-by-transact-sql#group-by-rollup)

