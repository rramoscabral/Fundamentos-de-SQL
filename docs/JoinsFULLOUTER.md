---
title: FULL OUTER
layout: default
nav_order: 4.4
parent: 'Joins'
---



# FULL OUTER
{: .no_toc }

O Full Outer Join combina as funcionalidades de ambos, retorna todos os registros quando há uma correspondência e preenchendo com NULL onde não há.

## FULL OUTER INCLUSIVE

**Sintaxe**

```sql
SELECT nome_coluna(s)
FROM tabelaA
FULL OUTER JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE condition; 
```

## FULL OUTER EXCLUSIVE

**Sintaxe**

```sql
SELECT nome_coluna(s)
FROM tabelaA
FULL OUTER JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE tabelaA.colunaA IS NULL OR tabelaB.colunaB IS NULL 
```

<br>