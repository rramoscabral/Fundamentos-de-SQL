---
title: Funções conversão
layout: default
nav_order: 8.4
parent: 'Funções integradas no T-SQL'
---

# Funções conversão
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## CAST

Esta função existe no SQL padrão (ANSI SQL) e permite converter um tipo de dados de uma expressão para outro tipo de dados.

A função `CAST` é frequentemente utilizada em conjunto com outras funções de agregação, como `SUM` ou `AVG`, para garantir que o resultado seja do tipo de dados esperado.

É importante frisar que, ao utilizar a função CAST, **deve-se ter cuidado com a possibilidade de perda de informação**, especialmente quando se converte de um tipo de dados com maior precisão ou capacidade para um tipo com menor. Por exemplo, ao converter um número decimal para um inteiro, a parte fracionária do número será perdida. Da mesma forma, ao converter um texto longo para um tipo de dados de texto com um limite de caracteres menor, o texto pode ser truncado.


A função CAST também suporta a conversão de tipos de dados como `xml`, `bigint` e `sql_variant`.

**Sintaxe básica**

```sql
CAST([expressão] AS [tipo_de_dados(comprimento)])
```
- O argumento `tipo_de_dados` é o tipo para o qual se deseja converter.
- O argumento `comprimento` é um número inteiro opcional que especifica o comprimento do tipo de dados de destinor. O valor por defeito é 30.


<br>  

**Exemplo**

```sql
SELECT CAST(10.58 AS int); 
-- Resultado: 10
-- Aqui há uma perda de informação.

SELECT CAST(10.58 AS float); 
-- Resultado: 10.58

SELECT CAST(10.58 AS money); 
-- Resultado: 10.58

SELECT CAST('2024-31-01' AS datetime); 
-- Resultado: The conversion of a varchar data type to a datetime data type resulted in an out-of-range value.

SELECT CAST('2024-01-31' AS datetime); 
-- Resultado: 2024-01-31 00:00:00.000
```

## CONVERT

Esta função é proprietária da Microsoft para o Microsoft SQL Server. O `CONVERT` permite a conversão de um tipo de dados para outro e aceita um parâmetro de estilo opcional usado para formatação.


O seguinte diagrama mostra tabela das possíveis conversões de tipos de dados.

![Tabela das possíveis conversões de tipos de dados](https://learn.microsoft.com/en-us/sql/t-sql/data-types/media/cast-and-convert-transact-sql/data-type-conversions.png)

> Fonte da ilustração: Microsoft

É recomendado que utilize o `CAST` em vez do `CONVERT`.

<br>

**Sintaxe básica**

```sql
CAST([tipo_de_dados(comprimento)], [expressão],[estilo])
```

- O argumento `tipo_de_dados` é o tipo para o qual se deseja converter.
- O argumento `estilo` é um argumento opcional que determina o formato da conversão.

<br>  

**Exemplo**

```sql
SELECT CONVERT(int, 10.58); 
-- Resultado: 10

SELECT CONVERT(float, 10.58); 
-- Resultado: 10.58

SELECT CONVERT(money, 10.58); 
-- Resultado: 10.58

SELECT CONVERT(datetime, '2024-31-01'); 
-- Resultado: The conversion of a varchar data type to a datetime data type resulted in an out-of-range value.

SELECT CONVERT(datetime, '2024-01-31'); 
-- Resultado: 2024-01-31 00:00:00.000
```

**Estilos de conversão**

Consulte as tabelas de conversão na documentação oficial [aqui](https://learn.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql#date-and-time-styles).

```sql
select convert(varchar, getdate(), 0) 
-- Resultado: Apr  1 2024  2:03PM

select convert(varchar, getdate(), 1) 
-- Resultado: 03/21/24

select convert(varchar, '2024-01-31', 3) 
-- Resultado: 2024-01-31
```

## TRY_CONVERT

A função TRY_CONVERT no T-SQL **oferece uma camada extra de segurança** ao converter tipos de dados. 

Esta função tenta converter um valor para um tipo de dados especificado e, se a conversão for bem-sucedida, devolve o valor convertido. 

Caso contrário, se a conversão não for possível, `TRY_CONVERT` devolve um valor nulo, evitando assim os erros que normalmente resultariam de uma conversão de tipo falhada. 

<br>

**Sintaxe básica**

```sql
TRY_CONVERT([tipo_de_dados], [expressão], [estilo])
```
- O argumento `tipo_de_dados` é o tipo para o qual se deseja converter.
- O argumento `estilo` é um argumento opcional que determina o formato da conversão.

<br>
  
**Exemplo** 

Se a string estiver num formato reconhecível, a função devolve a data correspondente. Se não, devolve nulo. 

```sql
SELECT TRY_CONVERT(datetime, '31/01/2024')
--- Resultado: NULL.

SELECT TRY_CONVERT(datetime, '2024-01-31')
--- 2024-01-31 00:00:00.000
```

Este comportamento é particularmente útil em cenários onde os dados de entrada podem não ser consistentes ou totalmente confiáveis, e onde uma conversão falhada não deve interromper a execução de um procedimento ou script.

Por exemplo, ao trabalhar com uma coluna que contém tanto números como texto, TRY_CONVERT pode ser usado para separar os valores numéricos dos não numéricos sem causar erros. 

## PARSE

A função PARSE permite converter uma string num tipo de dados específico, baseando-se numa cultura (locale) específica. 

Esta função é particularmente útil quando se trabalha com dados que foram formatados em diferentes culturas.


**Sintaxe básica**

```sql
PARSE (string_value AS data_type [USING culture]
```

- O argumento `string_value` é o valor que se pretende analisar.
- O `data_type` especifica o tipo de dados para o qual a conversão é desejada. 
- O argumento `culture` é opcional e define a cultura que deve ser considerada na análise da string. Se não for especificado, a função utiliza a cultura da sessão atual do SQL Server.


**É importante frisar que a função `PARSE` só deve ser utilizada para conversões de strings para tipos de dados de data/hora e números, e não para conversões gerais de tipos de dados**. 

**Para conversões mais gerais, deve-se continuar a usar as funções CAST ou CONVERT.** 

A função PARSE depende da presença do .NET Framework Common Language Runtime (CLR), o que significa que não será remota, pois depende da presença do CLR no servidor onde é executada.

**Exemplo** 

Converter uma string que representa um valor monetário formatado em euros, utilizando a cultura portuguesa, para o tipo de dados `money`.

```sql
SELECT PARSE('€398,21' AS money USING 'pt-PT') AS Resultado;
--- Resultado: 398.21
```

## TRY_PARSE

**Sintaxe básica**

```sql
```
TRY_PARSE é uma função que permite converter uma string num tipo de dados numérico ou de data/hora. 

Ao contrário da função `PARSE`, `TRY_PARSE` devolve um valor nulo se a conversão não for possível, evitando assim erros que interromperiam a execução do código.

Esta função é particularmente útil quando se trabalha com dados que foram inseridos manualmente e podem conter erros ou formatos inconsistentes. 

**Sintaxe básica**

```sql
TRY_PARSE (string AS tipo_usando cultura)
```
- O argumento `string` é a expressão a ser convertida. - O argumento `tipo` é o tipo de dados desejado. 
- O argumento `cultura` refere-se ao idioma e convenções regionais que influenciam a conversão.


**Exemplo** 

```sql
SELECT TRY_PARSE('31-01-2024' AS DATE USING 'pt-PT')
--- Resultado: 2024-01-31
```


<br>

---

<br>

##  Documentação oficial da Microsoft

- [CAST and CONVERT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql)
- [TRY_CONVERT (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/try-convert-transact-sql)
- [PARSE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/parse-transact-sql)
- [TRY_PARSE (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/functions/try-parse-transact-sql)