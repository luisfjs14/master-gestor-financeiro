# 💰 Sistema Financeiro Pessoal

![Status](https://img.shields.io/badge/status-Em%20Desenvolvimento-blue)
![PHP](https://img.shields.io/badge/PHP-8.2-%23777BB4)
![MySQL](https://img.shields.io/badge/MySQL-Database-orange)
![License](https://img.shields.io/badge/license-MIT-green)

Aplicação web completa para **controle financeiro pessoal**, desenvolvida em **PHP + MySQL**, com interface moderna, responsiva e intuitiva.  
Permite gerenciar contas, cartões de crédito, faturas mensais, lançamentos e acompanhar o saldo atualizado em tempo real.

---

## 🚀 Funcionalidades Principais

### 🧍‍♂️ Autenticação
- Registro e login de usuários com sessões seguras.
- Cada usuário tem acesso apenas aos seus próprios dados.

### 💳 Controle de Contas
- Cadastro de múltiplas contas (ex: carteira, conta corrente, poupança).
- Exibição de saldo em tempo real.
- Atualização automática após lançamentos em débito, pix ou dinheiro.

### 💸 Lançamentos Financeiros
- Registro de **compras e receitas** com:
  - Descrição, valor, data e forma de pagamento.
  - Opção de parcelamento para compras no crédito.
- Formas de pagamento disponíveis:
  - 💵 Dinheiro  
  - ⚡ Pix  
  - 🏦 Débito  
  - 💳 Crédito  

### 🧾 Sistema de Crédito com Faturas
- Cada cartão de crédito possui **fechamento** e **vencimento** configuráveis.
- O sistema gera automaticamente as **faturas mensais** conforme as compras.
- As parcelas são alocadas nas faturas dos meses correspondentes.
- Visualização de todas as faturas com:
  - Mês de referência  
  - Valor total  
  - Lista de lançamentos  
- Exibe apenas as faturas **que contêm compras** (sem gerar faturas vazias).

### 📊 Dashboard Inteligente
- Resumo com:
  - Saldo total consolidado  
  - Gastos do mês  
  - Projeção de faturas futuras  
  - Últimos lançamentos registrados

---

## 🧱 Estrutura do Banco de Dados

### Tabelas principais

#### 🧑 users
Armazena dados de login e autenticação do usuário.

#### 🏦 accounts
Registra as contas bancárias e carteiras do usuário.

#### 💳 cards
Gerencia os cartões de crédito com data de fechamento e vencimento.

#### 🧾 invoices
Representa as **faturas mensais** geradas automaticamente.

#### 💰 transactions
Armazena todos os lançamentos (compras, receitas, etc).

---

### Exemplo de estrutura da tabela `transactions`

| Campo | Tipo | Descrição |
|--------|------|-----------|
| id | INT | Identificador da transação |
| user_id | INT | Usuário dono da transação |
| account_id | INT | Conta vinculada (pix/débito) |
| card_id | INT | Cartão vinculado (crédito) |
| invoice_id | INT | Fatura relacionada |
| descricao | VARCHAR | Descrição da compra |
| valor | DECIMAL | Valor da transação |
| forma_pagamento | ENUM | dinheiro / pix / debito / credito |
| parcelas | INT | Nº total de parcelas |
| parcela_atual | INT | Número da parcela atual |
| data_compra | DATE | Data da compra |

---

## 🔁 Fluxo das Compras no Crédito

1. O usuário lança uma compra no **modo crédito**.  
2. O sistema identifica o **cartão** e suas **datas de fechamento e vencimento**.  
3. Cada parcela é alocada na **fatura do mês correspondente**.  
4. Caso a fatura não exista, ela é **criada automaticamente**.  
5. O valor é somado ao total da fatura.  
6. No painel do cartão (`card.php`), o usuário visualiza:
   - Faturas organizadas por mês.
   - Total da fatura e todas as compras daquele período.

---

## 🖥️ Tecnologias Utilizadas

| Tecnologia | Finalidade |
|-------------|-------------|
| **PHP (PDO)** | Lógica de back-end e conexão com o banco |
| **MySQL** | Armazenamento e relacionamento dos dados |
| **HTML5 / CSS3 / JavaScript** | Estrutura e interatividade do front-end |
| **Sessions PHP** | Controle de login |
| **Flexbox / Grid** | Layout responsivo e moderno |
