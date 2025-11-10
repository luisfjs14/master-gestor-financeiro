# 💰 Sistema Financeiro Pessoal

Aplicação web desenvolvida para controle financeiro pessoal, com foco em **organização de contas, cartões de crédito, faturas mensais, receitas e despesas**.  
O sistema foi totalmente construído em **PHP + MySQL**, com interface responsiva e moderna em **HTML, CSS e JavaScript puro**.

---

## 🚀 Funcionalidades Principais

### 🧍‍♂️ Autenticação
- Sistema de **login e registro de usuários** com validação de sessão.
- Cada usuário visualiza apenas suas próprias contas, cartões e transações.

### 💳 Controle de Contas
- Cadastro de contas bancárias e carteiras (ex: Conta Corrente, Carteira Física, Nubank, etc.).
- Exibição do saldo em tempo real.
- Atualização automática ao lançar compras em débito, pix ou dinheiro.

### 🧾 Lançamentos Financeiros
- Registro de **compras e receitas** com descrição, valor e data.
- Suporte a quatro formas de pagamento:
  - 💵 **Dinheiro**
  - ⚡ **Pix**
  - 🏦 **Débito**
  - 💳 **Crédito (com parcelamento)**
- Atualização automática dos saldos das contas envolvidas.

### 🧠 Sistema de Crédito com Faturas (Recém-Adicionado)
- Cada **cartão de crédito** possui:
  - Data de **fechamento** e **vencimento** configuráveis.
- O sistema gera **automaticamente as faturas mensais** conforme os lançamentos de crédito.
- As compras parceladas são distribuídas corretamente entre as faturas futuras.
- Visualização completa de todas as faturas:
  - Mês de referência
  - Valor total
  - Lista de lançamentos
- Geração apenas de faturas **que possuem compras** (sem faturas vazias).

### 📊 Dashboard
- Resumo geral com:
  - Saldo total
  - Despesas do mês
  - Projeção de faturas futuras
  - Últimos lançamentos

---

## 🧱 Estrutura do Banco de Dados

Principais tabelas utilizadas:

- **users** — Cadastro e autenticação de usuários  
- **accounts** — Contas bancárias e carteiras  
- **cards** — Cartões de crédito  
- **transactions** — Lançamentos (todas as formas de pagamento)  
- **invoices** — Faturas mensais geradas automaticamente

### Exemplo de colunas importantes

#### `transactions`
| Campo | Tipo | Descrição |
|--------|------|-----------|
| id | INT | Identificador da transação |
| user_id | INT | Dono da transação |
| account_id | INT | Conta vinculada (para débito/pix) |
| card_id | INT | Cartão (para crédito) |
| invoice_id | INT | Fatura relacionada (se crédito) |
| descricao | VARCHAR | Descrição da compra |
| valor | DECIMAL | Valor da transação |
| forma_pagamento | ENUM | dinheiro / pix / debito / credito |
| parcelas | INT | Nº total de parcelas (se houver) |
| parcela_atual | INT | Parcela atual |
| data_compra | DATE | Data da compra |

#### `invoices`
| Campo | Tipo | Descrição |
|--------|------|-----------|
| id | INT | Identificador da fatura |
| user_id | INT | Dono da fatura |
| card_id | INT | Cartão vinculado |
| mes_referencia | VARCHAR(7) | Ex: 2025-11 |
| valor_total | DECIMAL | Total de compras do mês |
| pago | TINYINT(1) | Status da fatura (0 = em aberto, 1 = paga) |

---

## 🧮 Fluxo das Compras no Crédito

1. O usuário lança uma compra com **forma de pagamento = crédito**.  
2. O sistema identifica o **cartão** e suas datas de **fechamento e vencimento**.  
3. Cada parcela da compra é:
   - Atribuída à **fatura do mês correspondente ao vencimento**.
   - Criada automaticamente, caso não exista.
4. O valor da parcela é somado ao **total da fatura**.
5. No painel de cartões, o usuário visualiza todas as faturas ordenadas por mês, com seus lançamentos.

---

## 🖥️ Tecnologias Utilizadas

| Tecnologia | Função |
|-------------|--------|
| **PHP (PDO)** | Lógica do servidor e conexão segura ao banco |
| **MySQL** | Armazenamento de dados |
| **HTML5 / CSS3 / JS** | Estrutura e interatividade do fron
