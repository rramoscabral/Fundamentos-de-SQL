---
layout: default
title: Manipular e combinar conjuntos de resultados
nav_order: 12
has_children: true
---


# Manipular e combinar conjuntos de resultados
{: .no_toc }

Os Joins em T-SQL permite combinar dados de diferentes tabelas numa base de dados do Microsoft SQL Server, mas existem vários operadores que também permitem manipular e combinar conjuntos de resultados de diferentes maneiras.

* O operador `UNION` é utilizado para combinar os resultados de dois ou mais comandos `SELECT` num único conjunto de resultados, eliminando duplicados.

* O operador `UNION ALL` faz o mesmo, mas inclui todas as duplicados, sendo geralmente mais rápido por não realizar a etapa adicional de eliminação de duplicados. 

* O operador `CROSS APPLY` e o `OUTER APPLY` são operadores que se assemelham aos `JOINs`, mas são utilizados especificamente para combinar uma tabela com o resultado de uma função de valor de tabela ou Table Valued Function (TVF) em inglês.

* O operador `CROSS APPLY` funciona de forma semelhante ao `INNER JOIN`, devolvido apenas as linhas correspondentes entre a tabela e o Table Valued Function (TVF).

* O operador `OUTER APPLY` é similar ao `LEFT JOIN`, devolvido todas as linhas da tabela, mesmo que não haja correspondência com o Table Valued Function (TVF).


* O operador `EXCEPT` devolve todas as linhas de um conjunto de resultados que não estão presentes no segundo conjunto de resultados, efetivamente subtraindo um conjunto do outro.


* O Operador `INTERSECT` devolve apenas as linhas que são comuns a ambos os conjuntos de resultados, funcionando como uma interseção matemática entre eles.

Cada um desses operadores tem suas particularidades e casos de uso específicos. Por exemplo 

## Operadores SET

Os operador SET são comandos especiais que permitem modificar o ambiente de execução de uma sessão ou os valores de variáveis de sistema.

<br>

**Sintaxe básica**

```sql
<SELECT consulta_1>
<operador_set>
<SELECT consulta_2>
[ORDER BY <lista_de_ordenação>];
```

Por exemplo o operador `UNION` é um operador SET que interage com duas consultas. 




<br>



