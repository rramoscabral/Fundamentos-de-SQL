---
layout: default
title: Tipo de dados númericos
nav_order: 6.1
parent: 'Tipo de dados'
---



# Tipo de dados númericos
{: .no_toc }


Os tipos de dados numéricos no SQL Server são fundamentais para o armazenamento e manipulação de variáveis numéricas. Existem vários tipos de dados numéricos que podem ser utilizados, dependendo da precisão e da escala. Os tipos exatos incluem **SMALLINT**, **INTEGER**, **BIGINT**, **NUMERIC(p,s)** e **DECIMAL(p,s)**, onde **p** representa a precisão total de dígitos e **s** a escala, ou seja, o número de dígitos à direita do ponto decimal. Estes tipos são chamados de exatos porque representam valores numéricos sem perda de precisão.

Por outro lado, os tipos de dados numéricos aproximados, como **FLOAT(p)** e **REAL**, são utilizados quando é aceitável uma representação aproximada do valor numérico, o que pode ser útil em cálculos científicos ou quando o volume de dados é tão grande que a precisão exata não é necessária. O tipo **FLOAT(p)** permite uma precisão variável e é ideal para situações onde a escala dos números pode variar amplamente.

O SQL Server oferece os tipos **MONEY** e **SMALLMONEY**, que são otimizados para operações monetárias, onde a precisão dos valores até quatro casas decimais é crucial. Estes tipos são frequentemente utilizados em sistemas financeiros e contábeis, onde a precisão dos cálculos monetários é de extrema importância.

É importante frisar que a escolha do tipo de dado numérico adequado pode ter um impacto significativo no desempenho da aplicação, na precisão dos cálculos e na otimização do espaço de armazenamento. Portanto, é essencial entender as características e limitações de cada tipo de dado numérico disponível no SQL Server para fazer a melhor escolha para cada situação específica.

Para mais informações detalhadas sobre os tipos de dados numéricos no SQL Server e como utilizá-los com T-SQL, pode-se consultar a documentação oficial da Microsoft. Esta documentação oferece uma visão abrangente e exemplos práticos que podem ajudar tanto iniciantes quanto profissionais experientes a aprofundar seus conhecimentos e habilidades no uso de T-SQL para manipulação de dados numéricos no SQL Server.


<br>

---

<br>

##  Documentação oficial da Microsoft

- [Tipos de dados do SQL Server (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql)
- [int, bigint, smallint, and tinyint (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)
- [decimal and numeric (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/decimal-and-numeric-transact-sql)
- [float and real (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/float-and-real-transact-sql)
- [Precision, scale, and length (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/data-types/precision-scale-and-length-transact-sql)
