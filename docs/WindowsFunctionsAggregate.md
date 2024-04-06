---
layout: default
title: Funções Agregadas ou Aggregate Functions
nav_order: 13.4
parent: 'Funções de Janela ou Windows Functions'
---


# Funções Agregadas ou Aggregate Functions
{: .no_toc }


As Funções Agregadas ou Aggregate Functions em inglês, permite realizar cálculos em conjuntos de dados, permitindo assim a análise e a obtenção de informações valiosas. 

Estas funções incluem: 
* A função `COUNT`, que conta o número de itens num conjunto; 
* A função `SUM`, que soma os valores; AVG, que calcula a média; 
* As funções `MIN` e `MAX`, que encontram o valor mínimo e máximo, respetivamente. 
* A função `GROUP BY`, que é frequentemente usada em conjunto com as funções agregadas para agrupar os resultados de uma consulta segundo um ou mais critérios.

<br>

**Utilizar funções agregadas** 
É importante frisar que, ao utilizar funções agregadas, deve-se ter em conta a possibilidade de valores nulos, que podem afetar o resultado. 

* Problema 1: a função `AVG` não conta valores nulo ao calcular a média. 

* Resolução 1: pode-se utilizar a função `COALESCE` ou` ISNULL` para substituir valores nulos por um valor predefinido antes de aplicar a função.


* Problema 2: A utilização de `DISTINCT` com funções agregadas permite eliminar valores duplicados de um conjunto antes de realizar o cálculo.

* Resolução 2: A utilização de `SUM(DISTINCT nome_coluna)` somaria apenas os valores únicos da coluna especificada.


**Funções mais avançadas***

O T-SQL também oferece funções avançadas para estatísticas:

* A função `STDEV`calcula o desvio padrão;
* A função `VAR`determina a variância. 

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Aggregate Functions (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql)


