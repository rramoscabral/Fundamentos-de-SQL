---
layout: default
title: Laboratório
nav_order: 13.8
parent: 'Funções de Janela ou Windows Functions'
---


# Exercício 13 – Funções de Janela ou Windows Functions
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório
É necessário efetuar analises de dados na base de dados da empresa AdventureWorks atraves de Windows Functions.


<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:

* Criar consultas com a cláusula OVER e PARTITION BY.
* Utilizar Funções Agregadas ou Aggregate Functions.
* Utilizar Funções de Classificação ou Ranking Functions.
* Utilizar Funções de Distribuição ou Distribution Functions.
* Utilizar Funções de deslocamento ou Offset Functions.


<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 30 minutos

<br>

## Tarefa 1 - Criar consultas com Windows Functions (30 minutos)

1. Crie uma consulta com a cláusula **OVER** para calcular a soma acumulativa das vendas para cada produto referente a tabela **Sales.SalesOrderDetail**.



1. Crie uma consulta para visualizar o pedido máximo, mínimo e número de pedidos por cada produto incluído na tabela **SalesOrderDetail**.



1. Crie uma consulta para visualizar a quantidade de produtos na tabela **SalesOrderDetail**, agrupe o ordene pelo produto de forma descendente. 



1. Baseado na consulta anterior aplique a função **RANK** para aplicar uma classificação de forma descendente e adicione uma nova coluna com a classificação. 



1. Escreva uma consulta que calcule a mediana (percentil 0.5) com a função **PERCENTILE_DISC** e **PERCENTILE_CONT** de todos os empregados da tabela **EmployeePayHistory**.



1. Escreva uma consulta que utilize a função **LAG** para visualizar o nome do produto anteriordenominado por **Previous_Value** e a função **LEAD** para visualizar o próximo segundo produto denominado por **Next_SecondValue** da tabela **Product**. 

<br>

[Back to top](#top) | [Back to all demos](./README.md)

<br/>

---

<br/>

