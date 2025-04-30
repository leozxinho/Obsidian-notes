


Autenticação de login:

O Symfony fornece um comando para gerar autenticação básica:
     - comand: <font color="#00b0f0">php bin/console make:auth</font>
         - Escolha a opção Login form authenticator
	          - O comando irá criar: 
                 - Criar o controlador SecurityController.php
                     - Controlador que gerencia as rotas de login/logout
                     - Contém essas ações:
                         - `login()`: Exibe e processa o formulário de login
                         - `logout()`: Manipula o logout (normalmente vazia, pois o firewall cuida disso)
                 - Criar a view login.html.twig
                     - Template Twig com o formulário de login
                     - Inclui campos para username e password
                     - Tratamento de erros de autenticação
                 - Configurar o security.yaml
                     - Arquivo de configuração principal de segurança
                     - As principais seções configuradas são:
                        - `firewalls`: Define como a autenticação funciona
                        - `access_control`: Define restrições de acesso
                        - `providers`: Define como os usuários são carregados (normalmente de banco de dados)






## Como funciona a autenticação

1. Usuário acessa uma rota protegida
2. É redirecionado para /login
3. Preenche o formulário e envia
4. O Authenticator (gerado pelo comando)
    - Valida as credenciais
    - Busca o usuário no provedor configurado
    - Verifica a senha (via "hashing")
    - Cria a sessão autenticada
5. Usuário é redirecionado para a rota original.]



| IMPORTANTE                                       |
| ------------------------------------------------ |
| Estudar Configuração típica no security.yaml<br> |
