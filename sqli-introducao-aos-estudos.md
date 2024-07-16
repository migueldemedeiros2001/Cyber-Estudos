---
description: Aprendendo como usar o Sql Injection para invasão de sites de forma manual.
---

# SQLi Introdução aos estudos

SQLi

Quando eu quiser quebrar uma query eu posso usar ' na URL do site alvo, como exemplo:



<mark style="color:purple;">SELECT \* FROM products WHERE category = 'Gifts' AND released = 1</mark>

<mark style="color:red;">^ esse seria para quebrar a query, e então daria erro no site. Porém, se eu colocar '' (duas aspas), o site vai interpretar de forma diferente, como se eu tivesse "arrumado" a query, e então eu saberia que existe forma de invadir com SQL.</mark>

<mark style="color:purple;">SELECT \* FROM products WHERE category = 'Gifts</mark><mark style="color:yellow;">''</mark> <mark style="color:purple;">AND released = 1</mark>



<mark style="color:purple;">SELECT \* FROM products WHERE category = 'Gifts'</mark> <mark style="color:yellow;">--+</mark> <mark style="color:purple;">AND released = 1</mark>

<mark style="color:purple;">com comentário ele ignora o que vem depois, e ai que está a vulnerabilidade.</mark>



