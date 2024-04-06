---
layout: default
title: Funções com Valor de Tabela ou Table-Valued Functions (TVFs)
nav_order: 11.3
parent: 'Expressões de consulta'
---


# Funções com Valor de Tabela ou Table-Valued Functions (TVFs)
{: .no_toc }


## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Funções com Valor de Tabela ou Table-Valued Functions (TVFs)

As Funções com Valor de Tabela ou Table-Valued Functions (TVFs) em inglês, é um tipo de função definida pelo utilizador que devolve um conjunto de dados no formato tabular.

Podem ser comparadas a Views parametrizáveis que são executadas sempre que são invocadas numa consulta.

Existem dois tipos principais de TVFs:
* As funções de valor de tabela em linha ou Inline TVFs (Table-Valued Functions) em inglês, que são definidas por uma única instrução **`SELECT`** e devolve o resultado diretamente.
* As funções de valor de tabela de múltiplas instruções ou Multi-statement TVFs (Table-Valued Functions) em inglês, que podem conter várias instruções SQL e utilizam uma variável da tabela para armazenar os dados temporariamente.


## Criar uma função de valor de tabela em linha ou Inline TVFs (Table-Valued Functions)


Para cria um inline TVFs tem de ter o privilégio de **database developer** ou **database administrator** na base de dados.


Para criar uma TVF em linha, utiliza-se a cláusula **RETURNS TABLE** juntamente com a instrução **RETURN** que contém a query. 

O seguinte exemplo, é uma função devolves os produtos de uma determinada cor.

```sql
CREATE FUNCTION Production.udf_ProductsColor(@color NVARCHAR(15))
RETURNS TABLE
AS
RETURN (
    SELECT Name, Color, ListPrice
    FROM Production.Product
    WHERE Color = @color
);

SELECT *
FROM Production.udf_ProductsColor('Black');

-- Apagar a FUNCTION
DROP FUNCTION IF EXISTS Production.udf_ProductsColor;
GO
```

> O **`udf`** no nome da função significa **`User-defined functions (UDFs)`** em que aceita uma entrada de dados para realizar uma operação.

Esta função aceita um parâmetro de entrada e devolve uma tabela com os produtos correspondentes a cor do produto especificado. 



## Criar uma função de valor de tabela de múltiplas instruções ou Multi-statement TVF

É uma função definida pelo utilizador que e devolve uma tabela com múltiplas linhas e colunas.

O seguinte exemplo representa uma função aceita um ID de subcategoria como parâmetro e devolve uma tabela com os detalhes do produto para essa subcategoria.

```sql
CREATE FUNCTION Production.udf_GetProductsBySubcategory(@SubcategoryID int)
RETURNS @ProductTable TABLE 
(
    ProductID int,
    Name nvarchar(50),
    ProductNumber nvarchar(25),
    Color nvarchar(15)
)
AS
BEGIN
    INSERT INTO @ProductTable(ProductID, Name, ProductNumber, Color)
    SELECT ProductID, Name, ProductNumber, Color
    FROM Production.Product
    WHERE ProductSubcategoryID = @SubcategoryID;

    RETURN;
END;

SELECT *
FROM Production.ufnGetProductsBySubcategory(1);
```



## Modificar um TVF

Para modificar uma TVF, usa-se a palavra-chave **ALTER** em vez de **CREATE**, mantendo o resto da definição da função inalterado.


Com a modificação pode reutilizar o código e a capacidade de encapsular lógica complexa numa forma que pode ser facilmente utilizada em várias queries. 

Também pode melhorar a legibilidade e a manutenção do código, pois permitem dividir queries complexas em componentes mais simples e modulares.


## Desempenho
É importante frisar que as TVFs podem ter impacto no desempenho, especialmente se devolverem um grande número de linhas ou se forem utilizadas em joins complexos. Portanto, é essencial avaliar cuidadosamente o uso de TVFs em relação aos requisitos de desempenho e às alternativas disponíveis, como procedimentos armazenados ou vistas.



<br>

---

<br>

##  Documentação oficial da Microsoft

- [CREATE FUNCTION (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/statements/create-function-transact-sql)
- [User-defined functions](https://learn.microsoft.com/en-us/sql/relational-databases/user-defined-functions/user-defined-functions)
