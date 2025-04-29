

**Resumo da Ideia do Projeto**  

A proposta é desenvolver uma plataforma de vendas online voltada para empresas e empreendedores de qualquer segmento, permitindo que cada cliente tenha seu próprio painel exclusivo para cadastrar produtos, gerenciar pedidos e acompanhar vendas. O sistema será simples, personalizável e escalável, ideal para quem deseja iniciar ou expandir suas vendas digitais com praticidade e organização

<font color="#00b0f0">A estrutura ainda está em fase inicial e será aperfeiçoada conforme o desenvolvimento do projeto evoluir.</font>

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
- Segurança
    - Autenticação em dois fatores (2FA)
    - Recuperação de senha por e-mail/SMS
    - Rate limit para tentativas de login

Lógica da Tela de login: [[Lógica da Tela de login]]

---

### 🌐 Estrutura da Aplicação Web

#### **🔹 Página 1 – Painel Administrativo (Admin)**

> Acesso exclusivo para colaboradores da empresa criadora do produto.

**Menu de Navegação:**

- **Home:** Exibição de mensagem de boas-vindas e visão geral do sistema.
- **Gráficos de Consumo:** Visualização de métricas e dados de uso dos clientes (intens consumidos).
- **Clientes:** Listagem de todos os clientes cadastrados que utilizam a plataforma; acesso à criação da Página 2.
- **Usuários:** Gerenciamento de usuários internos (colaboradores da empresa).
     - Tipo de senha:
        -  Controle de permissões e papéis (admin, gerente, vendedor, suporte)
        - Logs de atividade (registro de ações de usuários: login, criação, exclusão, edição)
        - Sistema de notificações internas (novos pedidos, alterações importantes, alertas)
- **Sair:** Encerramento da sessão e redirecionamento para a página de login.

Acesso painel de cliente:
     - Botão "Impersonar cliente" (Entrar no painel do cliente sem senha para suporte)
---
#### **🔸 Página 2 – Painel do Cliente**

> Criado automaticamente a partir da seção "Clientes" da Página 1. Cada cliente possui seu próprio painel exclusivo.

**Menu de Navegação:**

- **Home:** Mensagem de boas-vindas personalizada (ex: “Bem-vindo à empresa [NOME]”).
- **Produtos:** Cadastro, edição e listagem de produtos que o cliente deseja comercializar.
     - Filtro por categoria, preço, tipo, etc...
     - Histórico de pedidos (Com repetição rápida "Comprar novamente")
     - Notificações básicas por e-mail, status do produto.
- **Pedidos:** Visualização de pedidos recebidos, com status de validação e envio.
- **Relatório de Compras:** Relatórios detalhados por período (diário, mensal, anual) das vendas realizadas.
     - Relatórios exportáveis (CSV/PDF)
- Controle de estoque
     - Alertas de baixo estoque
- Personalização de identidade visual para cada cliente (cores, logotipo)
- Webhooks para sistema externos
     - Avisar quando tiver novos pedidos, cancelamentos, reclamações, etc...
---


#### **🛒 Página 3 – Portal do Consumidor**


>Essa página será gerada automaticamente, com um botão "Liberar para consumidor" na Página 2.


**Funcionalidades básicas da página do consumidor**

- Home da Loja
     - Logotipo, nome da empresa e banner (configurável pelo cliente)
 - Listagem de produtos
     - Nome, imagem, descrição, preço, botão "Adicionar ao carrinho"
     - Filtrar por categoria/preço/tipo 
 - Carrinho de compras
    - Listagem de itens selecionados
    - Quantidade e total
    - Botão para finalizar pedido
- Finalização de pedido
     - Dados obrigatórios: Nome, CPF/CNPJ, telefone, e-mail
     - Endereço de entrega
     - Forma de pagamento
     - Observações adicionais
     - Botão "Confirmar pedido"
         - Confirmação "Mensagem de sucesso:  Compra efetuada com sucesso!"
         - Envio automático de e-mail ao consumidor

**Privacidade e Segurança** 

 - A Página do consumidor não exige login obrigatório, **exceto somente caso for realizar pedidos de item.**
 - O painel do consumidor não permite acessar o painel de gestão nem editar produtos.


### 🧩 Relação Pai-Filho

- A **Página 1 (Admin)** é a **origem e gerenciadora** da Página 2.
- A **Página 2 (Cliente Final)** é **gerada dinamicamente** a partir do cadastro de um novo cliente.
- Cada cliente terá um **acesso separado** e **isolado** da área administrativa.

