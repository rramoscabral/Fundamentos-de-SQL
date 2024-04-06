---
layout: default
title: MERGE Statement
nav_order: 7.3
parent: 'Linguagem de manipulação de dados'
---


# MERGE Statement
{: .no_toc }


O **MERGE**, permite combinar operações de inserção, atualização e eliminação numa única instrução, otimizando assim as transações e a manutenção de dados. 


É uma instrução poderosa que permite realizar operações de inserção, atualização ou exclusão numa única declaração. 

Esta instrução é particularmente útil quando se deseja sincronizar duas tabelas, ou seja, atualizar uma tabela de destino com base nos dados de uma tabela de origem. 

**Sintaxe básica**

```sql
MERGE TOP (value) <tabela_destino> 
USING <tabela_fonte>   
ON <merge_condições_de_pesquisa>  
    [ QUANDO COINCIDE [ AND <condição_de_pesquisa_de_cláusula> ]  
        THEN <merge_correspondida> ] 
    [ QUANDO NÃO COINCIDE [ BY TARGET ] [ AND <condição_de_pesquisa_de_cláusula> ]  
        THEN <merge_não_correspondido> ]  
    [ QUANDO NÃO COINCIDE PELA FONTE [ AND <condição_de_pesquisa_de_cláusula> ]  
        THEN <merge_coincide> ] 
    [ <cláusula_de_saída> ]  
    [ OPÇÃO ( <query_hint> ) ]      
```


A sintaxe básica do MERGE começa com a palavra-chave MERGE seguida pelo nome da tabela de destino. Depois, utiliza-se a cláusula USING para especificar a tabela de origem dos dados. 

A cláusula ON define a condição de correspondência entre as tabelas de origem e destino. As cláusulas WHEN MATCHED e WHEN NOT MATCHED especificam as ações a serem tomadas quando os dados correspondem ou não. 

Por exemplo, pode-se atualizar os dados na tabela de destino se eles correspondem aos da tabela de origem, ou inserir novos dados se não houver correspondência. É importante frisar que o MERGE deve ser usado com cuidado, pois a execução de múltiplas operações numa única instrução pode ser complexa e suscetível a erros se não for bem compreendida e cuidadosamente implementada. 


Tem que garantir que as condições de correspondência sejam corretas para evitar resultados inesperados. 

Em resumo, o MERGE é uma ferramenta versátil em T-SQL que, quando usada corretamente, pode simplificar e otimizar as operações de sincronização de dados entre tabelas.

**Exemplo 1** 

```sql

USE AdventureWorks
GO

--Criar uma tabela de destino

CREATE TABLE dbo.Students (
    StudentId int IDENTITY(1,1) NOT NULL,
    FirstName varchar(50),
    LastName varchar(50)
);
GO

INSERT INTO dbo.Students VALUES 
    ('Pedro', 'Gato'), 
    ('Julia', 'Caracol'), 
    ('Margarida', 'Borboleta');
GO

SELECT * FROM Students;
GO

--MERGE statement

DECLARE @Changes TABLE(Change VARCHAR(20));

MERGE INTO dbo.Students AS Target  
USING ( VALUES 
            (3, 'Clara', 'Lémure'), 
            (7, 'Carlos','Águia'), 
            (8, 'Silvia', 'Arara')
        ) AS Source ( StudentId, FirstName, LastName )  
ON Target.StudentId = Source.StudentId
AND Target.FirstName = Source.FirstName
WHEN MATCHED THEN
    UPDATE SET FirstName = Source.FirstName, LastName = Source.LastName
WHEN NOT MATCHED BY TARGET THEN
    INSERT (FirstName, LastName) VALUES (Source.FirstName, Source.LastName)
OUTPUT $action INTO @Changes;

SELECT Change, COUNT(*) AS Count  
FROM @Changes  
GROUP BY Change;

SELECT * FROM dbo.Students;

```

*Desafio:* O estudante com o ID 3 é Margarida ou a Clara?


**Exemplo 2** 

```sql

--Criar tabela de origem
CREATE TABLE dbo.Courses (
    StudentId int IDENTITY(1,1) NOT NULL,
    FirstName varchar(50),
    LastName varchar(50),
    Course varchar(50)
);
GO

INSERT INTO dbo.Courses VALUES 
    ('Pedro', 'Gato','SQL'), 
    ('Julia', 'Caracol','SQL'), 
    ('Catarina', 'Tubarão','SQL');
GO


SELECT * FROM dbo.Courses;
GO

--MERGE statement

SET IDENTITY_INSERT dbo.Students ON;
GO

MERGE dbo.Students AS TARGET
USING dbo.Courses AS SOURCE 
ON (TARGET.StudentId = SOURCE.StudentId) 
WHEN MATCHED AND TARGET.FirstName <> SOURCE.FirstName AND TARGET.LastName  <> SOURCE.LastName  
THEN UPDATE SET TARGET.FirstName = SOURCE.FirstName, TARGET.LastName  = SOURCE.LastName  
WHEN NOT MATCHED BY TARGET 
THEN INSERT (StudentId, FirstName, LastName ) VALUES (SOURCE.StudentId, SOURCE.FirstName, SOURCE.LastName )
WHEN NOT MATCHED BY SOURCE 
THEN DELETE 
OUTPUT $action, 
DELETED.StudentId AS TargetStudentId, 
DELETED.FirstName AS TargetFirstName, 
DELETED.LastName  AS TargetLastName , 
INSERTED.StudentId AS SourceStudentId, 
INSERTED.FirstName AS SourceFirstName, 
INSERTED.LastName  AS SourceLastName; 

SELECT @@ROWCOUNT;
GO



SELECT * FROM dbo.students;
GO

```

Tabela de destino apos finalizar o exemplo 1.

| StudentId | FirstName	| LastName |
| --- | --- | --- |
| 1	| Pedro	| Gato |
| 2	| Julia	| Caracol |
| 3	| Margarida | Borboleta |
| 4	| Clara	 | Lémure |
| 5	| Carlos | Águia |
| 6	| Silvia | Arara |

Tabela de destino do exemplo 2 depois do merge.

| StudentId | FirstName	| LastName |
| --- | --- | --- |
| 1	| Pedro	| Gato |
| 2	| Julia	| Caracol |
| 3	| Catarina | Tubarão |


<br>

---

<br>

##  Documentação oficial da Microsoft

- [MERGE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/statements/merge-transact-sql)

