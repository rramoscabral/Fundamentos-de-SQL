---
layout: default
title: T-SQL operadores
nav_order: 2.2
parent: 'T-SQL'
has_children: true
---


# T-SQL operadores
{: .no_toc }


Os operadores no T-SQL são fundamentais para a construção de consultas e manipulação de dados em bases de dados SQL Server. 

Os operadores podem ser divididos em várias categorias:
* Operadores aritméticos, que incluem adição (+), subtração (-), multiplicação (*) e divisão (/); 
* Operadores de comparação, como igual (=), diferente de (<> ou !=), maior que (>), menor que (<), maior ou igual a (>=) e menor ou igual a (<=);
* Operadores lógicos, que englobam o AND, OR e NOT. 
* Operadores de conjunto, como UNION, INTERSECT e EXCEPT, que permitem combinar resultados de duas ou mais consultas.

É importante frisar o uso correto destes operadores pode otimizar o desempenho das consultas e garantir que os resultados sejam precisos e eficientes. 


**Exemplo**

```sql
USE AdventureWorks;
GO

SELECT * 
FROM Sales.SalesOrderDetail;

SELECT UnitPrice, (UnitPrice * 1.23) as 'Preço C/ IVA' 
FROM Sales.SalesOrderDetail
```


<br>

**Operadores de pesquisa**

O operador **EXISTS** pode ser utilizado para verificar a existência de um registo numa subconsulta, enquanto o operador **IN** permite especificar múltiplos valores numa cláusula WHERE. 

O operador **LIKE** é frequentemente usado em pesquisas de padrões de texto, com os caracteres **%** e **_** a servir como wild cards para múltiplos ou um único carácter, respetivamente.

<br>

**Operadores de cálculos**

O T-SQL também oferece funções agregadas como **COUNT**, **SUM**, **AVG**, **MIN** e **MAX**, que são essenciais para a realização de cálculos em grupos de dados. 

<br>

**Operadores de janela ou WINDOWS**

As funções de janela, como **ROW_NUMBER**, **RANK** e **DENSE_RANK**, também são operadores poderosos que permitem realizar cálculos complexos e análises de dados.


<br>

**Precedência dos operadores**

Ao escrever consultas em T-SQL, é crucial ter em mente a precedência dos operadores, que determina a ordem pela qual as operações são realizadas. 

Operadores com maior precedência são avaliados antes daqueles com menor precedência. 

Por exemplo, as operações aritméticas têm precedência sobre as operações de comparação, que por sua vez têm precedência sobre os operadores lógicos.

| Nível | Operador |
| --- | --- |
| 1 |	`~` (NOT bit a bit) |
| 2 |	`*` (MMultiplicação), `/` (Divisão), `%` (Módulo) |
| 3 |	`+` (Positivo), `-` (Negativo), `+` (Adição), `+` (Concatenação), `-` (Subtração), `&` (AND bit a bit), `^` (OR bit a bit Exclusivo), `&#124;` (OR Bit a bit ) |
| 4 |	`=`, `>`, `<`, `>=`, `<=`, `<>`, `!=`, `!>`, `!<` (Operadores de comparação) |
| 5 |	`NOT` |
| 6 |	`AND` |
| 7 |	`ALL`, `ANY`, `BETWEEN`, `IN`, `LIKE`, `OR`, `SOME` |
| 8 |	`=` (Atribuição) |


<br>

Compreender e aplicar corretamente estes operadores permite construir consultas eficazes e precisas, manipular dados de forma eficiente e realizar análises complexas, contribuindo assim para a gestão eficaz da informação e suporte à tomada de decisões nas organizações.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Operators (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/operators-transact-sql)
- [Operator Precedence (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/operator-precedence-transact-sql)

