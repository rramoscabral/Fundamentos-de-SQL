---
title: LEFT JOIN (ou LEFT OUTER JOIN)
layout: default
nav_order: 4.5
parent: 'Joins'
---



# LEFT JOIN (ou LEFT OUTER JOIN)
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## LEFT JOIN (ou LEFT OUTER JOIN)

Devolve todas as linhas da tabela esquerda e as linhas correspondentes da tabela direita, ou NULL se não houver correspondência.

## LEFT INCLUSIVE

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA
LEFT JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE condition; 
```

## LEFT EXCLUSIVE

**Sintaxe básica**

```sql
SELECT nome_coluna(s)
FROM tabelaA A
LEFT JOIN  tabelaB B
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE A.chave is NULL or B.chave is NULL
```

<br>