# CRUD Inline - Sistema PHP com Bootstrap

Sistema de gestão CRUD (Create, Read, Update, Delete) implementado em
**PHP** com interface **inline**, permitindo edição direta nas tabelas.

## 📁 Estrutura do Projeto

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

## 🛠️ Tecnologias Utilizadas

-   PHP 7+ com PDO\
-   MySQL\
-   Bootstrap 5.3.3\
-   HTML5 e CSS3

## 📋 Funcionalidades

### 🔐 Sistema de Autenticação

-   Página de login com validação de credenciais
-   Redirecionamento para página de erro em caso de falha
-   Uso de prepared statements contra SQL Injection

### 🎓 Módulo de Alunos

-   Listagem completa
-   Criação via formulário
-   Edição inline
-   Eliminação com confirmação
-   Validação e sanitização

### 📦 Módulo de Produtos

-   Listagem completa
-   Criação via formulário
-   Edição inline
-   Eliminação com confirmação
-   Validação de preço positivo

## 🔧 Configuração

### 1. Base de Dados

Importar o ficheiro `schema.sql`.

### 2. Configuração da Conexão

``` php
$pdo = new PDO(
    "mysql:host=SEU_HOST;dbname=SEU_DATABASE;charset=utf8",
    "SEU_USUARIO",
    "SUA_SENHA"
);
```

### 3. Tabelas Necessárias

``` sql
CREATE TABLE alunos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL,
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    produto VARCHAR(100) NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE utilizadores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);
```

## 🚀 Como Usar

### Gestão de Alunos e Produtos

-   Criar novos registos
-   Editar diretamente na tabela
-   Eliminar com confirmação

## 🔒 Segurança

-   Prepared statements
-   Sanitização de dados
-   Validação de inputs
-   Sessões PHP

## 🎨 Interface

-   Design responsivo com Bootstrap 
-   Navbar fixa e navegação intuitiva
-   Formulários com validação
-   Tabelas com edição inline

