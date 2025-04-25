

***Instalar o scoop***
<hr>

-  <font color="#00b0f0">Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser</font>
-  <font color="#00b0f0">Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression</font>

***Instalação do Symfony através do scoop, comand***
<hr>
  
- <font color="#00b0f0">   scoop install symfony-cli</font>
  
***Criação de um novo projeto webapp tradicional, comand***
<hr>

-  <font color="#00b0f0">symfony new --webapp "name"</font>

***Instalar pacotes/componentes do Symfony, instale o composer e execute o comand***
<hr>

- <font color="#00b0f0">composer require symfony/amphp-http-client-meta</font>

<hr>


1. Criação de controller deve ser feita em <font color="#00b0f0">/src/Controller</font>
2. Definição de rotas do controller em <font color="#00b0f0">/config/routes.yaml</font>
