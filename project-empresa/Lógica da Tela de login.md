
Voltar [[Projeto - In & National]]

> **Ferramentas a serem usadas**

- **PHP + Symfony** – Backend e autenticação.
- **Twig** – Templates da interface.
- **Tailwind CSS + HTML** – Estilização e estrutura visual da tela de login.

> **Contexto Geral**

A aplicação tem **três tipos de usuários**:

1. **Colaborador** – Acesso interno ao painel administrativo.
2. **Cliente final** – Acesso à área de cliente (perfil, pedidos, etc.).
3. **Consumidor (Visitante)** – Pode navegar livremente, login exigido apenas na hora da compra.


> **Lógica da Tela de Login (Página 0)**

 > **Ponto de Entrada**

- Há uma **única tela de login**, acessível por qualquer usuário.
- O sistema **não diferencia o tipo de usuário no início**, apenas depois que ele insere e autentica suas credenciais.

> **Fluxo de Autenticação**

1. **Usuário acessa a página de login.**
2. **Insere login e senha.**
3. **Sistema autentica as credenciais.**
4. Após autenticação:
    - Se for **colaborador** ➜ redireciona para **Página 1** (painel administrativo).
    - Se for **cliente final** ➜ redireciona para **Página 2** (área do cliente).
    - Se for **consumidor (visitante)**, o login **não é obrigatório no início**. Só precisa se autenticar se quiser **comprar** ou acessar funcionalidades privadas.

 > **Consumidor (Visitante) – Acesso Livre**

- Pode navegar normalmente sem login (Página 3).
- Só ao tentar comprar, o sistema exige autenticação:
    - Se já tem conta: faz login.
    - Se não tem: faz cadastro.

> **Segurança**

- **Ações sensíveis (compra, dados pessoais, histórico)** só são permitidas após autenticação.
- Deve-se manter:
    - Sessão de visitante (anônima).
    - Após login, atualizar a sessão para associá-la ao usuário autenticado.
    - Garantir que nenhuma rota sensível (como `/checkout`, `/perfil`, `/meus-pedidos`) esteja acessível sem login.