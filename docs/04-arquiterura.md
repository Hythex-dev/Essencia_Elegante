## Requisitos Não Funcionais

- Segurança
- Performance
- Escalabilidade
- Manutenção
- Disponibilidade
- Infraestrutura
- Padrões técnicos

# Arquitetura da Aplicação

> Documento responsável por definir a arquitetura, organização e padrões utilizados no desenvolvimento da plataforma Essência Elegante.

Versão: 1.0.0

Status: Em elaboração

---

# Objetivo

A arquitetura da Essência Elegante foi projetada para priorizar organização, escalabilidade, legibilidade e facilidade de manutenção.

O projeto seguirá princípios de Clean Code, Separation of Concerns (Separação de Responsabilidades) e uma abordagem simplificada inspirada em Domain Driven Design (DDD).

O objetivo é permitir que o sistema evolua de forma organizada, facilitando futuras implementações e reduzindo retrabalho.

---

# Tecnologias Utilizadas

## Front-end

- Next.js 15 (App Router)
- React
- TypeScript
- Tailwind CSS
- Shadcn/UI

---

## Back-end

- Next.js Server Actions
- Prisma ORM
- PostgreSQL
- Supabase

---

## Autenticação

- Auth.js
- Login por E-mail e Senha
- Login com Google

---

## Armazenamento

- Supabase Storage

---

# Estrutura do Projeto

```

src/

├── app/
│
├── components/
│
├── features/
│
├── repositories/
│
├── services/
│
├── lib/
│
├── types/
│
└── utils/

```

---

# Organização das Pastas

## app/

Responsável pelas rotas da aplicação utilizando o App Router do Next.js.

Exemplo:

- Página Inicial
- Produtos
- Carrinho
- Checkout
- Painel Administrativo

---

## components/

Componentes reutilizáveis da interface.

Exemplos:

- Button
- Input
- Card
- Modal
- Navbar
- Footer

Sempre que um componente puder ser utilizado em mais de um lugar, ele deverá permanecer nesta pasta.

---

## features/

Contém os módulos de negócio da aplicação.

Cada funcionalidade possui sua própria estrutura.

Exemplo:

features/

├── auth/
├── products/
├── categories/
├── cart/
├── orders/
└── admin/

Cada Feature poderá possuir:

- Components
- Services
- Hooks
- Types
- Utils

próprios daquele domínio.

---

## repositories/

Responsável pela comunicação com o banco de dados.

Nenhuma página poderá acessar o Prisma diretamente.

Todo acesso deverá ocorrer através dos Repositories.

Exemplo:

UserRepository

ProductRepository

OrderRepository

CategoryRepository

---

## services/

Responsável pelas regras de negócio.

Todo processamento da aplicação acontecerá nesta camada.

Exemplos:

Criar Pedido

Atualizar Estoque

Cadastrar Produto

Calcular Frete

Aplicar Cupom

---

## lib/

Configurações compartilhadas.

Exemplos:

Prisma Client

Auth

Supabase

Validações

Helpers

---

## types/

Tipos globais do projeto.

Interfaces.

Enums.

DTOs.

---

## utils/

Funções auxiliares.

Exemplos:

Formatar moeda

Formatar CEP

Formatar Data

Gerar Slug

Máscaras

---

# Fluxo da Aplicação

Toda requisição seguirá o seguinte fluxo:

Página (UI)
      ↓
Server Action
      ↓
Service
      ↓
Repository
      ↓
Prisma
      ↓
Banco de Dados

---

# Organização por Domínios

O sistema será dividido em módulos independentes.

## Autenticação

Responsável por:

- Cadastro
- Login
- Logout
- Recuperação de Senha

---

## Catálogo

Responsável por:

- Produtos
- Categorias
- Cores
- Tamanhos
- Imagens

---

## Carrinho

Responsável por:

- Carrinho
- Itens
- Quantidade
- Cálculo de valores

---

## Pedidos

Responsável por:

- Checkout
- Pedidos
- Pagamentos
- Histórico

---

## Administração

Responsável por:

- Produtos
- Categorias
- Usuários
- Pedidos
- Relatórios

---

# Padrões Utilizados

## Nomenclatura

Arquivos

kebab-case

Exemplo:

product-card.tsx

---

Componentes

PascalCase

Exemplo:

ProductCard

---

Funções

camelCase

Exemplo:

createProduct()

---

Variáveis

camelCase

Exemplo:

productPrice

---

Constantes

UPPER_SNAKE_CASE

Exemplo:

MAX_PRODUCTS

---

# Banco de Dados

Todas as tabelas utilizarão UUID como chave primária.

Todas as entidades importantes possuirão:

- createdAt
- updatedAt
- deletedAt

Será utilizado Soft Delete.

---

# Organização do Código

Cada arquivo deverá possuir apenas uma responsabilidade.

Exemplo:

ProductRepository

↓

Apenas consultas ao banco.

---

ProductService

↓

Apenas regras de negócio.

---

ProductCard

↓

Apenas interface.

---

# Princípios do Projeto

Durante todo o desenvolvimento serão seguidos os seguintes princípios:

- Clean Code
- SOLID (quando aplicável)
- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple)
- Separation of Concerns

---

# Escalabilidade

A arquitetura foi planejada para permitir futuras implementações sem necessidade de grandes refatorações.

Exemplos:

- Aplicativo Mobile
- Marketplace
- Programa de Fidelidade
- Cashback
- Multiadministradores
- Novos métodos de pagamento
- Integrações com ERP
- Integrações com transportadoras

---

# Objetivo Final

Construir uma plataforma moderna, organizada, escalável e de fácil manutenção, proporcionando uma excelente experiência tanto para os clientes quanto para os administradores da Essência Elegante.