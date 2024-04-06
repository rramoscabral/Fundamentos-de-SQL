---
layout: default
title: Operador UNPIVOT
nav_order: 14.2
parent: 'Pivoting'
---


# Operador UNPIVOT
{: .no_toc }

O operador **`UNPIVOT`** é a operação inversa do operador **`PIVOT**`.
* O PIVOT transforma valores de linhas em colunas.
* O UNPIVOT faz o contrário, transforma colunas em linhas.

**ATENÇÃO:** O **UNPIVOT** não restaura os dados originais. Os dados originais foram perdidos durante o processo de agregação.

<br>

**Sintaxe básica**

```sql
SELECT [Coluna_1], [Coluna_2]
FROM (
	SELECT <lista_de_colunas>> FROM <Tabela_Pivoted>                                          
)
UNPIVOT ( <valor_da_coluna> FOR <nome_da_coluna> IN ( <<lista_de_colunas> ) )
<cláusula_opcional WHERE>
<cláusula_opcional ORDER BY>
```

<br>

**Exemplo**

Este exemple é a continua do exemplo referente ao PIVOT.

O `UNPIVOT` pode ser útil para normalizar dados que foram previamente pivotados ou para preparar dados para operações que requerem um formato de linha.

```sql
SELECT *
FROM 
(
  -- Consulta PIVOT
  SELECT *
	FROM
	(
		SELECT SalesPersonID, Year, TotalSales
		FROM #TempSales
	) AS SourceTable
	PIVOT
	(
		SUM(TotalSales)
		FOR Year IN ([2022], [2024])
	) AS PivotTable
) as Tabela_Pivot
UNPIVOT
(
  TotalSales
  FOR Year IN ([2022], [2024])
) as Tabela_UNPivot;
```

<br>

---

<br>

##  Documentação oficial da Microsoft

- [FROM - Using PIVOT and UNPIVOT](https://learn.microsoft.com/en-us/sql/t-sql/queries/from-using-pivot-and-unpivot)
- [FROM clause plus JOIN, APPLY, PIVOT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/from-transact-sql)




