---
layout: default
title: Laboratório
nav_order: 11.6
parent: 'Expressões de consulta'
---

# Exercício 11 – Expressões de consulta
{: .no_toc }


<!-- Lab Scenario -->
## Cenário de laboratório

A equipa de produção da empresa AdventureWorks necessita de ter acesso a consultas de produção e inventário especificas e necessitam da sua ajuda para resolver esta situação. 

<!-- Objectives -->
## Objetivos

Depois de concluir este laboratório, você será capaz de:

* Criar e consultar uma View.
* Criar e consultar uma Derived Tables.
* Criar e consultar uma Common Table Expression (CTE).
* Criar e consultar uma Inline TVFs.

<!-- Lab Duration -->
## Duração do laboratório

* **Tempo estimado:** 40 minutos

<br>

## Tarefa 1 - Criar uma View com informação especifica dos dados de produção (20 minutos)

1. Utilize a base de dados AdventureWorks.


1. Consulte as tabelas **Product** e **ProductInventory** do esquema **Production** para familiarizar-se com o tipo de informação contidas nas suas colunas.



1. Crie uma consulta em que visualiza a identificação do produto, nome do produto, quantidade e localização do produto. 



1. Com a consulta anterior crie uma View denominada por Production.ProductLocation e consulte a mesma.


1. O mesmo produto pode estar em mais do que um lugar crie um View denominado por Production.ExcessInventory que agrupe os produtos e que mostre apenas produtos com mais de 1000 unidades e a sua quantidade independente da sua localização.



1. Apague as Views criadas.


<br/>


## Tarefa 2 - Expressões de tabela (20 minutos)


1. Crie uma função denominado por **Production.udf_ProductsLocation** de valor de tabela em linha ou Inline TVFs (Table-Valued Functions) em inglês, que indique os produtos existentes com base da localização.


1. Teste a função.


1. Crie uma tabela derivada com base da função **Production.udf_ProductsLocation**.


1. Crie um CTE com base da função **Production.udf_ProductsLocation**.



<br>
