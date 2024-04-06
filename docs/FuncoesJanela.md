---
title: Funções de janela ou Windows Functions 
layout: default
nav_order: 8.3
parent: 'Funções integradas no T-SQL'
---



# Funções de janela ou Windows Functions
{: .no_toc }


As funções de janela ou Windows Functions em T-SQL são uma característica poderosa da linguagem SQL que permitem realizar cálculos complexos sobre um conjunto de linhas de uma tabela enquanto ainda mantêm o acesso às linhas individuais. 


* A função **ROW_NUMBER()**, pode-se atribuir um número sequencial a cada linha de um conjunto de resultados, o que é particularmente útil para tarefas como paginação de resultados.

* As funções **RANK()**, **DENSE_RANK()** e **NTILE()**, ajudam a classificar dados dentro de um conjunto de resultados sem alterar a estrutura da tabela.

As funções de janela podem ser utilizadas para realizar cálculos agregados, como a soma ou a média, sem agrupar o resultado com **GROUP BY**, permitindo manter a granularidade dos dados. 

A cláusula **OVER** é o que define a 'janela' sobre a qual a função opera, podendo incluir partições para dividir o conjunto de dados em segmentos menores para cálculos independentes.

É importante frisar que funções de janela sejam extremamente úteis, elas podem ser complexas e requernum entendimento claro de como e quando as utilizar para evitar resultados inesperados ou desempenho. Por isso, é recomendável praticar com exemplos reais e consultar documentação específica para garantir a correta aplicação dessas funções nas suas consultas SQL.
<br>

---

<br>

## Documentação oficial da Microsoft

- [Deterministic and Nondeterministic Functions](https://learn.microsoft.com/en-us/sql/relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions)