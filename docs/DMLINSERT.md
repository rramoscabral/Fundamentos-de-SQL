---
layout: default
title: INSERT Statement
nav_order: 7.1
parent: 'Linguagem de manipulação de dados'
---


# INSERT Statement
{: .no_toc }


O **INSERT** é frequentemente acompanhado de cláusulas que especificam exatamente onde e como os novos dados devem ser inseridos na base de dados.


## INSERT INTO

**Sintaxe** 

Indicação dos nomes das colunas e os valores que serão inseridos. Não é obrigatório respeitar a ordem das colunas na tabela.

```sql
INSERT INTO [esquema].[tabela] (coluna1, coluna2, coluna3, ...)
valorS (valor1, valor2, valor3, ...); 
```

Não é especificado o nome das colunas mas tem de respeitar a ordem das colunas da tabela. 

```sql
INSERT INTO [esquema].[tabela]
valorS (valor1, valor2, valor3, ...); 
```

Em ambas as situações as colunas da tabela que não aceitem valores em desconhecidos (em branco ou nulos) são obrigados a estarem presentes.


**Exemplo**

```sql
INSERT INTO Sales.Customers valorS('Formação','Lisboa','XPTO','PT','','','','','','');

INSERT INTO Sales.Customers (companyname,city,address,country, contactname,contacttitle,phone)
valorS('Formação','Lisboa','XPTO','PT','','','');

SELECT * FROM Sales.Customers
```

<br>



## SELECT INTO

Copia todas as colunas de uma tabela para uma nova tabela com a utilização do **`*`**. A utilização de uma condição é opcional.

```sql
SELECT * INTO [esquema].[nova_tabela]
FROM [esquema].[tabela_origem]
WHERE condição;
```

Copias apenas as colunas definidas para uma nova tabela. A utilização de uma condição é opcional.

```sql
SELECT coluna1, conluna2 INTO [esquema].[nova_tabela]
FROM [tabela_origem]
WHERE condição;
```




<br>

---

<br>

##  Documentação oficial da Microsoft

- [INSERT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/statements/insert-transact-sql)

- [Table valor Constructor (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/table-valor-constructor-transact-sql)

- [SELECT - INTO Clause (Transact-SQL)](
https://learn.microsoft.com/en-us/sql/t-sql/queries/select-into-clause-transact-sql)