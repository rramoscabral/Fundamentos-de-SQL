---
layout: default
title: Laboratório
nav_order: 12.8
parent: 'Manipular e combinar conjuntos de resultados'
---

# Exercício 12 – Manipular e combinar conjuntos de resultados
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório

A empresa AdventureWorks voltou novamente a solicitar a sua ajuda para combinar dados em diferentes tabelas, mas sem a utilização de JOINS.

<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:

* Criar consultas com o operador UNION e UNION ALL**.
* Criar consultas com o operador INTERSECT`.
* Criar consultas com o operador EXCEPT.
* Criar consultas com o operador CROSS APPLY  e OUTER APPLY.


<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 30 minutos

<br>

## Tarefa 1 - Realizar operações de consulta entre tabelas sem Joins (30 minutos)

1. Utilize o operador **UNION** para consultar a identificação do produto, nome e número de produto da tabela **Product** filtrado pela identificação do produto entre 330 a 340 e 430 a 440.


1. Selecione todos **ProductID** e **UnitPrice** da tabela **SalesOrderDetail** que são comuns com a tabela **Product**.


1. Utilizado a mesma consulta anterior consulte apenas os produtos que foram vendidos com o preço igual em ambas as tabelas. 


1. Utilizando o operador **OUTER APPLY** consulte todos os clientes que nunca realizaram uma venda.


1. Utilizando o operador **CROSS APPLY** consulte os maiores cinco clientes com base no valor a pagamento por cada cliente da tabela **SalesOrderHeader**.


<br>