# Regras de Negócio — Essência Elegante

## Módulo 1 — Usuários 

### RN-001 
O e-mail do usuário deve ser único no sistema.

### RN-002 
A senha deverá ser armazenada utilizando criptografia

### RN-003 
Um usuário poderá possuir apenas um perfil (CLIENT ou ADMIN).

### RN-004 
A exclusão de contas será realizada através de Soft Delete.

### RN-005 
Usuários excluídos não poderão realizar login.

---

# Módulo 2 — Produtos

### RN-006
Todo produto deverá possuir pelo menos uma categoria.

### RN-007
Todo produto deverá possuir pelo menos uma imagem.

### RN-008 
Todo produto deverá possuir uma variação cadastrada antes de ser disponibilizado para venda.

### RN-009 
Um produto poderá pertencer a diversas categorias.

### RN-010 
Produtos inativos não serão exibidos na loja.

### RN-011 
Cada variação deverá possuir um SKU único.

### RN-012
O estoque será controlado por variação do produto.

---

# Módulo 3 — Carrinho

### RN-013 
Não será permitido adicionar produtos sem estoque.

### RN-014 
A quantidade adicionada ao carrinho não poderá ultrapassar o estoque disponível.

### RN-015 
Produtos inativos serão removidos automaticamente do carrinho.

---

# Módulo 4 — Pedidos

### RN-016 
Um pedido somente poderá ser criado com um carrinho válido.

### RN-017 
O valor total será calculado automaticamente.

### RN-018
Pedidos pagos não poderão ser alterados.

### RN-019 
Pedidos cancelados não poderão retornar para o status anterior.

---

# Módulo 5 — Pagamentos

### RN-020 
Cada pagamento deverá estar vinculado a um pedido

### RN-021
Pagamentos aprovados atualizarão automaticamente o status do pedido.

### RN-022
Pagamentos recusados manterão o pedido aguardando nova tentativa.

---

# Módulo 6 — Estoque

### RN-023 
O estoque será atualizado automaticamente após confirmação do pagamento.
### RN-024
O estoque nunca poderá assumir valor negativo.

---

# Módulo 7 — Administração

### RN-025 
Somente administradores poderão acessar o painel administrativo.

### RN-026
Somente administradores poderão cadastrar, editar ou excluir produtos.

### RN-027 
Todas as ações administrativas deverão ser registradas para auditoria.

---

