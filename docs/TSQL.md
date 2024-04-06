---
layout: default
title: T-SQL
nav_order: 2
has_children: true
---


# T-SQL
{: .no_toc }


T-SQL, ou Transact-SQL adiciona uma série de funcionalidades ao padrão ANSI/ISO. 

* Vistas ou Views, são consultas armazenadas que apresentam dados de uma ou mais tabelas de maneira lógica e consistente, sem necessidade de armazenar fisicamente os dados.

* Índices ou Indexes, ajudam a melhorar a velocidade das consultas, criando uma estrutura de dados que permite acesso rápido a linhas específicas de uma tabela. 

* Operadores lógicos e aritméticos.

* Cláusulas como JOIN para combinar registos de duas ou mais tabelas

* Funções de agregação como SUM, COUNT, AVG, MAX e MIN, que permitem realizar cálculos em conjuntos de dados.

* Manipulação de datas e horas, strings e dados binários.

* Mecanismos para tratamento de erros e exceções.

* As transações são sequências de operações realizadas como uma única unidade de trabalho, garantindo a integridade dos dados mesmo em caso de falhas ou erros.

* Procdimentos ou Storage procedure, que é uma coleção de instruções SQL que realizam uma tarefa específica e é armazenado no servidor de base de dados. 

* Funções, que são semelhantes aos procedimentos armazenados, mas podem devolver um valor e ser utilizado em consultas SQL. 

* Gatilhos ou triggers, permite ser executado automaticamente em resposta a eventos específicos na base de dados, como inserções, atualizações ou exclusões.


Ao escrever em T-SQL, é importante manter as boas práticas de programação, como a utilização de comentários para explicar a lógica do código, a escrita de código claro e legível, e a otimização de consultas para melhor performance. 

```sql
--- Isto é um comentário
--- :) 

/*
Isto 
é 
um
bloo
de
comentários.
*/
```

A segurança dos dados também é um aspecto crucial, devendo-se sempre considerar a implementação de medidas como controle de acesso e encriptação.



<br>

---

<br>

##  Documentação oficial da Microsoft

- [Transact-SQL reference (Database Engine)](https://learn.microsoft.com/en-us/sql/t-sql/language-reference)


