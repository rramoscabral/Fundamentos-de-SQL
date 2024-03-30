---
layout: default
title: Funções integradas no T-SQL
nav_order: 8
has_children: true
---


# Funções integradas no T-SQL
{: .no_toc }

As funções integradas no T-SQL são essenciais para a manipulação e análise de dados em bases de dados SQL Server. 
Estas funções podem ser categorizadas em diferentes tipos, como:
* funções escalares, que retornam um único valor; 
* funções de agregação, que operam sobre um conjunto de valores e retornam um único valor resumido; 
* funções de classificação e conjunto de linhas, que operam sobre um conjunto de linhas e retornam um conjunto de linhas. 

É importante notar que o uso adequado destas funções pode significativamente otimizar as consultas e o desempenho da base de dados. 

Por exemplo, funções escalares como **GETDATE()** ou **CONVERT()** são frequentemente utilizadas para manipular tipos de dados de data e hora ou converter um tipo de dado em outro. Já as funções de agregação como **SUM()**, **AVG()**, **COUNT()**, **MIN()** e **MAX()** são indispensáveis em consultas que necessitam resumir grandes volumes de dados. 

O T-SQL permite a criação de funções definidas pelo utilizador, o que proporciona uma flexibilidade adicional, permitindo aos programadores definir operações específicas que não são diretamente suportadas pelas funções integradas.



<br>

---

<br>

##  Documentação oficial da Microsoft

- [What are the SQL database functions?](https://learn.microsoft.com/en-us/sql/t-sql/functions/functions)


