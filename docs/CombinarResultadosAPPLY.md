---
layout: default
title: Operador APPLY
nav_order: 12.5
parent: 'Manipular e combinar conjuntos de resultados'
---


# Operador APPLY
{: .no_toc }


O operador `APPLY` permite consultar uma relação entre duas tabelas.

<br>

**Sintaxe básica**

```sql
FROM <Tabela_A> AS <alias>
[CROSS]|[OUTER] APPLY 
    <Tabela_B> AS <alias>;
```

Existem duas variantes do operador 
* `CROSS APPLY` devolve apenas as linhas da expressão de tabela externa que produzem um conjunto de resultados não vazio após a aplicação da função de valor de tabela. 

* O `OUTER APPLY` devolve todas as linhas da expressão de tabela externa, mesmo que a aplicação da função de valor de tabela resulte num conjunto de resultados vazio, preenchendo as colunas da função com valores NULL. 

<br>



