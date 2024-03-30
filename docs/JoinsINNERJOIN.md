---
title: Layout
layout: default
nav_order: 4.2
has_children: true
---



# INNER JOIN 
É o mais comum e retorna linhas quando há correspondência em ambas as tabelas.

**Sintaxe**

```sql
SELECT nome_coluna(s)
FROM tabelaA
INNER JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
```

<br>