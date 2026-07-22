# Requisitos Funcionais

## Módulo 1 - Autenticação

### RF-001 - Cadastro de Cliente

Descrição:

O sistema deverá permitir que visitantes criem uma conta na plataforma.

Dados necessários:

- Nome completo
- E-mail
- Telefone
- Senha

Critérios de aceitação:

- O e-mail não pode estar duplicado.
- A senha deve ser armazenada de forma segura.
- Após o cadastro, o cliente poderá acessar sua conta.


---

### RF-002 - Login

Descrição:

O sistema deverá permitir que clientes autenticados acessem sua conta.

Métodos:

- E-mail e senha
- Google


---

### RF-003 - Recuperação de senha

Descrição:

O sistema deverá permitir que o cliente redefina sua senha através do e-mail cadastrado.

---

### RF-004 - Logout

Descrição:

O sistema deverá permitir que o cliente encerre sua sessão com segurança.

---

### RF-005 - Perfil

Descrição:

O cliente poderá visualizar seus dados cadastrais.

---

### RF-006 - Editar Perfil

Descrição:

O cliente pode alterar:

Métodos:

- nome
- telefone
- foto (opcional)

---

### RF-007 - Alterar Senha

Descrição:

O cliente poderá alterar sua senha informando a senha atual.

---

### RF-008 - Exclusão de Conta

Descrição:

O cliente poderá solicitar a exclusão de sua conta.

# Módulo 2 — Clientes

## RF-009 — Visualização de Dados da Cliente
Permitir que a cliente visualize seus dados pessoais dentro da área "Minha Conta".

---

## RF-010 — Atualização de Dados da Cliente
Permitir que a cliente atualize suas informações pessoais.

---

## RF-011 — Gerenciamento de Endereços
Permitir que a cliente gerencie seus endereços de entrega.

Funcionalidades:
- Adicionar endereço
- Editar endereço
- Remover endereço
- Definir endereço principal

---

## RF-012 — Pedidos e Histórico de Compras
Permitir que a cliente visualize seus pedidos e histórico de compras.

Exibir:
- Número do pedido
- Data da compra
- Produtos
- Valor total
- Status do pedido

---

## RF-013 — Acompanhamento de Entrega
Permitir que a cliente acompanhe pedidos em andamento.

Funcionalidade:
- Botão "Acompanhar entrega"
- Visualização do status da entrega

# Módulo 3 — Produtos

## RF-014 — Cadastro de Produto

Permitir que administradores cadastrem novos produtos na plataforma.

Informações do produto:
- Nome do produto
- Descrição
- Fotos
- Preço
- Categoria
- Tamanhos disponíveis
- Cores disponíveis
- Quantidade em estoque
- Status do produto (ativo/inativo)

---

## RF-015 — Visualização de Produtos (Administrador)

Permitir que administradores visualizem todos os produtos cadastrados.

Informações exibidas:
- Nome do produto
- Categoria
- Preço
- Estoque
- Status do produto

---

## RF-016 — Atualização de Produto

Permitir que administradores alterem informações dos produtos cadastrados.

Dados editáveis:
- Nome do produto
- Descrição
- Fotos
- Preço
- Categoria
- Tamanhos disponíveis
- Cores disponíveis
- Quantidade em estoque
- Status do produto

---

## RF-017 — Remoção de Produto

Permitir que administradores removam produtos do catálogo.

Regra:
- Utilizar exclusão lógica (soft delete).
- Produtos removidos não devem aparecer para clientes.

---

## RF-018 — Controle de Estoque

Permitir que administradores controlem a quantidade disponível dos produtos.

Funcionalidades:
- Atualizar estoque
- Visualizar quantidade disponível
- Identificar produtos sem estoque

---

## RF-019 — Exibição de Categorias na Página Inicial

Permitir que clientes visualizem categorias de produtos na página inicial.

Informações exibidas:
- Nome da categoria
- Imagem da categoria (opcional)

Critério:
- Ao clicar em uma categoria, a cliente será direcionada aos produtos relacionados.

---

## RF-020 — Produtos em Destaque

Permitir que administradores selecionem produtos para aparecerem em destaque na página inicial.

Informações exibidas:
- Nome da peça
- Preço
- Botão "Adicionar ao carrinho"

Critérios:
- Apenas produtos ativos podem aparecer nos destaques.
- Cliente poderá adicionar o produto diretamente ao carrinho.

---

## RF-021 — Listagem de Produtos

Permitir que clientes visualizem todos os produtos disponíveis na loja.

Informações exibidas no card:
- Imagem do produto
- Nome da peça
- Preço
- Botão "Adicionar ao carrinho"

Critérios:
- Apenas produtos ativos aparecem na loja.
- Cliente poderá adicionar produtos ao carrinho.

---

## RF-022 — Visualização Detalhada do Produto

Permitir que clientes visualizem todas as informações de uma peça antes da compra.

Informações exibidas:
- Nome da peça
- Descrição
- Imagem do produto
- Preço
- Cores disponíveis
- Tamanhos disponíveis
- Botão "Adicionar ao carrinho"

Critérios:
- Cliente deverá visualizar todas as informações da peça.
- Cliente deverá selecionar tamanho e cor quando necessário antes de adicionar ao carrinho.
- Produtos inativos não poderão ser comprados.

# Módulo 4 — Categorias

## RF-023 — Cadastro de Categoria

Permitir que administradores cadastrem novas categorias de produtos.

Informações da categoria:
- Nome da categoria
- Descrição
- Imagem da categoria
- Status (ativa/inativa)
- Ordem de exibição na página inicial

Critérios:
- Administrador poderá criar novas categorias.
- Categorias ativas poderão ser exibidas para clientes.
- Categorias inativas não serão exibidas na loja.

---

## RF-024 — Visualização de Categorias (Administrador)

Permitir que administradores visualizem todas as categorias cadastradas.

Informações exibidas:
- Nome da categoria
- Quantidade de produtos vinculados
- Status
- Ordem de exibição

Critérios:
- Administrador poderá identificar categorias ativas e inativas.
- Administrador poderá visualizar produtos vinculados à categoria.

---

## RF-025 — Atualização de Categoria

Permitir que administradores alterem informações das categorias cadastradas.

Dados editáveis:
- Nome
- Descrição
- Imagem
- Status
- Ordem de exibição

Critérios:
- Alterações deverão ser salvas corretamente.
- Atualizações deverão refletir na loja.

---

## RF-026 — Remoção de Categoria

Permitir que administradores removam categorias cadastradas.

Regra:
- Utilizar exclusão lógica (soft delete).
- Categorias vinculadas a produtos não devem ser removidas definitivamente sem validação.

---

## RF-027 — Exibição de Categorias para Clientes

Permitir que clientes visualizem categorias disponíveis na loja.

Locais de exibição:
- Página inicial
- Menu de navegação
- Página de produtos

Critérios:
- Apenas categorias ativas serão exibidas.
- Ao selecionar uma categoria, a cliente visualizará os produtos relacionados.

# Módulo 5 — Carrinho

## RF-028 — Seleção de Produto Antes de Adicionar ao Carrinho

Permitir que a cliente visualize informações do produto antes de adicioná-lo ao carrinho.

Informações exibidas no pop-up:
- Imagem do produto
- Nome da peça
- Descrição
- Cores disponíveis
- Tamanhos disponíveis

Critérios:
- O pop-up deverá abrir ao clicar em "Adicionar ao carrinho" na Home.
- A cliente deverá selecionar cor e tamanho antes de adicionar o produto.
- O produto não poderá ser adicionado sem as informações necessárias.

---

## RF-029 — Adicionar Produto ao Carrinho

Permitir que a cliente adicione produtos ao carrinho após selecionar suas características.

Informações adicionadas:
- Produto
- Imagem
- Nome da peça
- Cor escolhida
- Tamanho escolhido
- Quantidade
- Valor unitário

Critérios:
- O produto deverá aparecer no carrinho após confirmação.
- As informações selecionadas deverão ser mantidas corretamente.

---

## RF-030 — Visualização do Carrinho

Permitir que a cliente visualize todos os produtos adicionados ao carrinho em uma página exclusiva.

Informações exibidas:
- Imagem do produto
- Nome da peça
- Cor selecionada
- Tamanho selecionado
- Quantidade
- Valor unitário
- Subtotal do produto
- Valor total da compra

Critérios:
- O acesso ao carrinho será realizado através da navbar.
- Apenas produtos adicionados pela cliente serão exibidos.
- O carrinho deverá apresentar o resumo da compra.

---

## RF-031 — Alteração de Quantidade no Carrinho

Permitir que a cliente altere a quantidade dos produtos adicionados.

Funcionalidades:
- Aumentar quantidade
- Diminuir quantidade

Critérios:
- O valor total deverá ser atualizado automaticamente.
- A quantidade não poderá ultrapassar o estoque disponível.

---

## RF-032 — Remover Produto do Carrinho

Permitir que a cliente remova produtos do carrinho.

Critérios:
- O produto removido deverá deixar de aparecer no carrinho.
- O valor total deverá ser atualizado automaticamente.

---

## RF-033 — Acesso aos Detalhes do Produto pelo Carrinho

Permitir que a cliente acesse novamente a página do produto através do carrinho.

Objetivo:
- Permitir alteração de características do produto.

Ações disponíveis:
- Alterar cor
- Alterar tamanho
- Adicionar novamente ao carrinho

Critérios:
- Ao clicar no produto, a cliente será direcionada para a página detalhada da peça.
- As alterações realizadas deverão refletir no carrinho.

---

## RF-034 — Persistência do Carrinho

Permitir que o carrinho permaneça salvo mesmo após a cliente sair da plataforma.

Funcionamento:
- Produtos adicionados deverão permanecer vinculados à conta da cliente.
- Ao retornar ao site, a cliente visualizará os produtos adicionados anteriormente.

Critérios:
- O carrinho não deverá ser perdido ao fechar o navegador.
- Produtos removidos não deverão permanecer no carrinho.
- O sistema deverá validar o estoque antes da finalização da compra.

# Módulo 6 — Checkout

## RF-035 — Seleção de Endereço de Entrega

Permitir que a cliente selecione um endereço de entrega previamente cadastrado durante o checkout.

Funcionamento:
- Exibir endereços cadastrados pela cliente.
- Permitir selecionar o endereço desejado.
- Permitir adicionar um novo endereço caso necessário.

Critérios:
- A cliente não precisará preencher novamente um endereço já cadastrado.
- O endereço selecionado deverá ser vinculado ao pedido.
- Caso não exista endereço cadastrado, a cliente poderá cadastrar um novo.

---

## RF-036 — Seleção de Forma de Pagamento

Permitir que a cliente escolha a forma de pagamento durante o checkout.

Formas disponíveis:
- Cartão de crédito
- Pix

Critérios:
- A cliente deverá selecionar uma forma de pagamento antes de finalizar a compra.
- O sistema deverá registrar a forma de pagamento escolhida no pedido.

---

## RF-037 — Resumo da Compra

Permitir que a cliente revise todas as informações da compra antes da confirmação.

Informações exibidas:

Produtos:
- Imagem do produto
- Nome da peça
- Cor escolhida
- Tamanho escolhido
- Quantidade
- Valor unitário
- Subtotal do produto

Valores:
- Subtotal dos produtos
- Valor do frete
- Descontos aplicados (quando houver)
- Valor total da compra

Dados da compra:
- Endereço de entrega
- Forma de pagamento

Critérios:
- A cliente deverá conseguir revisar todas as informações antes da finalização.
- O valor total deverá ser calculado corretamente.
- A cliente poderá voltar etapas anteriores para realizar alterações.

---

## RF-038 — Criação do Pedido no Checkout

Permitir que o sistema crie um pedido após a confirmação da compra pela cliente.

Funcionamento:
- Criar o pedido.
- Associar o pedido à cliente.
- Registrar produtos comprados.
- Registrar endereço de entrega.
- Registrar forma de pagamento.
- Definir status inicial como "Aguardando pagamento".

Critérios:
- O pedido deverá possuir um identificador único.
- O pedido deverá aparecer na área "Meus Pedidos".
- O estoque deverá ser validado antes da criação do pedido.

---

## RF-039 — Confirmação da Compra

Permitir que a cliente receba uma confirmação após finalizar a compra.

Informações exibidas:
- Número do pedido
- Data da compra
- Valor total
- Forma de pagamento
- Status atual do pedido

Critérios:
- A cliente deverá ser informada que o pedido foi criado.
- O pedido deverá aparecer no histórico de compras.

# Módulo 7 — Pedidos

## RF-040 — Gerenciamento de Status do Pedido

Permitir que o sistema controle o ciclo de vida dos pedidos através de diferentes status.

Status disponíveis:
- Aguardando pagamento
- Pagamento aprovado
- Em preparação
- Enviado
- Entregue
- Cancelado

Regras de atualização:

Automático:
- Aguardando pagamento → Pagamento aprovado

Administrador:
- Pagamento aprovado → Em preparação
- Em preparação → Enviado
- Enviado → Entregue
- Qualquer etapa permitida → Cancelado

Critérios:
- A cliente deverá visualizar o status atualizado do pedido.
- O administrador deverá conseguir atualizar os status permitidos.
- O sistema deverá registrar alterações realizadas.

---

## RF-041 — Visualização de Pedidos pela Cliente

Permitir que a cliente visualize seus pedidos realizados através da área "Minha Conta".

Lista de pedidos:

Informações exibidas:
- Número do pedido
- Data da compra
- Valor total
- Status atual do pedido

Detalhes do pedido:

Produtos:
- Imagem do produto
- Nome da peça
- Cor escolhida
- Tamanho escolhido
- Quantidade
- Valor unitário

Compra:
- Subtotal dos produtos
- Frete
- Valor total
- Forma de pagamento

Entrega:
- Endereço de entrega
- Status do pedido

Critérios:
- A cliente deverá visualizar somente seus próprios pedidos.
- A cliente poderá acessar detalhes de cada pedido.
- Pedidos antigos e atuais deverão permanecer disponíveis.

---

## RF-042 — Acompanhamento de Entrega

Permitir que a cliente acompanhe o andamento da entrega do pedido.

Funcionamento:

Quando o administrador alterar o pedido para "Enviado":

O sistema permitirá informar:
- Código de rastreio (opcional)

Regras:

Caso exista código de rastreio:
- Exibir status "Enviado".
- Exibir código de rastreio para a cliente.

Caso não exista código de rastreio:
- Exibir apenas o status "Enviado".

Critérios:
- A cliente deverá conseguir consultar o andamento do pedido.
- O código de rastreio deverá aparecer somente quando informado.

---

## RF-043 — Cancelamento de Pedido pelo Cliente

Permitir que a cliente solicite o cancelamento de um pedido dentro das condições permitidas.

Status permitidos para cancelamento:
- Aguardando pagamento
- Pagamento aprovado

Status que não permitem cancelamento direto:
- Em preparação
- Enviado
- Entregue

Critérios:
- O botão "Cancelar pedido" deverá aparecer somente nos status permitidos.
- O pedido deverá alterar seu status para "Cancelado".
- O histórico do pedido deverá permanecer registrado.

---

## RF-044 — Gerenciamento de Pedidos pelo Administrador

Permitir que administradores visualizem e gerenciem todos os pedidos realizados na plataforma.

Informações exibidas:

Pedido:
- Número do pedido
- Data da compra
- Status atual

Cliente:
- Nome da cliente
- E-mail
- Telefone

Produtos:
- Imagem do produto
- Nome da peça
- Cor escolhida
- Tamanho escolhido
- Quantidade
- Valor unitário

Pagamento:
- Forma de pagamento
- Status do pagamento
- Valor total

Entrega:
- Endereço de entrega
- Código de rastreio (quando informado)

Ações disponíveis:
- Visualizar detalhes do pedido
- Alterar status do pedido
- Confirmar preparação
- Informar envio
- Adicionar código de rastreio
- Confirmar entrega
- Cancelar pedido conforme regras

Critérios:
- Administradores deverão visualizar todos os pedidos.
- Alterações deverão refletir para a cliente.
- O histórico do pedido deverá ser mantido.

---

## RF-045 — Histórico de Alterações do Pedido

Permitir que o sistema registre todas as alterações realizadas no pedido.

Informações registradas:
- Status anterior
- Novo status
- Data e hora da alteração
- Responsável pela alteração

Exemplo:

Pedido #000125

Histórico:

21/07/2026 10:30
Pedido criado

21/07/2026 10:35
Pagamento aprovado

22/07/2026 09:15
Em preparação

23/07/2026 14:20
Enviado

30/07/2026 16:00
Entregue

Critérios:
- Toda alteração de status deverá gerar um registro.
- O histórico não poderá ser apagado.
- Cliente poderá visualizar o histórico do próprio pedido.
- Administrador poderá visualizar o histórico de todos os pedidos.

# Módulo 8 — Administração

## RF-046 — Acesso Administrativo

Permitir que um administrador único acesse o painel administrativo da plataforma.

Funcionamento:
- O administrador deverá realizar login utilizando:
  - E-mail
  - Senha

Após autenticação:
- O sistema deverá validar a permissão administrativa.
- O administrador terá acesso completo ao painel.

Critérios:
- Apenas usuários com permissão administrativa poderão acessar o painel.
- Clientes comuns não poderão acessar funcionalidades administrativas.
- O acesso deverá ser protegido por autenticação.

---

## RF-047 — Dashboard Administrativo

Permitir que o administrador visualize um resumo geral da operação da loja.

Informações exibidas:

Vendas:
- Total de vendas realizadas.
- Valor total vendido.
- Vendas recentes.

Pedidos:
- Pedidos aguardando pagamento.
- Pedidos em preparação.
- Pedidos enviados.
- Pedidos entregues.

Produtos:
- Quantidade de produtos cadastrados.
- Produtos ativos.
- Produtos inativos.
- Produtos com estoque baixo.

Clientes:
- Quantidade de clientes cadastrados.

Critérios:
- O administrador deverá visualizar um resumo da loja ao acessar o painel.
- As informações deverão ser atualizadas conforme movimentações.

---

## RF-048 — Gerenciamento de Clientes

Permitir que o administrador visualize e gerencie os clientes cadastrados.

Informações exibidas:

Dados do cliente:
- Nome completo.
- E-mail.
- Telefone.
- Data de cadastro.
- Status da conta.

Histórico:
- Quantidade de pedidos realizados.
- Última compra.
- Histórico de pedidos.

Ações:
- Visualizar dados do cliente.
- Consultar histórico de compras.
- Visualizar pedidos realizados.
- Ativar conta.
- Inativar conta.

Critérios:
- O administrador deverá visualizar todos os clientes cadastrados.
- Clientes inativos não poderão realizar compras.

---

## RF-049 — Gerenciamento de Produtos pelo Administrador

Permitir que o administrador gerencie os produtos cadastrados.

Informações exibidas:
- Imagem do produto.
- Nome da peça.
- Categoria.
- Preço.
- Quantidade em estoque.
- Status do produto.
- Data de cadastro.

Funcionalidades:
- Cadastrar novos produtos.
- Editar produtos.
- Atualizar estoque.
- Alterar preço.
- Gerenciar imagens.
- Gerenciar tamanhos.
- Gerenciar cores.
- Ativar produtos.
- Inativar produtos.

Filtros:
- Categoria.
- Status.
- Estoque.

Critérios:
- O administrador deverá localizar produtos facilmente.
- Produtos inativos não deverão aparecer para clientes.

---

## RF-050 — Gerenciamento de Categorias pelo Administrador

Permitir que o administrador gerencie categorias de produtos.

Informações:
- Nome da categoria.
- Descrição.
- Imagem.
- Status.
- Ordem de exibição.

Funcionalidades:
- Criar categorias.
- Editar categorias.
- Alterar imagem.
- Ativar categorias.
- Inativar categorias.
- Definir ordem na Home.

Critérios:
- Categorias inativas não deverão aparecer para clientes.
- A ordem definida deverá refletir na página inicial.

---

## RF-051 — Controle de Estoque por Variação

Permitir controle de estoque considerando cor e tamanho dos produtos.

Informações controladas:
- Produto.
- Cor.
- Tamanho.
- Quantidade disponível.

Funcionalidades:
- Cadastrar estoque por variação.
- Alterar quantidade.
- Visualizar estoque por cor.
- Visualizar estoque por tamanho.
- Identificar baixo estoque.

Regras:
- Cada combinação de cor e tamanho terá estoque próprio.
- Produtos sem estoque não poderão ser comprados.
- Estoque deverá atualizar após confirmação do pedido.

---

## RF-052 — Gerenciamento de Produtos em Destaque na Home

Permitir que o administrador escolha manualmente os produtos exibidos em destaque.

Funcionalidades:
- Selecionar produtos para destaque.
- Remover produtos dos destaques.
- Alterar ordem dos produtos.
- Ativar ou desativar destaque.

Regras:
- Apenas produtos ativos poderão aparecer na Home.

Critérios:
- Alterações deverão refletir automaticamente na página inicial.

---

## RF-053 — Gerenciamento de Banners da Home

Permitir que o administrador gerencie banners exibidos na página inicial.

Informações:
- Imagem.
- Título.
- Descrição.
- Texto do botão.
- Link de destino.
- Status.

Funcionalidades:
- Criar banners.
- Editar banners.
- Alterar imagens.
- Alterar textos.
- Definir ordem.
- Ativar/Inativar banners.

Critérios:
- Apenas banners ativos serão exibidos.
- Alterações não dependerão de código.

---

## RF-054 — Configurações da Loja

Permitir que o administrador altere informações gerais da Essência Elegante.

Informações editáveis:

Identidade:
- Nome da loja.
- Logo.

Contato:
- WhatsApp.
- E-mail.
- Telefone.

Redes sociais:
- Instagram.
- Facebook.
- Outras redes.

Institucional:
- Endereço.
- Política de troca.
- Política de privacidade.

Critérios:
- Alterações deverão refletir no sistema.
- Apenas administrador poderá alterar configurações.

---

## RF-055 — Relatórios Administrativos

Permitir que o administrador visualize relatórios gerenciais.

Relatórios:

Vendas:
- Faturamento.
- Vendas por período.
- Quantidade de pedidos.
- Ticket médio.

Produtos:
- Produtos mais vendidos.
- Categorias mais vendidas.
- Produtos com baixo estoque.

Clientes:
- Quantidade de clientes.
- Clientes que mais compram.
- Novos clientes.

Pedidos:
- Quantidade por status.

Filtros:
- Período.
- Categoria.
- Produto.
- Status.

Visualizações:
- Gráficos.
- Indicadores.
- Tabelas.

---

## RF-056 — Gerenciamento de Cupons e Promoções

Permitir que o administrador crie e gerencie cupons de desconto.

Informações:
- Código do cupom.
- Nome da promoção.
- Tipo de desconto.
- Valor.
- Data inicial.
- Data final.
- Status.

Tipos:
- Por porcentagem.
- Valor fixo.
- Frete grátis (futuramente).

Funcionalidades:
- Criar cupons.
- Editar.
- Ativar.
- Inativar.
- Definir validade.
- Visualizar utilização.

Regras:
- Cupons inválidos não poderão ser utilizados.
- O desconto deverá ser aplicado no checkout.
- Uso deverá ser registrado no pedido.

# Módulo 9 — Marketing

## RF-057 — Lista de Desejos (Favoritos)

**Descrição:**

O sistema deverá permitir que clientes salvem produtos favoritos para consultar posteriormente.

### Funcionalidades:

A cliente poderá:

- Adicionar produtos aos favoritos.
- Remover produtos favoritos.
- Visualizar sua lista de desejos.
- Adicionar produtos favoritos ao carrinho.

### Informações exibidas:

Cada produto favorito deverá apresentar:

- Imagem do produto.
- Nome da peça.
- Preço atual.
- Status de disponibilidade.

### Regras:

- Apenas clientes autenticados poderão utilizar a lista de desejos.
- Produtos inativos não deverão aparecer como disponíveis.
- A lista deverá permanecer salva na conta da cliente.

### Critérios de aceitação:

- A cliente deverá conseguir salvar produtos para consultar depois.
- Os favoritos deverão permanecer salvos após novo login.
- A cliente deverá conseguir remover produtos da lista.

---

## RF-058 — Avaliação de Produtos

**Descrição:**

O sistema deverá permitir que clientes avaliem produtos adquiridos na plataforma.

### Funcionalidades para clientes:

A cliente poderá:

- Avaliar produtos comprados.
- Atribuir nota de 1 a 5 estrelas.
- Escrever comentários.
- Visualizar avaliações de outras clientes.

### Regras:

- Apenas clientes que compraram o produto poderão avaliar.
- Cada cliente poderá avaliar um produto uma vez.
- Avaliações deverão estar vinculadas ao pedido realizado.

### Funcionalidades para administrador:

O administrador poderá:

- Visualizar avaliações.
- Remover avaliações inadequadas.
- Gerenciar avaliações publicadas.

### Critérios de aceitação:

- A avaliação deverá aparecer na página do produto.
- A nota média deverá ser calculada automaticamente.
- Apenas compradores poderão realizar avaliações.

---

## RF-059 — Newsletter e Captura de Leads

**Status:** Futuro

**Descrição:**

O sistema poderá permitir a captura de contatos de visitantes interessados em receber novidades da Essência Elegante.

### Possíveis funcionalidades futuras:

- Cadastro de nome e e-mail.
- Envio de novidades.
- Divulgação de coleções.
- Campanhas promocionais.

---

## RF-060 — Recuperação de Carrinho Abandonado

**Status:** Futuro

**Descrição:**

O sistema poderá identificar carrinhos abandonados e criar ações para recuperar possíveis vendas.

### Possíveis funcionalidades futuras:

- Identificar clientes que abandonaram produtos no carrinho.
- Enviar lembretes.
- Criar campanhas de recuperação.
- Direcionar cliente novamente ao carrinho.

---

## RF-061 — Compartilhamento de Produtos

**Descrição:**

O sistema deverá permitir que clientes compartilhem produtos da Essência Elegante.

### Funcionalidades:

A cliente poderá:

- Compartilhar link do produto.
- Compartilhar pelo WhatsApp.
- Compartilhar pelas redes sociais.

### Informações compartilhadas:

- Imagem do produto.
- Nome da peça.
- Preço.
- Link da página do produto.

### Regras:

- O compartilhamento deverá direcionar para a página pública do produto.
- Produtos inativos não deverão ser compartilhados como disponíveis.

### Critérios de aceitação:

- A cliente deverá conseguir compartilhar produtos facilmente.
- O link deverá abrir corretamente a página do produto.
- As informações deverão estar atualizadas.

---

## RF-062 — Notificações por E-mail para Clientes

**Descrição:**

O sistema deverá enviar notificações automáticas por e-mail para informar clientes sobre eventos importantes.

### Eventos de notificação:

Conta:

- Cadastro realizado.
- Recuperação de senha.
- Alteração de dados.

Pedidos:

- Pedido realizado.
- Pagamento aprovado.
- Pedido em preparação.
- Pedido enviado.
- Código de rastreio disponível.
- Pedido entregue.
- Pedido cancelado.

### Informações do e-mail:

- Nome da cliente.
- Número do pedido.
- Produtos comprados.
- Valor total.
- Status do pedido.
- Código de rastreio.

### Regras:

- O envio deverá ocorrer automaticamente.
- A cliente deverá receber apenas informações da própria conta.

---

## RF-063 — Programa de Fidelidade

**Status:** Futuro

**Descrição:**

O sistema poderá permitir a criação de um programa de fidelidade para clientes recorrentes.

### Possíveis funcionalidades futuras:

- Acúmulo de pontos.
- Benefícios exclusivos.
- Cupons personalizados.
- Categorias VIP.

---

## RF-064 — Produtos Relacionados

**Status:** Futuro

**Descrição:**

O sistema poderá apresentar produtos relacionados para incentivar compras complementares.

### Possíveis funcionalidades futuras:

- Produtos semelhantes.
- Combinações de peças.
- Sugestões por categoria.
- Curadoria manual pelo administrador.

Exemplo:

Produto:

Blazer Alfaiataria Preto

Sugestões:

- Calça Alfaiataria Preta.
- Camisa Social Feminina.
- Conjunto Alfaiataria.

---

## RF-065 — Histórico de Interações da Cliente

**Status:** Futuro

**Descrição:**

O sistema poderá registrar interações das clientes para criar experiências personalizadas.

### Possíveis informações:

- Produtos visualizados.
- Categorias acessadas.
- Produtos favoritos.
- Histórico de compras.
- Preferências de estilo.

### Possíveis aplicações:

- Recomendações personalizadas.
- Campanhas direcionadas.
- Estratégias de relacionamento.
# Módulo 10 — Configurações

## RF-066 — Configurações Gerais da Loja

**Descrição:**

O sistema deverá permitir que o administrador gerencie informações gerais da Essência Elegante através do painel administrativo.

### Informações editáveis:

### Identidade da marca:

- Nome da loja.
- Logo.
- Favicon.

### Contatos:

- WhatsApp.
- Telefone.
- E-mail.

### Redes sociais:

- Instagram.
- Facebook.
- TikTok.
- Outras redes sociais.

### Informações institucionais:

- Endereço.
- Sobre a marca.
- Política de troca.
- Política de privacidade.

### Funcionalidades:

O administrador poderá:

- Editar informações da loja.
- Atualizar logo.
- Alterar contatos.
- Atualizar redes sociais.
- Modificar textos institucionais.

### Regras:

- Apenas administrador autenticado poderá alterar configurações.
- Alterações deverão refletir automaticamente nas áreas públicas.
- Informações deverão ser armazenadas com segurança.

---

## RF-067 — Configurações de Pagamento

**Descrição:**

O sistema deverá permitir a configuração das formas de pagamento disponíveis para os clientes.

### Formas de pagamento:

## PIX

O sistema deverá permitir:

- Pagamento via PIX.
- Identificação do pagamento.
- Atualização do status do pedido após confirmação.

## Cartão de crédito

O sistema deverá permitir:

- Pagamento com cartão.
- Processamento da transação.
- Atualização do status do pedido.

### Funcionalidades administrativas:

O administrador poderá:

- Ativar ou desativar métodos de pagamento.
- Visualizar pagamentos realizados.
- Acompanhar status dos pagamentos.

### Regras:

- Apenas métodos ativos aparecerão no checkout.
- O pedido deverá registrar a forma de pagamento utilizada.
- O pedido só deverá avançar após confirmação do pagamento.

---

## RF-068 — Configurações de Entrega

**Descrição:**

O sistema deverá permitir a configuração dos métodos de entrega disponíveis aos clientes.

### Métodos de entrega:

## Correios

O sistema deverá permitir:

- Envio pelos Correios.
- Registro do valor do frete.
- Prazo estimado de entrega.

## Transportadora

O sistema deverá permitir:

- Seleção da transportadora.
- Registro do valor do frete.
- Prazo estimado de entrega.

### Funcionalidades administrativas:

O administrador poderá:

- Ativar ou desativar métodos de entrega.
- Configurar valores de frete.
- Definir prazos.
- Atualizar informações de envio.

### Regras:

- Apenas métodos ativos aparecerão no checkout.
- O cliente deverá escolher uma opção de entrega.
- O pedido deverá armazenar o método escolhido.

---

## RF-069 — Configurações de Segurança

**Descrição:**

O sistema deverá possuir mecanismos básicos de segurança para proteger dados de clientes, pedidos e informações administrativas.

### Segurança de autenticação:

- Login protegido.
- Senhas criptografadas.
- Controle de sessão.

### Controle administrativo:

- Acesso restrito ao painel administrativo.
- Validação de permissões.
- Bloqueio de acesso de clientes comuns.

### Proteção de dados:

- Proteção das informações cadastradas.
- Comunicação segura entre serviços.

### Regras:

- Senhas nunca deverão ser armazenadas em texto puro.
- Apenas usuários autorizados poderão acessar áreas administrativas.
- Dados sensíveis deverão possuir proteção.

---

## RF-070 — Configurações de E-mails

**Descrição:**

O sistema deverá permitir que o administrador configure informações relacionadas aos e-mails enviados pela Essência Elegante.

### Informações editáveis:

### Identificação:

- Nome do remetente.
- E-mail de contato.

### Comunicação:

- Mensagem de boas-vindas.
- Mensagem de confirmação de pedido.
- Mensagem de atualização de entrega.

### Controle:

- Ativar ou desativar notificações específicas.

### Configurações protegidas:

- Servidor de envio.
- Credenciais.
- Chaves de acesso.

### Regras:

- Apenas administrador poderá alterar mensagens.
- Alterações deverão refletir nos próximos e-mails enviados.

---

## RF-071 — Modo de Manutenção do Sistema

**Descrição:**

O sistema deverá permitir que o administrador ative um modo de manutenção temporário.

### Funcionalidades:

O administrador poderá:

- Ativar modo manutenção.
- Desativar modo manutenção.
- Definir mensagem personalizada.
- Continuar acessando o painel administrativo.

### Comportamento:

Quando ativado:

Clientes:

- Não poderão realizar compras.
- Visualizarão mensagem de manutenção.

Administrador:

- Terá acesso ao painel.
- Poderá realizar ajustes.

### Regras:

- O modo manutenção não poderá apagar dados.
- O administrador deverá manter acesso ao sistema.

---

## RF-072 — Configurações de Integrações

**Descrição:**

O sistema deverá permitir que o administrador gerencie integrações externas utilizadas pela loja.

### Integrações possíveis:

### Pagamentos:

- Gateway de pagamento.

### Entregas:

- Serviços de transporte.
- Rastreamento.

### Comunicação:

- Serviço de envio de e-mails.

### Análises:

- Ferramentas de acompanhamento.

### Funcionalidades:

O administrador poderá:

- Ativar integrações.
- Desativar integrações.
- Configurar informações necessárias.
- Verificar status.

### Regras:

- Apenas integrações autorizadas poderão ser configuradas.
- Dados sensíveis deverão ser protegidos.

---

## RF-073 — Backup e Recuperação de Dados

**Descrição:**

O sistema deverá possuir mecanismos de backup para proteger os dados da Essência Elegante.

### Dados incluídos:

- Clientes.
- Produtos.
- Categorias.
- Estoque.
- Pedidos.
- Pagamentos.
- Configurações da loja.

### Funcionalidades:

O sistema deverá:

- Realizar backups automáticos.
- Armazenar cópias de segurança.
- Permitir recuperação dos dados.

### Funcionalidades administrativas:

O administrador poderá:

- Visualizar status do backup.
- Consultar último backup realizado.
- Solicitar restauração.

### Regras:

- O backup deverá ocorrer automaticamente.
- Os dados deverão possuir proteção.
- A restauração deverá ser realizada com segurança.

---

# Resumo do Módulo 10 — Configurações

RF-066 — Configurações Gerais da Loja

RF-067 — Configurações de Pagamento

RF-068 — Configurações de Entrega

RF-069 — Configurações de Segurança

RF-070 — Configurações de E-mails

RF-071 — Modo de Manutenção do Sistema

RF-072 — Configurações de Integrações

RF-073 — Backup e Recuperação de Dados