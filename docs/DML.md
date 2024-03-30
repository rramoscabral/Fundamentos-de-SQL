---
layout: default
title: Linguagem de manipulação de dados
nav_order: 7
has_children: true
---


# Linguagem de manipulação de dados ou Data manipulation language (DML)
{: .no_toc }


A Linguagem de Manipulação de Dados (DML) é um componente essencial do Transact-SQL (T-SQL), que é a extensão proprietária da Microsoft para o SQL utilizada no Microsoft SQL Server e no Azure SQL Database. DML refere-se ao conjunto de linguagens utilizadas para realizar operações CRUD - Criar, Ler, Atualizar e Eliminar - em dados armazenados numa base de dados. No contexto do T-SQL, os comandos DML mais comuns incluem **SELECT**, para extrair dados de uma base de dados; **INSERT**, para inserir novos dados; **UPDATE**, para atualizar dados existentes; e **DELETE**, para eliminar dados.

Estes comandos são fundamentais para a gestão de dados e permitem que os utilizadores interajam com a base de dados de uma forma estruturada e controlada. Por exemplo, o comando **SELECT** pode ser utilizado não só para recuperar dados simples, mas também para executar operações mais complexas, como junções entre tabelas, agrupamentos e ordenações. O **INSERT**, por sua vez, é frequentemente acompanhado de cláusulas que especificam exatamente onde e como os novos dados devem ser inseridos na base de dados.

O **UPDATE** permite modificar os dados existentes, o que pode ser feito de forma seletiva através da especificação de condições que determinam quais as linhas a serem atualizadas. 

Já o **DELETE** é utilizado para remover dados de uma base de dados, e deve ser usado com cautela, pois a eliminação de dados pode ser irreversível se não houver um sistema de backup adequado.

Além destes, o T-SQL também suporta comandos adicionais de DML, como **MERGE**, que permite combinar operações de inserção, atualização e eliminação numa única instrução, otimizando assim as transações e a manutenção de dados. 

É importante notar que, ao trabalhar com DML no T-SQL, deve-se sempre considerar o impacto das operações nos dados e na performance da base de dados, bem como implementar práticas seguras de programação para proteger contra injeções SQL e outros tipos de vulnerabilidades de segurança.

Em resumo, a DML no T-SQL é uma ferramenta poderosa para a manipulação de dados, oferecendo aos desenvolvedores e administradores de bases de dados a capacidade de gerir eficientemente os dados e garantir a sua integridade e segurança. Ao compreender e utilizar corretamente os comandos DML, é possível realizar uma vasta gama de operações de dados, desde as mais simples às mais complexas, com precisão e eficácia.

<br>

---

<br>

##  Documentação oficial da Microsoft

- [Transact-SQL statements](https://learn.microsoft.com/en-us/sql/t-sql/statements/statements)

