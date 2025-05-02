
📄 Mapeamento técnico

1. Objetivo da Tela de Login
Permitir o acesso seguro à aplicação, respeitando as permissões e comportamentos específicos de **colaboradores**, **clientes finais** e **consumidores visitantes**. A tela de login funciona como **ponto de entrada controlado** para usuários que precisam de autenticação.
- Tipos de Usuários e Comportamento:
     - <font color="#0070c0">Colaborador</font>
       - **Quem é:** Funcionário ou gestor da empresa, com funções administrativas
       - **Acesso: Restrito** — só acessa com login.
       - **Áreas permitidas:** Painel de controle interno (/admin,/relatorios, etc).
       - **Segurança:** Alta — exige login completo, 2FA, e rate limit.
       - **Comportamento após login:** É redirecionado diretamente para o painel administrativo. 
    - <font color="#0070c0">Cliente:</font>
      - **Quem é**: Pessoa que possui cadastro e interage com a empresa (ex: compras, contratos, suporte).
      - **Acesso**: **Restrito** — precisa de login para acessar o “painel do cliente”.
      - **Áreas permitidas**: `/cliente`, `/perfil`, `/pedidos-consumidor`, etc.
      - **Segurança**: Exige login, senha forte e pode ter 2FA opcional.
      - **Comportamento após login**: Redirecionado para sua área pessoal.
    - <font color="#0070c0">Consumidor (Visitante)</font>
      - **Quem é**: Qualquer usuário que navega no site sem se identificar.
      - **Acesso**: **Livre**, com login **obrigatório** até o momento da compra.
      - **Áreas permitidas**: Produtos, páginas públicas, blog, etc.
      - **Segurança**: Básica — login só exigido no carrinho/checkout.
      - **Comportamento após login**: Volta para o ponto da jornada (ex: checkout).


**Objetivos — Tela de login**

- Utilizar RegEx ou biblioteca PHP para validar formato CPF/CPNJ.
- Integração com Scheb/2FA Bundle (TOTP)
- Symfony Mailer (Envio de e-mails para recuperação de senha e alertas.)
- ReCaptcha (Google)
- Rate Limiting
- Proteção CSRF (Symfony já inclui CSRF nos fomulários form_login)
- Roles para para Entidade de usuários (role_admin, role_cliente, role_consumidor)