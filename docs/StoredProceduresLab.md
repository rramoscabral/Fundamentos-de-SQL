---
layout: default
title: Laboratório
nav_order: 15.1
parent: 'Stored Procedures'
---

# Exercício 15 – Stored Procedures
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório

Um procedimento permite armazenar e executar comandos SQL e a AdventureWorks tem a necessidade de criar procedimentos para serem reutilizadas pelos utilizadores e aplicações informáticas.

<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:

* Criar e executar Stored Procedures.


<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 30 minutos

<br>

## Tarefa 1 - Criar e executar Stored Procedures  (30 minutos)


1. Crie um Stored Procedure denomimado **Production.ProdsByColor** com as seguintes condições:
    * Consulte a tabela **Production.Product** e obtenha as colunas **ProductID**, **Name**, e **ListPrice**. 
    * Os resultados são filtrados pela cor definida pelo utilizador.
    * O procedimento tem dois parâmetros de entrada:
        * O **numrows** que recebe o número de linhas a ser visualizadas definido pelo utilizador.
        * O **color** que recebe a cor definida pelo utilizador.
  

1. Execute o procedimento **Production.ProdsByColor** e selecione apenas os primeiros 5 registos e cor **Red**.


1. Remova o procedimento **Production.ProdsByColor** na base de dados. 


1. O seguinte storage procedure tem um problema e requer que seja corrigido. Corrija e execute o mesmo.

    Código:
    ```sql
    DROP PROCEDURE IF EXISTS dbo.GetProductsByCategory;

    CREATE PROCEDURE dbo.GetProductsByCategory
    @CategoryName NVARCHAR(50)
    AS
    BEGIN
        SELECT p.ProductID, p.Name, p.Color, pc.Name AS Category
        FROM Production.Product p
        INNER JOIN Production.ProductSubcategory ps ON p.ProductSubcategoryID = ps.ProductSubcategoryID
        INNER JOIN Production.ProductCategory pc ON 
        ps.ps.Name = pc.Name
        WHERE pc.Name = @CategoryName;
    END;

    EXEC dbo.GetProductsByCategory 
    @CategoryName = 'Bikes'
    ```


<br>