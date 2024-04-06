---
layout: default
title: Funções de Classificação ou Ranking Functions
nav_order: 13.5
parent: 'Funções de Janela ou Windows Functions'
---


# Funções de Classificação ou Ranking Functions
{: .no_toc }

As Funções de Classificação ou Ranking Functions em inglês, permitem organizar conjuntos de dados com base numa ordem específica e atribuir uma classificação a cada linha dentro de uma partição de dados.


No T-SQL, existem quatro funções principais de classificação (ranking): 


| Função | Descrição |
| --- | --- | 
| ROW_NUMBER()  | Atribui um número sequencial único a cada linha, começando do um, de acordo com a ordem especificada na cláusula `OVER()`. |
| RANK()       | Atribui um número de classificação a cada linha dentro de uma partição, com linhas de mesmo valor recebendo o mesma classificação e o número de classificação seguinte sendo incrementado com base no total de linhas com o mesmo valor. |
| DENSE_RANK()  | É semelhante ao `RANK()`, mas não há incremento nos números de classificação entre linhas com o mesmo valor. |
| NTILE()       | É utilizado para distribuir as linhas de uma partição num número definido de grupos com aproximadamente o mesmo número de linhas. |


<br>

**Exemplo `ROW_NUMBER()`**

Se quisermos atribuir um número de linha a cada venda numa tabela de vendas, ordenando-as pelo valor da venda em ordem decrescente.

```sql
ROW_NUMBER() OVER(ORDER BY ValorVenda DESC)
```


**Exemplo `RANK()`**

Se duas vendas têm o mesmo valor, ambas receberão a mesma classificação (rank), e a próxima venda com um valor diferente receberá uma classificação que considera as duas vendas anteriores.


**Exemplo `DENSE_RANK()`**

Se duas vendas partilham o mesmo valor, a próxima venda com um valor diferente receberá o próximo número de classificação sequencial, sem saltos.

**Exemplo `NTILE()`**
 
Se quisermos dividir uma lista de notas de alunos por quartis (é um valor de uma unidade estatística divida por quatro partes iguais, ou seja, cada parte representa 1/4) a função seria `NTILE(4)`.

<br>

**Como utilizar funções de classificação**

É importante frisar que todas essas funções dependem da cláusula `OVER()` para definir a ordem e a partição dos dados. 

As funções de classificação são não determinísticas, o que significa que, se a ordem não for única, os resultados podem variar a cada execução da consulta.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Ranking Functions (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/ranking-functions-transact-sql)
- [RANK (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/rank-transact-sql)
- [DENSE_RANK (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/dense-rank-transact-sql)
- [ROW_NUMBER (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/row-number-transact-sql)
- [NTILE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/ntile-transact-sql)




