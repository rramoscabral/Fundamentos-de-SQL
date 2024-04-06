---
layout: default
title: Subconsultas Correlacionadas
nav_order: 10.2
parent: 'Subconsultas'
---


# Subconsultas Correlacionadas ou Correlated Subqueries
{: .no_toc }


Subconsultas correlacionadas também conhecidas como Correlated Subqueries em inglês permite realizar consultas mais complexas e dinâmicas.

Estas subconsultas são utilizadas quando queremos referenciar uma coluna de uma subconsulta na consulta principal.

<br>

**Sintaxe básica**

```sql
SELECT coluna1, coluna2, ....
FROM tablela_A as a
WHERE column1 operator
    (SELECT coluna1, coluna2, ....
    FROM tablela_B
    WHERE expressão1 = a.expressão2);
```

<br>

**Exemplo**

Pode consultar todos os empregados que ganham acima da média de um departamento. 
    
* A subconsulta interna iria calcular o salário médio para cada departamento.
* A consulta externa seleciona os funcionários cujo salário individual é superior à média do departamento.


É importante frisar que a subconsulta é executada para cada linha da consulta externa, o que pode ter um impacto no desempenho se não for bem otimizado. 

As subconsultas correlacionadas podem ser utilizadas em várias cláusulas, como **`WHERE`**, **`FROM`** e **`SELECT`**, proporcionando uma grande flexibilidade na construção de consultas. 

No entanto, é importante compreender bem a lógica por trás das subconsultas correlacionadas para evitar erros lógicos e garantir que os resultados sejam precisos e eficientes.


<br>