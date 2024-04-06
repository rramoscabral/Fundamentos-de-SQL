---
layout: default
title: Operador PIVOT
nav_order: 14.1
parent: 'Pivoting'
---


# Operador PIVOT
{: .no_toc }


O operador **`PIVOT`** permite transformar dados de linhas em colunas, facilitando a análise e a visualização de informações. 

Este operador é particularmente útil quando se trabalha com grandes volumes de dados e necessita-se de uma representação que destaque tendências ou padrões. 


<br>

**Sintaxe básica**

A sintaxe básica do PIVOT envolve a especificação da coluna que contém os valores que se deseja rotacionar para o cabeçalho da tabela, bem como a função de agregação que será aplicada.

```sql
SELECT <coluna_não_dinâmic> AS <nome_da_coluna>,  
FROM  
    (<SELECT <consuta_que_produz_os_dados>) AS <alias_para_a_consulta_de_origem>  
PIVOT  
(  
    <função_de_agregação>(<oluna_que_vai_ser_agregada>)  
FOR   
[<colunas_que_contém_os_valores_que_vai_ser_transformado_em_cabeçalhos_das_colunas>]   
    IN ( [A_primeira_coluna_para_pivoted], ... [Ulitmacoluna_para_pivoted])  
) AS <alias_para_a_tabela_transformada>  
<cláusula_opcional ORDER BY>;
```

* A utilização do `PIVOT` inicia-se com a seleção das colunas que não serão transformadas em linhas.
* Tem de especificar as colunas transformadas e a função de agregação. 
* A cláusula `FOR` no `PIVOT` define a coluna que contém os valores que se tornarão os cabeçalhos das colunas transformadas. 
* O PIVOT **requer** uma função de agregação porque, ao transformar linhas em colunas, pode haver múltiplos valores que correspondem a uma única célula transformada. 
* A função de agregação garante que um único valor é devolvido, dependente se é uma soma, média, máximo, ou qualquer outra função agregada.



**Exemplo**

O seguinte exemplo vai demostrar as vendas totais de cada vendedor nos anos 2019 e 2020 em colunas separadas.

```sql
-- Cria uma tabela temporária denominada por '#TempSales'.
CREATE TABLE #TempSales
(
    SalesPersonID INT,
    Year INT,
    TotalSales DECIMAL(18, 2)
);

-- Os dados de exemplo vão ser inseridos na temporária '#TempSales'.
INSERT INTO #TempSales (SalesPersonID, Year, TotalSales)
VALUES
    (1, 2024, 9100),
    (1, 2023, 7500),
    (1, 2022, 1000),
    (2, 2023, 5000),
    (2, 2022, 3000);

-- É utilizado a operador PIVOT para transformar as linhas em colunas e agrupar as vendas totais por ano e vendedor.
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
) AS PivotTable;

-- Elimina a temporária '#TempSales'.
DROP TABLE #TempSales;
```

Também podemos aplicar uma função de agregação `SUN` para calcular o total de vendas por ano.

**Cuidados em trabalhar com PIVOT**

É importante frisar que o PIVOT pode ser dinâmico, o que significa que as colunas transformadas podem ser determinadas em tempo de execução. Isto é útil quando não se sabe antecipadamente quais valores únicos uma coluna pode ter. 

Para criar um PIVOT dinâmico, geralmente utiliza-se uma combinação de instruções SQL para construir uma string que contém a consulta PIVOT e a seguir executa-se essa consulta dinamicamente com o comando `EXECUTE`.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [FROM - Using PIVOT and UNPIVOT](https://learn.microsoft.com/en-us/sql/t-sql/queries/from-using-pivot-and-unpivot)
- [FROM clause plus JOIN, APPLY, PIVOT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/queries/from-transact-sql)

