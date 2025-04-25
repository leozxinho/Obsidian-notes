

**Resumo da Ideia do Projeto**  

A proposta é desenvolver uma plataforma de vendas online voltada para empresas e empreendedores de qualquer segmento, permitindo que cada cliente tenha seu próprio painel exclusivo para cadastrar produtos, gerenciar pedidos e acompanhar vendas. O sistema será simples, personalizável e escalável, ideal para quem deseja iniciar ou expandir suas vendas digitais com praticidade e organização

A estrutura esta básico ainda, conforme o projeto for se desenvolvendo, será aperfeiçoado. 

#### **🔹 Página 0 – Login (Acesso Inicial)**

> Página de entrada da aplicação, acessível por qualquer tipo de usuário.

**Características:**

- Campo de **usuário**
     Alternativas de login por:
     - **CPF**
     - **CNPJ**
- Campo de **senha**.
     Tipo de senha:
    -  8 caracteres
    -  pelo menos uma letra maiúscula
    -  pelo menos uma letra minúscula
    -  pelo menos 1 número
    -  pelo menos 1 caráter especial
---

> [!note]
> Talvez será usado essa logica, deixando apenas registrado 👇👇
> 
> Fluxo de Acesso e Lógica
> 1. O usuário acessa a **Página 0 (Login)**.
> 2. O sistema verifica se o login é de colaborador → redireciona para **Página 1**. Se o login é de cliente final (usuário com CNPJ/CPF) → redireciona para a **Página 2** correspondente.
> 3. Após o login, a navegação fica restrita conforme o tipo de usuário. 

---
### 🌐 Estrutura da Aplicação Web

#### **🔹 Página 1 – Painel Administrativo (Admin)**

> Acesso exclusivo para colaboradores da empresa criadora do produto.

**Menu de Navegação:**

- **Home:** Exibição de mensagem de boas-vindas e visão geral do sistema.
- **Gráficos de Consumo:** Visualização de métricas e dados de uso dos clientes (intens consumidos).
- **Clientes:** Listagem de todos os clientes cadastrados que utilizam a plataforma; acesso à criação da Página 2.
- **Usuários:** Gerenciamento de usuários internos (colaboradores da empresa); criação e edição.
- **Sair:** Encerramento da sessão e redirecionamento para a página de login.
---
#### **🔸 Página 2 – Painel do Cliente Final**

> Criado automaticamente a partir da seção "Clientes" da Página 1. Cada cliente possui seu próprio painel exclusivo.

**Menu de Navegação:**

- **Home:** Mensagem de boas-vindas personalizada (ex: “Bem-vindo à empresa [NOME]”).
- **Produtos:** Cadastro, edição e listagem de produtos que o cliente deseja comercializar.
- **Pedidos:** Visualização de pedidos recebidos, com status de validação e envio.
- **Relatório de Compras:** Relatórios detalhados por período (diário, mensal, anual) das vendas realizadas.
---
### 🧩 Relação Pai-Filho

- A **Página 1 (Admin)** é a **origem e gerenciadora** da Página 2.
- A **Página 2 (Cliente Final)** é **gerada dinamicamente** a partir do cadastro de um novo cliente.
- Cada cliente terá um **acesso separado** e **isolado** da área administrativa.

