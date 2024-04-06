---
layout: default
title: Laboratório
nav_order: 6.2
parent: 'Tipo de dados'
---

# Exercício 6 – Tipo de dados
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório

Foi lhe solicitado extrair os dados das pessoas registadas na base de dados da Adventure Works para ser reutilizado noutro sistema. É importante que alguns caracteres sejam removidos devido a não ser compatível com o novo sistema. Nenhum dado existente deve ser alterado. 


<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:
- Substituir texto numa consulta T-SQL. 


<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 30 minutos


<!-- Tasks -->

## Tarefa 1 - Extrair o nome da pessoa registada se o apostrofe (15 minutos)

1. Utilize a base de dados Adventure Work.


    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>

    ```sql
    USE AdventureWorks
    GO
    ```

    </details>

    <br>


1. Registre uma nova pessoa com o nome **O'Neil Jackson** utilizando as seguintes instruções.

    <br>

    ```sql
    SET IDENTITY_INSERT Person.BusinessEntity ON;
    GO

    INSERT INTO Person.BusinessEntity (BusinessEntityID, rowguid)
    VALUES(90001, NEWID());
    GO

    INSERT INTO Person.Person(FirstName, LastName, BusinessEntityID, PersonType)
    VALUES('O''Neil','Jackson',90001,'EM');
    GO
    ```

    <br>
 

1. Escreva e execute uma consulta T-SQL que mostre a pessoa O'Neil Jackson sem apostrofe e o resultado é identificado como **Pessoa** tendo apenas uma coluna.

    <br>

    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>

    ```sql
    SELECT REPLACE(FirstName, '''', '') + ' ' + LastName AS Pessoa
    FROM Person.Person
    WHERE FirstName = 'O''Neil';
    ```

    </details>

    <br>

    Resultado esperado 

    | Pessoa| 
    | --- | 
    | ONeil Jackson |

    <br>

1. Se na questão anterior utilizou **+** para concatenar strings (conjunto de texto) rescreva a consulta utilizando a função **CONCAT**. 


    <br>

    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>

    ```sql
    SELECT CONCAT(Replace(FirstName, '''', ''), ' ',LastName) AS Pessoa
    FROM Person.Person
    WHERE FirstName = 'O''Neil';
    ```

    </details>

   <br>

    Resultado esperado 

    | Pessoa| 
    | --- | 
    | ONeil Jackson |

    <br>



## Tarefa 2 - Substituir moradas que iniciam com o número zero a esquerda (15 minutos).


1. Utilize o operador LIKE para pesquisar todas as moradas que iniciem com o número zero na tabela **Person.Address**.

    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>

    ```sql
    SELECT AddressID, AddressLine1
    FROM Person.Address
    WHERE AddressLine1 LIKE '0%';
    ```

    </details>

    <br>

    Resultado esperado 

    | AddressID	| AddressLine1 |
    | --- | --- | 
    | 29781	| 00, rue Saint-Lazare |
    | 24231	| 02, place de Fontenoy | 
    | 19637	| 035, boulevard du Montparnasse |
    | 15671	| 081, boulevard du Montparnasse |
    | 13079	| 081, boulevard du Montparnasse |
    | 21354	| 084, boulevard du Montparnasse |

    <br>




1. Utilize a função **PATINDEX** para obter a posição onde o primeiro zero ocorre. 

   > Documentação [PATINDEX (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/patindex-transact-sql)


    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>
 
    ```sql
    SELECT PATINDEX('0%', AddressLine1)
    FROM Person.Address
    WHERE AddressLine1 LIKE '0%';
    ```

    </details>

    <br>

    Resultado esperado 

    | # | (No column name) |
    | --- | --- | 
    | 1 | 1 |
    | 2 | 1 |
    | 3 | 1 |
    | 4 | 1 |
    | 5 | 1 |
    | 6 | 1 |

    <br>


1. Utilize a função **SUBSTRING** para remover o primeiro zero a esquerda.

    <br>

   > Documentação [PATINDEX (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/patindex-transact-sql)

    <br>

    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>
 
    ```sql
    SELECT SUBSTRING (AddressLine1, 2, LEN(AddressLine1) ) AS AddressLine1
    FROM Person.Address
    WHERE AddressLine1 LIKE '0%';
    ```

    </details>

    <br>

    Resultado esperado 

    | - | AddressLine1 |
    |  --- | --- | 
    | 1 | 0, rue Saint-Lazare |
    | 2 | 2, place de Fontenoy |
    | 3 | 35, boulevard du Montparnasse |
    | 4 | 81, boulevard du Montparnasse |
    | 5 | 81, boulevard du Montparnasse |
    | 6 | 84, boulevard du Montparnasse |


    <br>


1. Com base da reposta dos exercícios anteriores utilize a expressão **CASE** para remover o primeiro zero quando este existir. 

    <br>

    <details markdown="block">
    <summary>Expanda esta seção para visualizar a solução.</summary>
 
    ```sql
    SELECT AddressID,
        CASE SUBSTRING(AddressLine1, 1, 1)
            WHEN '0' THEN SUBSTRING (AddressLine1, 2, LEN(AddressLine1) )
            ELSE AddressLine1
        END AS AddressLine1
    FROM Person.Address
    WHERE AddressLine1 LIKE '0%';
    ```

    </details>

    <br>

    Resultado esperado 

    | - | AddressLine1 |
    |  --- | --- | 
    | 1 | 0, rue Saint-Lazare |
    | 2 | 2, place de Fontenoy |
    | 3 | 35, boulevard du Montparnasse |
    | 4 | 81, boulevard du Montparnasse |
    | 5 | 81, boulevard du Montparnasse |
    | 6 | 84, boulevard du Montparnasse |


    <br>






<br>


Com o SQL Server 2022 esta tarefa podia ser resolvida com o a função [LTRIM](https://learn.microsoft.com/en-us/sql/t-sql/functions/ltrim-transact-sql).


