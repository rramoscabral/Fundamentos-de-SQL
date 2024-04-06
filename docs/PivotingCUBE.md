---
layout: default
title: Subcláusula CUBE
nav_order: 14.4
parent: 'Pivoting'
---


# Subcláusula CUBE
{: .no_toc }

A Subcláusula **`CUBE`** é uma extensão da cláusula **`GROUP BY`** que permite criar subtotais em múltiplas dimensões. 

Esta cláusula é particularmente útil em consultas analíticas onde é necessário analisar dados agregados de várias  perspetivas. 

A cláusula **`CUBE`** cria subtotais para todas as combinações possíveis dos grupos especificados.

<br>

**Sintaxe básica**

A sintaxe básica para a utilizar o `GROUP BY CUBE` é a seguinte: 

```sql
SELECT <coluna1>, <coluna2>, <função_agregada(coluna3)> 
FROM <nome_tabela>
GROUP BY CUBE (<coluna1>, <coluna2>)
ORDER BY <coluna1>, <coluna2> 
```

<br>

**Exemplos**

Ao analisar as vendas de uma empresa, poderíamos visualizar o total de vendas por produto, por região, por períodos de tempo, ou qualquer combinação destes fatores.

<br>

**Cuidados com a cláusula CUBE**

É importante frisar que o uso da cláusula **`CUBE`** pode resultar num grande número de linhas no conjunto de resultados, devido a criar todas as combinações possíveis dos grupos especificados. Por este motivo é totalmente recomendado utilizar com bastante cuidado, especialmente em tabelas com um grande número de linhas ou quando se agrupa muitas colunas.

<br>

---

<br>

##  Documentação oficial da Microsoft


- [GROUP BY CUBE](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-group-by-transact-sql#group-by-cube--)


