---
layout: default
title: Tabelas Derivadas ou Derived Tables
nav_order: 11.4
parent: 'Expressões de consulta'
---


# Tabelas Derivadas ou Derived Tables
{: .no_toc }


Tabelas Derivadas ou Derived Tables em inglês permite simplificar consultas complexas, permitindo que cri uma subconsulta dentro da cláusula `FROM` de uma consulta principal. 


**As tabelas derivadas são temporárias e só existem durante a execução da consulta**. Não ficam armazenadas na base de dados, assim não têm nenhum impacto na estrutura de dados.


Estas subconsultas são tratadas como tabelas normais pelo SQL Server, o que significa que podem ser utilizadas para `JOINs`, `WHERE` ou até mesmo em outras subconsultas. 

A principal vantagem das tabelas derivadas é a sua capacidade de encapsular a complexidade, tornando a consulta principal mais limpa e fácil de entender. 

## Criar uma tabelas derivadas ou derived table

Para criar uma tabela derivada, começa-se com uma subconsulta entre parênteses, seguida de um alias que serve como referência para a tabela resultante. Este alias é essencial, pois sem ele, a tabela derivada não pode ser referenciada na consulta exterior. 

As tabelas derivadas devem ter:
* Tem de conter um alias.
* Nomes de colunas únicos;
* Não pode ter colunas sem nome.
* Não podem incluir uma cláusula ORDER BY na subconsulta, a menos que também sejam utilizadas as cláusulas `TOP` ou `OFFSET-FETCH`.
* Não pode ser referenciada várias vezes na mesma consulta

<br>

**Sintaxe básica**

```sql
SELECT coluna1, coluna2
FROM (
    SELECT coluna_A, coluna_B
    FROM Tabela_Origem
) AS Tabela_Derivada
WHERE Tabela_Derivada.colunaA = 'algum_valor';
```

* A `Tabela_Derivada` é o alias para a subconsulta que seleciona `coluna_A` e `coluna_B` da `Tabela_Origem`.
* A consulta exterior então seleciona `coluna1` e `coluna2` da `Tabela_Derivada`, aplicando um filtro na `coluna_A`.




<br>

---

<br>

##  Documentação oficial da Microsoft



