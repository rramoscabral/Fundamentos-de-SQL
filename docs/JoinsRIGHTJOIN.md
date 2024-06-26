---
title: RIGHT JOIN (ou RIGHT OUTER JOIN)
layout: default
nav_order: 4.6
parent: 'Joins'
---


# RIGHT JOIN (ou RIGHT OUTER JOIN)
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## RIGHT JOIN (ou RIGHT OUTER JOIN)

Funciona de forma oposta ao LEFT JOIN; FULL JOIN (ou FULL OUTER JOIN) devolve linhas quando há uma correspondência numa das tabelas.

## RIGHT INCLUSIVE:

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA
RIGHT JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE condition; 
```

## RIGHT EXCLUSIVE

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA A
RIGHT JOIN tabelaB B
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE A.chave is NULL or B.chave is NULL
```

<br>