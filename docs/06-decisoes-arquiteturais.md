# 06 - Decisões Arquiteturais

## Introdução

Este documento registra todas as decisões arquiteturais tomadas durante o desenvolvimento da plataforma **Essência Elegante**.

Cada decisão possui uma justificativa técnica e de negócio, permitindo compreender o motivo das escolhas realizadas e servindo como referência para futuras evoluções do sistema.

---

# ADR-001 — Framework Principal

## Status

✅ Aprovado

## Decisão

O sistema será desenvolvido utilizando **Next.js (App Router)**.

## Justificativa

- Excelente integração com React.
- Renderização híbrida (SSR, SSG e CSR).
- Melhor otimização para SEO.
- Server Components.
- Escalabilidade para crescimento da aplicação.
- Grande adoção pelo mercado.

---

# ADR-002 — Banco de Dados

## Status

✅ Aprovado

## Decisão

O banco de dados utilizado será **PostgreSQL**, hospedado no **Supabase**.

## Justificativa

- Banco relacional robusto.
- Excelente integração com Prisma.
- Facilidade para backups.
- Infraestrutura gerenciada.
- Possibilidade futura de utilizar Storage, Edge Functions e Realtime.

---

# ADR-003 — ORM

## Status

✅ Aprovado

## Decisão

Será utilizado o **Prisma ORM**.

## Justificativa

- Tipagem forte.
- Excelente integração com TypeScript.
- Migrations.
- Facilidade de manutenção.
- Alta produtividade durante o desenvolvimento.

---

# ADR-004 — Estrutura do Projeto

## Status

✅ Aprovado

## Decisão

A arquitetura seguirá uma estrutura modular baseada em funcionalidades (Feature-Based Architecture).

## Estrutura

```text
src/

app/
components/
features/
services/
repositories/
lib/
hooks/
types/
utils/
middleware/
```

## Justificativa

- Separação clara de responsabilidades.
- Melhor organização do código.
- Escalabilidade.
- Facilidade de manutenção.
- Reutilização de componentes.

---

# ADR-005 — Estratégia de Modelagem

## Status

✅ Aprovado

## Decisão

O banco de dados será modelado primeiro em nível de negócio.

Somente após a validação completa da modelagem será implementado no Prisma.

## Justificativa

- Evitar retrabalho.
- Reduzir alterações em migrations.
- Garantir uma modelagem consistente.
- Basear a implementação nas regras de negócio.

---

# ADR-006 — Arquitetura do Catálogo

## Status

✅ Aprovado

## Decisão

As imagens dos produtos pertencem às variações do produto e não ao produto principal.

Relacionamento:

```text
Product
    │
    ▼
ProductVariant
    │
    ▼
ProductImage
```

## Justificativa

Cada cor possuirá seu próprio conjunto de imagens.

Quando a cliente selecionar uma cor, todas as imagens da galeria serão atualizadas automaticamente para aquela variação.

Essa abordagem é utilizada pelos principais e-commerces de moda.

---

# ADR-007 — Autenticação

## Status

✅ Aprovado

## Decisão

A autenticação será implementada utilizando **Auth.js**.

A entidade **User** será estendida para armazenar informações específicas da Essência Elegante.

## Justificativa

- Maior segurança.
- Integração nativa com Next.js.
- Padrão adotado pelo mercado.
- Redução da quantidade de código de autenticação.
- Melhor manutenção a longo prazo.

---

# ADR-008 — Evolução do Catálogo

## Status

✅ Aprovado

## Decisão

As entidades **Brand** e **Tag** não farão parte da versão 1.0.

Serão implementadas apenas quando houver necessidade real do negócio.

## Justificativa

- Redução da complexidade inicial.
- Banco de dados mais simples.
- Desenvolvimento mais rápido.
- Foco no MVP.

---

# ADR-009 — Estratégia do MVP

## Status

✅ Aprovado

## Decisão

A primeira versão da Essência Elegante será focada em disponibilizar uma loja completamente funcional para vendas.

### Funcionalidades incluídas

- Cadastro de clientes
- Login
- Recuperação de senha
- Catálogo de produtos
- Categorias
- Coleções
- Produtos
- Variações
- Carrinho
- Pedidos
- Pagamentos
- Painel administrativo
- Auditoria
- Banners

### Funcionalidades futuras

- Marcas (Brand)
- Tags
- Cupons
- Wishlist
- Avaliações
- Programa de fidelidade
- Relatórios avançados
- Integrações futuras

## Justificativa

Permitir o lançamento rápido de uma versão estável e preparada para crescer sem aumentar desnecessariamente a complexidade do projeto.

---

# ADR-010 — Filosofia de Desenvolvimento

## Status

✅ Aprovado

## Decisão

Todo o desenvolvimento seguirá a filosofia de modelagem orientada ao domínio do negócio.

Antes da implementação de qualquer funcionalidade deverão ser definidos:

1. O problema de negócio.
2. A entidade responsável.
3. Os relacionamentos envolvidos.
4. As regras de negócio.
5. A implementação técnica.

## Princípios adotados

- Modelar primeiro o negócio.
- Modelar depois o banco de dados.
- Escrever código somente após a validação da arquitetura.
- Implementar apenas funcionalidades necessárias (YAGNI).
- Priorizar simplicidade.
- Manter a escalabilidade da solução.

## Justificativa

Redução de retrabalho.

Maior organização do projeto.

Facilidade de manutenção.

Arquitetura preparada para crescimento.

---

# ADR-011 — Modelagem das Compras

## Status

✅ Aprovado

## Decisão

O fluxo de compras será dividido em entidades independentes:

```text
User
 │
 ├── Address
 │
 ├── Cart
 │      │
 │      └── CartItem
 │
 └── Order
        │
        ├── OrderItem
        │
        └── Payment
```

## Justificativa

Cada entidade possui responsabilidades específicas.

Essa separação facilita manutenção, evolução e futuras integrações com gateways de pagamento e serviços logísticos.

---

# ADR-012 — Estratégia de Soft Delete

## Status

✅ Aprovado

## Decisão

Nem todas as entidades utilizarão Soft Delete.

Utilizarão:

- User
- Product
- ProductVariant
- Category
- Collection
- Banner

As demais entidades permanecerão com exclusão física quando necessário.

## Justificativa

Evitar aumento desnecessário da complexidade do banco.

Preservar apenas informações relevantes para auditoria e histórico.

---

# ADR-013 — Precisão Financeira

## Status

✅ Aprovado

## Decisão

Todos os valores monetários serão armazenados utilizando o tipo **Decimal**, nunca Float.

## Justificativa

Evitar erros de arredondamento.

Garantir precisão financeira.

Seguir boas práticas para sistemas de pagamentos e e-commerce.

---

# ADR-014 — Utilização de Enums

## Status

✅ Aprovado

## Decisão

Estados do sistema serão representados por Enums.

Exemplos:

- Role
- OrderStatus
- PaymentStatus
- PaymentMethod

## Justificativa

Maior consistência.

Melhor legibilidade.

Redução de erros de digitação.

Facilidade de manutenção.

---

# Considerações Finais

As decisões registradas neste documento representam a base arquitetural da plataforma Essência Elegante.

Novas decisões poderão ser adicionadas conforme o projeto evoluir, sempre mantendo o histórico das escolhas realizadas e suas respectivas justificativas.