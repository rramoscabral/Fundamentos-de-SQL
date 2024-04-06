---
title: FULL OUTER
layout: default
nav_order: 4.4
parent: 'Joins'
---



# FULL OUTER
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## FULL OUTER Join

O Full Outer Join combina as funcionalidades de ambos, devolve todos os registos quando há uma correspondência e preenchendo com NULL onde não há.

## FULL OUTER INCLUSIVE

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA
FULL OUTER JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE condition; 
```

## FULL OUTER EXCLUSIVE

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA
FULL OUTER JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE tabelaA.colunaA IS NULL OR tabelaB.colunaB IS NULL 
```

<br>