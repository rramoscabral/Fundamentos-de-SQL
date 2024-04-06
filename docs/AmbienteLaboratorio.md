---
layout: default
title: Ambiente Laboratório
nav_order: 1.1
parent: 'Introdução aos Fundamentos de SQL com Transact-SQL'
---


# Ambiente Laboratório
{: .no_toc }

## Índice
{: .no_toc .text-delta }

## Ambiente Laboratório

O formando pode utilizar um ambiente virtual facultado pela entidade de formação, uma máquina virtual alojada na cloud ou a sua própria máquina local ou virtual.

## Software


O ambiente de laboratório para realizar os exercícios requer que disponha do seguinte software.

* Microsoft SQL Server
* Microsoft SQL Sever Manangement Studio ou Azure Data Studio



## Base de dados

A base de dados utilizado é a base de dados de amostra **AdventureWorks** da Microsoft para OLTP, cargas de trabalho típicas de processamento de transações online.

Oferece suporte a cenários padrões de processamento de transações on-line para fabricação, vendas, compras, gestão de produtos, gestão de contatos e recursos humanos.

O design desta base de dados progrediu desde que AdventureWorks foi publicado pela primeira vez mas não sofreu nenhuma mudança significativa desde a versão de 2012. A única diferença entre as versões é o nível de compatibilidade da base de dados. 
<br>

**Quem é AdventureWork**
É uma empresa multinacional fictícia que vende bicicletas e acessórios para ciclismo.

<br>

Esta base de dados de amostra tem diversas verões desde do SQL Server 2008 ao 2022.

Para instalar a base de dados AdventureWorks com o nível de compatibilidade da base de dados na instância do SQL Server, você pode instalar a partir de um ficheiro de backup específico da versão ou de um script de instalação.

Pode fazer o download [aqui](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure) e restaurar para SQL Server.


**Exemplo de comando T-SQL para restaurar uma base de dados**

```sql
USE master
GO

RESTORE DATABASE AdventureWorksDW2016
FROM disk= 'C:\Backup\AdventureWorksDW2016.bak'
WITH MOVE 'AdventureWorksDW2016_data' TO 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\AdventureWorksDW2016.mdf',
MOVE 'AdventureWorksDW2016_Log' TO 'C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\AdventureWorksDW2016.ldf',REPLACE
GO
```



