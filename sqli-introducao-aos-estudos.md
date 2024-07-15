---
description: Aprendendo como usar o Sql Injection para invasão de sites de forma manual.
---

# SQLi Introdução aos estudos

SQLi

Quando eu quiser quebrar uma query eu posso usar ' na URL do site alvo, como exemplo:



<mark style="color:purple;">SELECT \* FROM products WHERE category = 'Gifts'' AND released = 1</mark>

<mark style="color:red;">^ esse seria para quebrar a query, e então daria erro no site. Porém, se eu colocar '' (duas aspas), o site vai interpretar de forma diferente.</mark>

<mark style="color:purple;">SELECT \* FROM products WHERE category = 'Gifts'' AND released = 1</mark>



<mark style="color:purple;">SELECT \* FROM products WHERE category = 'Gifts' --+ AND released = 1</mark>

<mark style="color:purple;">com comentário ele interpreta de forma diferente também, porém, não da erro.</mark>



