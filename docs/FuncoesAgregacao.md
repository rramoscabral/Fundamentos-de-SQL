---
title: Funções agregação
layout: default
nav_order: 8.2
parent: 'Funções integradas no T-SQL'
---



# Funções agregação
{: .no_toc }


As funções de agregação em T-SQL são essenciais para a análise e síntese de dados em bases de dados SQL Server. 

Estas funções permitem realizar cálculos num conjunto de valores e retornar um único valor. 

* A função `SUM()` é utilizada para somar todos os valores de uma coluna específica.

* A função `COUNT()` conta o número de itens numa coluna, incluindo ou excluindo os valores nulos, dependendo se especificado `COUNT(*)` ou `COUNT(column_name)`. 

* A função `AVG()` calcula a média dos valores.

* As funções `MAX()` e `MIN()` retornam, respetivamente, o maior e o menor valor de uma coluna. É importante notar que estas funções ignoram os valores nulos, exceto no caso do `COUNT(*)`. 


As funções de agregação podem ser combinadas com a cláusula `GROUP BY`, que agrupa os resultados conforme os valores de uma ou mais colunas, permitindo assim uma análise mais detalhada dos dados.

Pode-se utilizar `GROUP BY` para agrupar vendas por região e depois aplicar a função `SUM()` para calcular o total de vendas por região.

A função `OVER()`, que permite realizar cálculos de agregação em janelas de dados específicas, sem a necessidade de agrupar os resultados. Esta função é particularmente útil para cálculos complexos em conjuntos de dados particionados. 

Em resumo, as funções de agregação são ferramentas poderosas para a manipulação e análise de grandes volumes de dados, permitindo extrair informações significativas e apoiar a tomada de decisões baseada em dados. É crucial entender bem estas funções para maximizar o potencial analítico do T-SQL em ambientes de bases de dados SQL Server.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Aggregate Functions (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql)