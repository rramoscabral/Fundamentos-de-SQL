---
layout: default
title: SELECT Statement
nav_order: 3.1
parent: 'Linguagem de Consulta de dados'
---


# SELECT Statement
{: .no_toc }

A instrução SELECT é uma das mais importantes em T-SQL, permitindo a recuperação de dados das bases de dados. 


Selecionar todas as colunas numa tabela.

```sql
SELECT * 
FROM [esquema].[tabela] 
WHERE condição;
```


Selecionar colunas especificas numa tabela.

```sql
SELECT coluna1, coluna2 
FROM [esquema].[tabela] 
WHERE condição;
```

<br>

**Sintaxe básica** 

```sql
SELECT coluna1, coluna2 
FROM [esquema].[tabela] 
WHERE condição
GROUP BY lista
ORDER BY ordenação
```

<br>

**Outras cláusulas**

O JOIN permitem combinar dados de múltiplas tabelas.
O ORDER BY organiza os resultados segundo um critério específico. 

É importante também estar ciente das diferenças entre o T-SQL utilizado no SQL Server e outras variantes do SQL, pois existem particularidades que podem afetar a execução dos comandos.

Ao escrever consultas em T-SQL, é recomendável fazer uso de boas práticas, como evitar a seleção desnecessária de todas as colunas, o que pode impactar o desempenho, e garantir que as condições WHERE sejam claras e eficientes para obter os resultados desejados. 
Lembre-se de testar as consultas num **ambiente seguro** antes de aplicá-las num contexto de produção, para assegurar que funcionam conforme esperado e não causam efeitos indesejados.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [SELECT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-transact-sql)
