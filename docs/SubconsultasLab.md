---
layout: default
title: Laboratório
nav_order: 10.4
parent: 'Subconsultas'
---

# Exercício 10 – Subconsultas
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório

Na empresa AdventureWorks é necessário consultar empregados com o nome do meio **R.** sem alterar nenhuma informação na base de dados. 

<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:

* Escrevendo subconsultas.
* Utilizar o predicado EXISTS com subconsultas.


<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 30 minutos


<br>

## Tarefa 1 - Consultar os empregados com subconsultas.


1. Utilize a base de dados AdventureWorks.

1. Liste todos as pessoas da tabela **Person** no esquema **Person**.

1. Liste todas as pessoas e utilize uma subconsulta independente ou subqueries self-contained em inglês que mostre todos as pessoas mesmo que contenha algum valor desconhecido (NULL) e ordene os resultados pelo primeiro nome por ordem ascendente.


1. Rescreva a consulta anterior para pesquisar apenas empregados da tabela **Employee** no esquema **HumanResources** em que nome do meio seja **R.**.


1. Liste todos o histórico de pagamentos efetuados da tabela **EmployeePayHistory** no esquema **HumanResources**.


1. Ordene o menor pagamento efetuado da tabela **EmployeePayHistory** agrupado pela a identificação e rate.

1. Adapte as consultas anteriores para visualizar os em que nome do meio seja **R.** e o menor valor recebido.

