---
layout: default
title: Agrupar dados
nav_order: 9
has_children: true
---



# Agrupar dados
{: .no_toc }

Agrupar dados em T-SQL é uma tarefa fundamental para a análise e relatório de informações armazenadas em bases de dados SQL Server. 

A cláusula **GROUP BY** é utilizada para organizar dados em grupos baseados numa ou mais colunas, permitindo realizar operações de agregação, como somas, médias, contagens, entre outras. Por exemplo, se quisermos calcular a média de vendas diárias.


A cláusula **HAVING** funciona como um **WHERE** após o agrupamento, permitindo filtrar grupos baseados em condições de agregação. 


É importante frisar que todas as colunas selecionadas que não estão dentro de funções de agregação devem estar presentes na cláusula **GROUP BY**. 


O T-SQL permite o uso de funções de janela ou WINDOW, como **ROW_NUMBER()**, **RANK()**, e **DENSE_RANK()**, que podem ser utilizadas para criar rankings ou numerações dentro de cada grupo sem alterar a estrutura do agrupamento.

Estas são apenas algumas das possibilidades que o T-SQL oferece para o agrupamento de dados, e a escolha da abordagem correta dependerá sempre do contexto específico e dos requisitos da análise a ser realizada.


