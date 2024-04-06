---
layout: default
title: Stored Procedures
nav_order: 15
has_children: true
---




# Stored Procedures
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Stored Procedures

Os Stored Procedures permitem a executar de conjuntos de comandos SQL de forma eficiente e segura. 

Estes procedimentos são armazenados na própria base de dados por este motivo tem de ter direitos para criar um Stored Procedures.

A utilização de Stored Procedures oferece várias vantagens:
* Reutilização do código SQL;
* Manutenção simplificada do código SQL;
* Mensagens de erro caso o código não seja executado com sucesso.
* O resultado pode ficar no cache do servidor e ser reutilizado pelo motor permitindo a redução de execução.
* Segurança em que é possível definir se o procedimento faz operações de leitura e/ou escrita.

<br>

## Criar um Stored Procedures

A criação de uma Stored Procedure é feita através da instrução `CREATE PROCEDURE` com a definição dos parâmetros de entrada e do bloco de código SQL que pretende ser executado. Opcionalmente pode definir parâmetros de saída, que permitem devolver valores após a execução do procedimento.


**Sintaxe básica**

A sintaxe básica para a criar (`CREATE`) ou alterar (`ALTER`) um `Stored Procedures` é a seguinte: 

```sql
CREATE [ OR ALTER ] { PROC | PROCEDURE }
    [schema_name.] procedure_name [ ; number ]
    [ { @parameter_name [ type_schema_name. ] data_type }
        [ = default ] [ OUT | OUTPUT ] [READONLY]
    ] [ ,...n ]
[ WITH EXECUTE AS Clause ]
AS { EXTERNAL NAME assembly_name.class_name.method_name }
[;]
```

```sql
```


<br>

## Executar Stored Procedures 

**Sintaxe básica**

A sintaxe básica para a executar um `Stored Procedures` com parâmetros de entrada e saída é a seguinte: 

```sql
DECLARE @<parâmetro_saída> AS <type>;
{ EXEC | EXECUTE } <nome_stored_procedure> <lista_parâmetros_enrada>, @<parâmetro_saída> OUTPUT;
SELECT @parametro_saída;
```
* O procedimento pode ser executado com `EXEC` ou `EXECUTE`.


<br>

## Criar e executar consultas dinâmicas

**Sintaxe básica**

A sintaxe básica para a executar um procedimento dinámico que suporta parâmetros (sys.sp_executesql):

```sql
DECLARE @sqlcode AS NVARCHAR(256) = 	N'<code_to_run>';
EXEC sys.sp_executesql @statement = @sqlcode;
```

É altamente recomendado execuatar com o `sys.sp_executesql` porque permite verificar ataques de SQL injection attacks definidos nos parâmetros.

**Exemplo***

Obtém a data e hora do servidor.

```sql
DECLARE @sqlcode AS NVARCHAR(256) = 
    N'SELECT SYSDATETIME()  AS ServerDate';
EXEC sys.sp_executesql @statement = @sqlcode;
```

<br>

---

<br>

##  Documentação oficial da Microsoft


- [CREATE PROCEDURE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/statements/create-procedure-transact-sql)