---
title: Layout
layout: default
nav_order: 4.6
has_children: true
---


# RIGHT JOIN (ou RIGHT OUTER JOIN) 

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