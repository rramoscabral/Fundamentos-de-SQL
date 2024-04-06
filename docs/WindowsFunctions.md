---
layout: default
title: Funções de Janela ou Windows Functions
nav_order: 13
has_children: true
---


# Funções de Janela ou Windows Functions
{: .no_toc }


## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Funções de Janela ou Windows Functions

Funções de Janela ou Windows Functions em inglês, permite realizar cálculos complexos sobre um conjunto de linhas relacionadas com a linha atual.

Estas funções são particularmente úteis para tarefas de análise de dados, como cálculos cumulativos, médias móveis, e rankings. 


Este tipo de funções oferecem uma maneira eficiente de trabalhar com grandes volumes de dados, mantendo a clareza do código e a eficiência da execução.

Exemplos de funções:

* A função `ROW_NUMBER()` atribui um número sequencial a cada linha dentro de uma partição de um conjunto de resultados, o que é ideal para criar rankings ou numerações automáticas. 

* A função `RANK()` fornece um ranking dentro de uma partição, com linhas iguais recebendo o mesmo rank e deixando espaços ou falhas nos números de rank subsequentes.

* A função `DENSE_RANK()` é semelhante ao `RANK` mas não deixa espaços ou falhas no ranking, mesmo entre linhas iguais.

* As funções `LEAD()` e `LAG()`, permitem olhar para frente ou para trás no conjunto de dados, respectivamente, o que é extremamente útil para comparar valores em linhas consecutivas. 


* A função `SUM()` pode ser utilizada com a cláusula `OVER()` para realizar somas acumulativas, permitindo aos utilizadores ver a soma total até a linha atual.

<br>

**Cuidados**

Todas estas funções, deve-se ter cuidado com a especificação das partições e ordens, pois vai afetar diretamente o resultado dos cálculos

Ao aplicar grandes conjuntos de dados sem uma indexação adequada vai afetar o desepenho da operação.


## cláusula WINDOW

Permite definir uma série de funções de janela para serem usadas em consultas SQL.

Esta cláusula é particularmente útil quando se trabalha com conjuntos de dados grandes, pois permite especificar uma ordem e particionamento de dados para cálculos complexos em subconjuntos de dados.


## Componentes da cláusula WINDOW

Os componentes desta cláusula incluem:

* O Result set (ORDER BY), que define a ordem lógica das linhas dentro de cada partição do conjunto de resultados.

* O Windows partition (PARTITION BY), que divide o conjunto de resultados da consulta em partições.

* A Frame (ROWS/RANGE, ROWS BETWEEN) que limita as linhas dentro da partição especificando pontos de início e fim dentro da partição.


<br>

##  Documentação oficial da Microsoft

[SELECT - WINDOW - (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-window-transact-sql)
