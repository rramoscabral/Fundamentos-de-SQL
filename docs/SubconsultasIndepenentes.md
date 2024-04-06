---
layout: default
title: Subconsultas autocontidas
nav_order: 10.1
parent: 'Subconsultas'
---


# Subconsultas Indepenentes ou Autocontidas ou Subqueries Self-Contained
{: .no_toc }


Subconsultas indepenentes também conhecidas como subconsultas autocontidas ou Subqueries Self-Contained em inglês permite realizar consultas dentro de outras consultas. 


Estas subconsultass são executadas de forma independente da consulta externa e podem devolver um valor escalar, um conjunto de valores ou até mesmo um conjunto de tabelas.

<br>

**Exemplo**

Exemplos clássicos de uma subconsulta autocontida é quando se deseja comparar um valor de uma tabela com a média dos valores de outra tabela. 

Uma subconsulta autocontida pode ser utilizada para devoler todos os produtos que têm um preço superior à média dos preços dos produtos. Neste caso, uma subconsulta seria usada para calcular a média dos preços e depois essa média seria usada na consulta principal para filtrar os produtos desejados.


```sql
SELECT *
FROM Production.Product
WHERE ListPrice > (SELECT AVG(ListPrice) FROM Production.Product);
```


* Na cláusula `FROM`, uma subconsulta pode ser usada para definir uma tabela temporária sobre a qual a consulta externa irá operar. 

* Na cláusula `SELECT`, as subconsultas podem ser utilizadas para fornecer valores para as colunas da consulta principal.

**Em qualquer lugar**

É importante frisar que as subconsultas autocontidas possam ser utilizadas em qualquer lugar onde uma expressão é permitida, elas devem devolver um único valor quando utilizadas com operadores de comparação como **`=`**, **`<`** ou ** `>`**.

Além disso, as subconsultass autocontidas podem ser muito úteis em situações onde se deseja isolar a lógica de uma parte da consulta, tornando o código mais legível e fácil de manter. 

Por exemplo, se você tem uma consulta complexa que necessita de vários cálculos intermediários, pode-se utilizar subconsultas autocontidas para encapsular estes cálculos, simplificando a consulta principal.

**Uso excessivo de subconsultas**

É importante compreender que o uso excessivo de subconsultas pode afetar o desempenho da consulta. Portanto, é sempre recomendável avaliar se uma junção (**`JOIN`**) não seria mais apropriada para o caso em questão. Em alguns cenários, especialmente quando se verifica a existência de valores, uma junção pode oferecer melhor desempenho do que uma subconsulta.

Tem de garantir que as subconsultas estejam corretamente indexadas e que as colunas utilizadas nas condições de filtragem estejam otimizadas para pesquisas. Isso pode ser alcançado através da criação de índices apropriados nas tabelas envolvidas. A **otimização de subconsultas é um tópico avançado** e essencial para garantir a eficiência e o desempenho das consultas no SQL Server.


<br>

