---
layout: default
title: Funções de deslocamento ou Offset Functions
nav_order: 13.7
parent: 'Funções de Janela ou Windows Functions'
---


# Funções de deslocamento ou Offset Functions
{: .no_toc }

As Funções de deslocamento ou Offset Functions em inglês, permitem realizar cálculos complexos sobre um conjunto de linhas relacionadas a uma linha atual.

Estas funções podem ser utilizadas para análises financeiras, estatísticas ou comparação sequencial.

* Função `LAG` permite aceder a dados de uma linha anterior sem a necessidade de um auto-join. O valor é desconhecido se não existir nenhuma posição anterior.

* A função `LEAD`permite aceder aos dados da seguinte linha. O valor é desconhecido se não existir nenhuma posição subsequente.

* A função `FIRST_VALUE`permite aceder ao primeiro valor e requer que os dados estejam ordenados.

* A função `LAST_VALUE` permite aceder ao ultimo valor e requer que os dados estejam ordenados.



<br>

---

<br>

##  Documentação oficial da Microsoft

- [ROW_NUMBER (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/row-number-transact-sql?view=sql-server-ver16)


