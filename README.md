# 💰 Sistema Financeiro Pessoal

![Status](https://img.shields.io/badge/status-Em%20Desenvolvimento-blue)
![PHP](https://img.shields.io/badge/PHP-8.2-%23777BB4)
![MySQL](https://img.shields.io/badge/MySQL-Database-orange)
![License](https://img.shields.io/badge/license-MIT-green)

Aplicação web completa para **controle financeiro pessoal MA$TER**, desenvolvida em **PHP + MySQL**, com interface moderna, responsiva e intuitiva.  
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

## 🧠 Estrutura do Projeto

```
📁 projeto-financeiro/
├── config/
│   └── db.php                # Conexão com o banco de dados
│
├── pages/
│   ├── dashboard.php         # Página principal com resumo financeiro
│   ├── card.php              # Controle e exibição das faturas de cartão
│   ├── add_card.php          # Cadastro de novos cartões de crédito
│   ├── process_lancar_compra.php # Processa os lançamentos de compras
│   ├── lancar_compra.php     # Formulário para registrar uma nova compra
│   ├── login.php             # Tela de login
│   ├── register.php          # Cadastro de usuários
│   └── logout.php            # Encerramento da sessão
│
├── assets/
│   ├── css/                  # Estilos do projeto (design moderno e responsivo)
│   ├── js/                   # Scripts de interação
│   └── img/                  # Imagens e ícones utilizados
│
├── index.php                 # Página inicial (login)
└── README.md                 # Documentação do projeto
```

---

## 🧩 Banco de Dados

**Banco:** `u440974109_financeiro`

Principais tabelas:

- `users`: dados dos usuários cadastrados  
- `cards`: cartões de crédito cadastrados  
- `transactions`: lançamentos de compras e despesas  
- `accounts`: contas de recebimento e pagamento

---

## ⚙️ Tecnologias Utilizadas

| Categoria | Tecnologia |
|------------|-------------|
| Backend | PHP 8.2 |
| Banco de Dados | MySQL |
| Frontend | HTML5, CSS3, JavaScript |
| Estilo | Design Responsivo + CSS personalizado |
| Hospedagem | Hostinger |

---

## 💡 Como Executar o Projeto Localmente

1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/projeto-financeiro.git
   cd projeto-financeiro
   ```

2. Configure o banco de dados no arquivo `config/db.php`:
   ```php
   $host = 'localhost';
   $dbname = 'u440974109_financeiro';
   $username = 'SEU_USUARIO';
   $password = 'SUA_SENHA';
   ```

3. Importe o arquivo SQL (estrutura das tabelas).

4. Inicie o servidor local (por exemplo, com o XAMPP ou Laragon):
   ```bash
   php -S localhost:8000
   ```

5. Acesse o sistema em:
   [http://localhost:8000](http://localhost:8000)

---

## 🧾 Próximas Implementações

🔹 Relatórios financeiros detalhados  
🔹 Exportação de dados em PDF e Excel  
🔹 Dashboard com gráficos interativos  
🔹 Sistema de notificações e metas financeiras  

---

## 👨‍💻 Autor

**Luís Felipe de Jesus Soares**  
💼 Coordenador Financeiro | Desenvolvedor Web  
📧 [Contato via GitHub](https://github.com/seuusuario)

---

## 🪪 Licença

Este projeto está licenciado sob a **MIT License** — sinta-se livre para usar e modificar conforme desejar.
