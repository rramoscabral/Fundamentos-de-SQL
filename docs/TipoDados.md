---
layout: default
title: Tipo de dados
nav_order: 6
has_children: true
---



# Tipo de dados
{: .no_toc }


No Microsoft SQL Server, os tipos de dados são fundamentais para definir a natureza dos dados que podem ser armazenados numa tabela. 

O T-SQL, a linguagem de consulta transacional do SQL Server, oferece uma variedade de tipos de dados que ajudam a garantir a precisão e a eficiência do armazenamento de dados. 

Cada tipo de dado tnas suas próprias propriedades e limitações, e a escolha correta é crucial para o desempenho e a integridade da base de dados. Ao projetar uma base de dados, é importante considerar cuidadosamente quais tipos de dados são mais adequados para cada coluna, levando em conta não apenas o tipo de dado, mas também o tamanho máximo esperado, a precisão necessária e o comportamento esperado das consultas e operações que serão realizadas nesses dados.

Por exemplo, os tipos de dados numéricos incluem **int**, **decimal**, e **money**, que são adequados para armazenar números inteiros, valores decimais com precisão fixa e dados monetários, respetivamente. Para texto, temos **varchar** para texto de comprimento variável e **nvarchar** para texto Unicode. 

O **date**, **time**, **datetime2**, e **datetimeoffset** são utilizados para armazenar informações de data e hora com diferentes níveis de precisão e detalhes. Há também tipos de dados especializados como **xml** para armazenar dados XML e **varbinary** para armazenar dados binários. 




<br>

---

<br>

##  Documentação oficial da Microsoft

-[SQL Server Data types (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql)


* **Dados númericos**
    - [Tipos de dados do SQL Server (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql)
    - [int, bigint, smallint, and tinyint (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)
    - [decimal and numeric (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/decimal-and-numeric-transact-sql)
    - [float and real (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/float-and-real-transact-sql)
    - [Precision, scale, and length (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/precision-scale-and-length-transact-sql)

    <br>

* **Dados binários**

    - [binary and varbinary (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/binary-and-varbinary-transact-sql)


    <br>


* **Caracter e conjunto de caracteres**

    - [char and varchar (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/char-and-varchar-transact-sql)
    - [String Functions](https://learn.microsoft.com/en-us/sql/odbc/reference/appendixes/string-functions)
    - [LIKE (Transact-SQL) - SQL Server](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/like-transact-sql)
    - [Collation and Unicode support](https://learn.microsoft.com/en-us/sql/relational-databases/collations/)

    <br>

* **Data e hora**
    - [Date and time data types and functions (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)

    <br>

* **Conversão**
    - [Data type precedence (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/data-type-precedence-transact-sql)
    - [CAST and CONVERT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql)
    - [PARSE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/parse-transact-sql)
    - [TRY_PARSE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/try-parse-transact-sql)
