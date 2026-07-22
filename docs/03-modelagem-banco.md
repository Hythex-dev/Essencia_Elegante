# Modelagem do Banco de Dados

> Documento responsável por descrever todas as entidades do banco de dados da plataforma Essência Elegante.

Versão: 1.0.0

Status: Em elaboração

---

# Módulo 3 - Catálogo

## Objetivo

O módulo de Catálogo é responsável pelo gerenciamento completo dos produtos comercializados pela Essência Elegante.

Ele contempla produtos, categorias, imagens, cores, tamanhos e variações, permitindo que cada peça possua diferentes combinações de tamanho e cor, mantendo um controle individual de estoque.

---

# Entidade: Product

## Descrição

Armazena as informações gerais de um produto.

As informações específicas como cor, tamanho e estoque pertencem às variações do produto.

## Campos

| Campo | Tipo | Obrigatório | Descrição |
|--------|------|-------------|-----------|
| id | UUID | Sim | Identificador único |
| name | VARCHAR(150) | Sim | Nome do produto |
| slug | VARCHAR(180) | Sim | URL amigável |
| shortDescription | VARCHAR(255) | Sim | Descrição resumida |
| description | TEXT | Sim | Descrição completa |
| brand | VARCHAR(100) | Não | Marca |
| status | BOOLEAN | Sim | Produto ativo ou inativo |
| featured | BOOLEAN | Sim | Produto em destaque |
| metaTitle | VARCHAR(120) | Não | SEO |
| metaDescription | VARCHAR(255) | Não | SEO |
| weight | DECIMAL(8,2) | Não | Peso |
| height | DECIMAL(8,2) | Não | Altura |
| width | DECIMAL(8,2) | Não | Largura |
| length | DECIMAL(8,2) | Não | Comprimento |
| createdAt | TIMESTAMP | Sim | Data de criação |
| updatedAt | TIMESTAMP | Sim | Última atualização |
| deletedAt | TIMESTAMP | Não | Exclusão lógica |

---

## Relacionamentos

Product

1:N ProductVariant

1:N ProductImage

N:N Category

---

# Entidade: ProductVariant

## Descrição

Cada registro representa uma combinação única de cor e tamanho.

O estoque será controlado nesta entidade.

## Campos

| Campo | Tipo | Obrigatório | Descrição |
|--------|------|-------------|-----------|
| id | UUID | Sim | Identificador |
| productId | UUID | Sim | Produto |
| colorId | UUID | Sim | Cor |
| sizeId | UUID | Sim | Tamanho |
| sku | VARCHAR(50) | Sim | Código único |
| price | DECIMAL(10,2) | Sim | Preço |
| stock | INTEGER | Sim | Quantidade em estoque |
| createdAt | TIMESTAMP | Sim | Data de criação |
| updatedAt | TIMESTAMP | Sim | Última atualização |

---

## Relacionamentos

ProductVariant

N:1 Product

N:1 Color

N:1 Size

---

# Entidade: Color

## Descrição

Tabela responsável pelas cores disponíveis dos produtos.

## Campos

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | UUID | Sim |
| name | VARCHAR(50) | Sim |
| hex | VARCHAR(7) | Não |
| createdAt | TIMESTAMP | Sim |

---

## Exemplos

- Preto
- Branco
- Bege
- Azul
- Verde
- Marrom

---

# Entidade: Size

## Descrição

Tabela responsável pelos tamanhos disponíveis.

## Campos

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | UUID | Sim |
| name | VARCHAR(20) | Sim |
| displayOrder | INTEGER | Sim |
| createdAt | TIMESTAMP | Sim |

---

## Exemplos

- PP
- P
- M
- G
- GG

---

# Entidade: ProductImage

## Descrição

Armazena todas as imagens de um produto.

Um produto poderá possuir diversas imagens.

## Campos

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | UUID | Sim |
| productVariantId | UUID | Sim |
| imageUrl | TEXT | Sim |
| altText | VARCHAR(150) | Não |
| displayOrder | INTEGER | Sim |
| isPrimary | BOOLEAN | Sim |
| createdAt | TIMESTAMP | Sim |

---

## Relacionamentos

Product

1:N ProductImage

---

# Entidade: Category

## Descrição

Organiza os produtos em grupos.

## Campos

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | UUID | Sim |
| name | VARCHAR(100) | Sim |
| slug | VARCHAR(120) | Sim |
| description | TEXT | Não |
| createdAt | TIMESTAMP | Sim |
| updatedAt | TIMESTAMP | Sim |
| deletedAt | TIMESTAMP | Não |

---

## Exemplos

- Blazers
- Vestidos
- Calças
- Camisas
- Promoções
- Nova Coleção

---

# Entidade: ProductCategory

## Descrição

Tabela responsável pelo relacionamento entre Produtos e Categorias.

Um produto poderá pertencer a várias categorias.

Uma categoria poderá possuir vários produtos.

## Campos

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| productId | UUID | Sim |
| categoryId | UUID | Sim |

---

## Relacionamentos

Product

↓

ProductCategory

↓

Category

---

# Decisões Arquiteturais

## ADR-003

Os produtos utilizarão uma entidade de variações.

Motivo:

Permitir controle individual de estoque por tamanho e cor.

---

## ADR-004

Categorias utilizarão relacionamento N:N.

Motivo:

Permitir que um mesmo produto pertença a múltiplas categorias.

---

## ADR-005

O estoque será armazenado na ProductVariant.

Motivo:

Cada combinação de cor e tamanho possui quantidade própria.

---

# Fluxo do Catálogo

Product

│

├── ProductVariant

│      ├── Color

│      └── Size

│

├── ProductImage

│

└── ProductCategory

       └── Category

---

# Observações

- Todo produto deverá possuir pelo menos uma categoria.
- Todo produto deverá possuir pelo menos uma imagem.
- Todo produto deverá possuir ao menos uma variação cadastrada.
- Produtos inativos não serão exibidos na loja.
- Cada SKU deverá ser único.
- O controle de estoque será realizado por variação.
- Nenhum registro será removido fisicamente do banco de dados (Soft Delete).