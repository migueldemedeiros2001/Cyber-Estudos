---
description: Exploração de falhas de Command Injection
---

# Command Injection

Command Injection, permite a execução de comandos arbitrários do sistema operacional por um atacante no servidor que hospeda uma aplicação.

Exemplo:

Em um site para pesquisa de hospedagem de URL, se tiver essa falha, você consegue abusar da falha com um comando, como este no lab da solyd: <mark style="color:yellow;">caveiratech.com && ls</mark>

&#x20;                                                                                  <mark style="color:yellow;">caveiratech.com && cat index.php</mark>

Com esses comandos, você vai ter acesso a arquivos confidenciais do banco de dados daquela URL.

O usuário pode tanto consultar arquivos, como adicionar arquivos ao banco de dados, usando a mesma forma, como esse exemplo: <mark style="color:yellow;">caveiratech.com && touch teste.php</mark>&#x20;
