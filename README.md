# 💳 Sistema de Gestão Financeira Pessoal

Um sistema web completo para **controle financeiro pessoal**, desenvolvido em **PHP + MySQL**, com interface totalmente **responsiva e moderna**.

---

## 🚀 Funcionalidades Principais

✅ **Controle de contas a pagar e a receber**  
✅ **Cadastro e exclusão de cartões de crédito**  
✅ **Lançamento de compras parceladas no crédito**  
✅ **Visualização automática de faturas mensais**  
✅ **Dashboard com visão geral das finanças**  
✅ **Controle de despesas por categoria e período**  
✅ **Autenticação de usuários (Login e Registro)**  
✅ **Design moderno e responsivo (HTML, CSS, JS)**

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
