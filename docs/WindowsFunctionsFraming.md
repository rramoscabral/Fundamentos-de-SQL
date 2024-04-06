---
layout: default
title: Windows Framing 
nav_order: 13.3
parent: 'Funções de Janela ou Windows Functions'
---



# Windows Framing 
{: .no_toc }


Windows Framing em inglês, é a definição de uma janela de linhas numa consulta SQL onde uma função de agregação pode ser aplicada.

A cláusula de `framing` especifica exatamente quais linhas dentro da partição devem ser consideradas para cada cálculo de agregação. 


O framing é particularmente útil quando temos dados empatados, ou seja, linhas com o mesmo valor na coluna de ordenação. Sem especificar o tipo de framing, o SQL Server usa por padrão `RANGE BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW`, o que pode não ser o comportamento desejado. 

<br>

**Exemplo**

Se se tivermos várias linhas com o mesmo valor de `mês do pedido`, todas essas linhas seriam incluídas na janela de agregação, o que poderia levar a resultados inesperados. Ao especificar `ROWS`, garantimos que apenas as linhas fisicamente anteriores à linha atual sejam incluídas, evitando assim a agregação de linhas com valores idênticos de `mês do pedido`.

Além disso, o uso explícito de `ROWS` pode melhorar o desempenho da consulta, pois o comportamento padrão `RANGE` pode exigir o uso de um buffer em disco, o que é mais exigente em termos de recursos. 

É muito importante frisar que ao escrever consultas T-SQL que utilizam funções de janela, é importante considerar cuidadosamente se o framing padrão corresponde às necessidades da consulta ou se um framing específico `ROWS` ou `RANGE` deve ser utilizado para obter os resultados corretos e otimizar o desempenho. 


<br>




