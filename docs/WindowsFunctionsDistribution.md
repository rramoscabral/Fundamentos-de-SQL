---
layout: default
title: Funções de Distribuição ou Distribution Functions
nav_order: 13.6
parent: 'Funções de Janela ou Windows Functions'
---


# Funções de Distribuição ou Distribution Functions
{: .no_toc }


Funções de Distribuição ou Distribution Functions em inglês, permitem calcular medidas de tendência central e dispersão, que são fundamentais para entender a distribuição dos dados. P


**Calcular média aritmética**

Funções que permitem Calcular média aritmética

* A função `AVG()` é utilizada para calcular a média aritmética de um conjunto de valores.
* A função `STDEV()` é usada para determinar o desvio padrão, que indica o quanto os valores de um conjunto de dados se afastam da média. 
* As funções `MIN()` e `MAX()` ajudam a identificar os valores mínimo e máximo de uma coluna.


**Funções analisticas**

A função `PERCENT_RANK` permite calcular a classificação percentual de uma linha dentro de um conjunto de linhas. Esta função devolve um valor flutuante maior que 0 e menor ou igual a 1, representando a posição relativa de um valor dentro de um conjunto de resultados de consulta ou partição. 

```sql
PERCENT_RANK() OVER ( [ partition_by_clause ] order_by_clause ) 
```
* A cláusula `partition_by_clause` é opcional e serve para dividir o conjunto de resultados em partições às quais a função é aplicada. 

<br>

A função `CUME_DIST` é uma função analítica que calcula a distribuição acumulada de um valor dentro de um grupo de valores. A função determina a posição relativa de um valor específico em relação ao conjunto de valores analisados

O `CUME_DIST` devolve um valor do tipo float que varia entre 0 (exclusivo) e 1 (inclusivo), representando a proporção acumulada do valor especificado. 

```sql
CUME_DIST() OVER (PARTITION BY <coluna> ORDER BY <coluna>)
```

* A cláusula `PARTITION BY` é opcional e serve para dividir o conjunto de resultados em partições distintas.
* A cláusula `ORDER BY` é obrigatória para definir a ordem dos valores dentro de cada partição. 

Um exemplo de utilização é se quisermos saber a posição percentual de um salário dentro de um departamento, a função `CUME_DIST` pode calcular a percentagem de funcionários que ganham menos ou o mesmo que um determinado valor



<br>

A função `PERCENTILE_CONT()` é uma função analítica que calcula o valor no percentil contínuo especificado da distribuição de um conjunto de valores.

Esta função permite calcular a mediana dividindo o conjunto de dados em duas partes.

Por exemplo pode-se utilizar esta função para efectuar o cálculo dos quartis.

* Primeiro quartil: `PERCENTILE_CONT(0.25)`.
* Segundo quartil: `PERCENTILE_CONT(0.50)`.
* Terceiro quartil: `PERCENTILE_CONT(0.75)`.
* Quarto quartil:  `PERCENTILE_CONT(1.00)`.



<br>


A função `PERCENTILE_DISC` permite calcular um percentil específico para valores ordenados num conjunto completo de linhas ou dentro de partições distintas de um conjunto de linhas. 

Para um `percentil X` função ordena os valores da expressão na cláusula `ORDER BY` e devolve o valor com a menor classificação `CUME_DIST` que é maior ou igual a `X`. 


Por exemplo, `PERCENTILE_DISC(0,5) `calculará o 50º percentil, ou seja, a mediana de uma expressão. Que permite determinar um valor de corte ou um limite específico dentro de um conjunto de dados. 

```sql
PERCENTILE_DISC (literal_numérico) WITHIN GROUP (ORDER BY expressão_de_ordenação [ASC | DESC]) OVER ([cláusula_partition_by])
``` 

A função ignora todos os valores nulos no conjunto de dados em que a função é não determinística, o que significa que os resultados podem variar cada vez que é executada, dependendo da ordem dos dados.

<br>


**Calcular variância**

A variância é o cálculo do raiz quadrada do desvio padrão para compreender o grau de variação dos dados em relação à média.

A função `VAR()` permite calcular a variância.

Quando se deseja comparar a dispersão de dois conjuntos de dados que possuem escalas diferentes, pode-se utilizar o coeficiente de variação, que é o desvio padrão dividido pela média.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [PERCENT_RANK (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/percent-rank-transact-sql)


