---
title: INNER JOIN 
layout: default
nav_order: 4.2
parent: 'Joins'
---



# INNER JOIN
{: .no_toc }

É o mais comum e devolve linhas quando há correspondência em ambas as tabelas.

<br>

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA
INNER JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
```

<br>