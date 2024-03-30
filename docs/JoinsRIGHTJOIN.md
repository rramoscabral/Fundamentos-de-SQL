---
title: Layout
layout: RIGHT JOIN (ou RIGHT OUTER JOIN)
nav_order: 4.6
parent: 'Joins'
---


# RIGHT JOIN (ou RIGHT OUTER JOIN)
{: .no_toc }

Funciona de forma oposta ao LEFT JOIN; FULL JOIN (ou FULL OUTER JOIN) retorna linhas quando há uma correspondência em uma das tabelas.

### RIGHT INCLUSIVE:

**Sintaxe**

```sql
SELECT nome_coluna(s)
FROM tabelaA
RIGHT JOIN tabelaB
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE condition; 
```

### RIGHT EXCLUSIVE

**Sintaxe**

```sql
SELECT nome_coluna(s)
FROM tabelaA A
RIGHT JOIN tabelaB B
ON tabelaA.nome_coluna = tabelaB.nome_coluna
WHERE A.chave is NULL or B.chave is NULL
```

<br>