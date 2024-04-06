---
layout: default
title: Linguagem de Consulta de dados
nav_order: 3
has_children: true
---

## Linguagem de Consulta de dados ou Data Query Language (DQL).

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Linguagem de Consulta de dados ou Data Query Language (DQL).

É uma parte fundamental da Transact-SQL (T-SQL), a linguagem de programação utilizada pelo Microsoft SQL Server. No contexto do SQL Server, a DQL é usada para realizar consultas aos dados armazenados numa base de dados, permitindo a recuperação de informações de acordo com critérios específicos. Em T-SQL, os comandos mais comuns associados à DQL são **SELECT**, que é utilizado para selecionar dados de uma ou mais tabelas, e **WHERE**, que serve para filtrar registos que satisfaz uma condição especificada.

<br>

**Sintaxe básica**

Selecionar todas as colunas numa tabela.

```sql
SELECT * 
FROM [esquema].[tabela] 
WHERE condição;
```


Selecionar colunas especificas numa tabela.

```sql
SELECT coluna1, coluna2 
FROM [esquema].[tabela] 
WHERE condição;
```


## Operadores e funções

Para escrever consultas eficientes em T-SQL, é importante compreender a estrutura das tabelas e as relações entre elas. Além disso, deve-se ter conhecimento sobre os operadores lógicos como **AND**, **OR**, e **NOT**, que ajudam a refinar as condições de busca e sobre as funções de agregação como **COUNT**, **SUM**, **AVG**, **MIN**, e **MAX**, que permitem realizar cálculos sobre um conjunto de valores.

## Agrupar e ordenar

Outro aspecto relevante é a capacidade de ordenar e agrupar os resultados das consultas, o que é feito através das cláusulas **ORDER BY** e **GROUP BY**. 
- A cláusula **ORDER BY** é utilizada para definir a ordem de exibição dos dados, seja em ordem ascendente (**ASC**) ou descendente (**DESC**).
- A cláusula **GROUP BY** é usada para agrupar linhas que têm os mesmos valores em colunas especificadas, permitindo realizar operações de agregação sobre cada grupo.


## Idioma de sessão

Na sessão de utilizador pode-se definir o idioma pretendido para as resposta das instruções.

```sql
SET LANGUAGE Portuguese
GO

SELECT OBTERDATA();
GO

-- Msg 195, Level 15, State 10, Line 144
-- 'OBTERDATA' não é um nome da função incorporada reconhecido.

SET LANGUAGE English;
GO

SELECT OBTERDATA()
GO

-- Resposta: Msg 195, Level 15, State 10, Line 144
--'OBTERDATA' is not a recognized built-in function name.

```



<br>

---

<br>

##  Documentação oficial da Microsoft

- [SET LANGUAGE (Transact-SQL)](https://learn.microsoft.com/pt-br/sql/t-sql/statements/set-language-transact-sql)

