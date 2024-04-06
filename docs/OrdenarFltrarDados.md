---
layout: default
title: Ordenar e filtrar dados
nav_order: 5
has_children: false
---


# Ordenar e filtrar dados
{: .no_toc }

O T-SQL permite classificar, filtrar, ordenar até mesmo limitar os resultados numa consulta de dados.

A cláusula **ORDER BY** permite classificar e ordenar os dados de forma ascendente ou decrescente.

A cláusula **TOP** permite obter o número de linhas pretendidas ou uma percentagem dos resultados e pode ser utilizado com a cláusula **ORDER BY**.

A cláusula **OFFSET-FETCH** é uma combinação de duas ações **OFFSET** e **FETCH** que é utilizado após a cláusula **ORDER BY**.
* O **OFFSET** define o número de linhas que pretendemoss ignorar.
* O **FETCH** definir o número de linhas que pretendemos obter após o `OFFSET`.

    ```sql
    OFFSET 5 ROWS --Ignora 5 linhas
    FETCH NEXT 20 ROWS ONLY; --Obtém as próximas 20 linhas
    ```


A cláusula **DISTINCT** permite remover duplicados.

A cláusula **WHERE** permite filtrar os dados utilizando predicados.


<br>

---

<br>

##  Documentação oficial da Microsoft

Ordenar dados
- [SELECT - ORDER BY Clause (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-order-by-clause-transact-sql)

Filtrar Dados com Predicados
- [TOP (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/top-transact-sql)
- [FETCH (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/fetch-transact-sql)

Trabalhar com valores desconhecidos
- [IS NULL (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql)


<br>