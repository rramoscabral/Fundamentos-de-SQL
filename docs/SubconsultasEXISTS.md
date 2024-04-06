---
layout: default
title: Subconsultas com o predicado EXISTS
nav_order: 10.3
parent: 'Subconsultas'
---



# Subconsultas com o predicado EXISTS
{: .no_toc }


O predicado **`EXISTS`** é frequentemente utilizado para testar a existência de linhas numa subconsulta. 

* É verdadeiro se a subconsulta contém qualquer linha, o que significa que pode ser usado para verificar a existência de condições específicas nos dados. 
* É falso se a subconsulta não contém nenhuma linha.

<br>

**Sintaxe básica**

```sql
WHERE [NOT] EXISTS (subquery)
```

Após a palavra-chave **`EXISTS`**, coloca-se entre parênteses a subconsulta que se deseja avaliar. 

Permite ser utilizado em várias cláusulas do T-SQL, como **`WHERE`**, **`HAVING`** e até mesmo dentro de outra subconsulta, oferecendo uma flexibilidade considerável na construção de consultas complexas.

Ao utilizar o EXISTS, **é muito importante** que a subconsulta esteja corretamente indexada e otimizada para evitar problemas de desempenho. 

<br>

**Exemplo**

Pode-se querer saber se existem produtos que nunca foram encomendados para isso, pode-se utilizar uma subconsulta com **`EXISTS`** para verificar se há linhas na tabela de encomendas que correspondam a produtos específicos na tabela de produtos. 

<br>

**Atenção**

É importante frisar que o **`EXISTS`** é eficiente em termos de desempenho, pois a execução da subconsulta é interrompida assim que uma linha é encontrada, tornando-a mais rápida do que algumas alternativas que exigem a verificação de todas as linhas da subconsulta. 


<br>

**Sintaxe básica**

```sql
WHERE [NOT] EXISTS (subquery)
```


<br>

---

<br>

##  Documentação oficial da Microsoft

-[EXISTS (Transact-SQL)](https://learn.microsoft.com/en-us/sql/t-sql/language-elements/exists-transact-sql)

