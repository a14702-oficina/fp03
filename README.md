CRUD Inline - Sistema PHP com Bootstrap

Sistema de gestão CRUD (Create, Read, Update, Delete) implementado em PHP com interface inline, permitindo edição direta nas tabelas.

📁 Estrutura do Projeto
├── conexao.php              # Configuração da conexão à base de dados
├── index.php                # Página inicial do CRUD (ou página de login)
├── login.php                # Processamento de login
├── erro_login.php           # Página de erro de autenticação
│
├── alunos_form.php          # Formulário para criar novo aluno
├── alunos_inserir.php       # Processa inserção de alunos
├── alunos_editar.php        # Processa edição de alunos
├── alunos_apagar.php        # Processa eliminação de alunos
├── alunos_lista.php         # Lista de alunos com edição inline
│
├── produtos_form.php        # Formulário para criar novo produto
├── produtos_inserir.php     # Processa inserção de produtos
├── produtos_editar.php      # Processa edição de produtos
├── produtos_apagar.php      # Processa eliminação de produtos
└── produtos_lista.php       # Lista de produtos com edição inline

🛠️ Tecnologias Utilizadas

PHP 7+ com PDO

MySQL

Bootstrap 5.3.3

HTML5 e CSS3

📋 Funcionalidades
🔐 Sistema de Autenticação

Página de login com validação de credenciais

Redirecionamento para página de erro em caso de falha

Uso de prepared statements para evitar SQL Injection

🎓 Módulo de Alunos

Listagem: Tabela com todos os alunos

Criação: Formulário para novo aluno

Edição Inline: Alteração direta na tabela

Eliminação: Com confirmação via JavaScript

Validação: Campos obrigatórios e sanitização de dados

📦 Módulo de Produtos

Listagem: Tabela com todos os produtos

Criação: Formulário dedicado

Edição Inline: Alteração direta na linha

Eliminação: Com confirmação via JavaScript

Validação: Preço positivo e campos obrigatórios

🔧 Configuração
1. Base de Dados

Importar o ficheiro schema.sql no phpMyAdmin.

2. Configuração da Conexão

Editar o ficheiro conexao.php:

$pdo = new PDO(
    "mysql:host=SEU_HOST;dbname=SEU_DATABASE;charset=utf8",
    "SEU_USUARIO",
    "SUA_SENHA"
);

3. Tabelas Necessárias
-- Tabela de alunos
CREATE TABLE alunos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL,
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabela de produtos
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    produto VARCHAR(100) NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabela de utilizadores (login)
CREATE TABLE utilizadores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);

🚀 Como Usar
Primeiro Acesso

Aceder a index.php via navegador

Efetuar login com credenciais da tabela utilizadores

Após sucesso, será redirecionado para o dashboard do CRUD

Gestão de Alunos

Aceder a CRUD Inline - Alunos

Criar novo aluno via botão + Novo Aluno

Editar diretamente na tabela

Eliminar com confirmação

Gestão de Produtos

Aceder a CRUD Inline - Produtos

Criar novo produto via + Novo Produto

Editar inline

Eliminar com confirmação

🔒 Segurança

SQL Injection: protegido com prepared statements

XSS: sanitização com htmlspecialchars()

Validação de Inputs no servidor

Sessões PHP para gestão de login

🎨 Interface

Design responsivo com Bootstrap 5

Navbar fixa e navegação intuitiva

Formulários com validação

Tabelas com edição inline

Alertas visuais para confirmação e sucesso
