# 07 - Especificação do Banco de Dados

## Introdução

Este documento descreve detalhadamente todas as entidades que compõem o banco de dados da plataforma Essência Elegante.

Cada entidade possui sua responsabilidade, seus campos e seus relacionamentos claramente definidos antes da implementação no Prisma.

---

# Domínio: Autenticação

## Entidade: User

### Responsabilidade

Representa qualquer usuário cadastrado na plataforma.

Um usuário pode ser uma cliente ou um administrador do sistema.

A autenticação será realizada utilizando Auth.js, sendo esta entidade estendida com informações específicas da Essência Elegante.

---

### Campos

| Campo | Tipo | Obrigatório | Descrição |
|--------|------|-------------|-----------|
| id | UUID | Sim | Identificador único |
| name | String | Sim | Nome completo |
| email | String | Sim | E-mail único |
| emailVerified | DateTime | Não | Confirmação do e-mail |
| password | String | Não | Utilizado quando houver autenticação por senha |
| image | String | Não | Foto de perfil |
| phone | String | Não | Telefone de contato |
| role | Enum(Role) | Sim | Perfil do usuário |
| isActive | Boolean | Sim | Indica se a conta está ativa |
| createdAt | DateTime | Sim | Data de criação |
| updatedAt | DateTime | Sim | Última atualização |
| deletedAt | DateTime | Não | Exclusão lógica |

---

### Relacionamentos

- 1:N Address
- 1:1 Cart
- 1:N Order
- 1:N Account
- 1:N Session

---

### Observações

- O campo `email` deverá ser único.
- Administradores serão diferenciados através do campo `role`.
- A exclusão será lógica (Soft Delete).
- O histórico de compras será preservado mesmo que a conta seja desativada.