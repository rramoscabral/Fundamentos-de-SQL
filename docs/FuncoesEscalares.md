---
title: Funções escalares
layout: default
nav_order: 8.1
parent: 'Funções integradas no T-SQL'
---



# Funções escalares
{: .no_toc }


As funções escalares em T-SQL são essenciais para a manipulação e análise de dados em bases de dados SQL Server. 

Estas funções permitem realizar operações em nível de coluna, retornando um único valor por cada chamada.

* A função **LEN** permite obter o comprimento de uma string.
* A função **GETDATE()** permite obter a data e hora atuais.

Ambas as funções são amplamente utilizadas em consultas e procedimentos armazenados.

Funções matemáticas como **ROUND**, **FLOOR** e **CEILING** permitem arredondamentos e ajustes de valores numéricos com precisão. 

É também possível criar funções definidas pelo utilizador, que estendem as capacidades do T-SQL para se adequarem a necessidades específicas de negócio. 


Ao criar uma função escalar definida pelo utilizador, é importante garantir que ela seja eficiente e testado, para não comprometer o desempenho das consultas. 

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Deterministic and Nondeterministic Functions](https://learn.microsoft.com/en-us/sql/relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions)