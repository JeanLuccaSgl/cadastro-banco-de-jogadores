# Cadastro de Jogadores

Sistema web em PHP para cadastro de usuários com armazenamento em MySQL.

## Objetivo

Gerenciar o registro de jogadores em uma rede social ou plataforma de jogos, permitindo cadastro com nome de usuário e senha.

## Funcionalidades

- Cadastro de usuários com nome e senha
- Conexão segura com banco de dados MySQL
- Redirecionamento automático após cadastro
- Prevenção contra SQL Injection com `real_escape_string`

## Tecnologias

- PHP 8+
- MySQL
- HTML5

## Arquitetura

Aplicaçao monolítica em PHP com HTML embutido. O cadastro é processado no servidor e os dados são persistidos no MySQL.

```
cadastro_jogadores/
├── cadastrarBanco.php   # Script principal de cadastro
├── script_sql_dbJogadores.png  # Modelo do banco de dados
├── README.md
└── .gitignore
```

## Instalação

1. Certifique-se de ter PHP e MySQL instalados.
2. Crie o banco de dados `rede` no MySQL.
3. Execute a query de criação da tabela `usuario`:

```sql
CREATE TABLE usuario (
    idUsuario INT AUTO_INCREMENT PRIMARY KEY,
    nomeUsuario VARCHAR(100) NOT NULL,
    senha VARCHAR(255) NOT NULL,
    dataCadastro DATE NOT NULL,
    ativo CHAR(1) NOT NULL DEFAULT 's'
);
```

4. Configure o arquivo `cadastrarBanco.php` com suas credenciais MySQL:

```php
$hostname = "127.0.0.1";
$user = "seu_usuario";
$password = "sua_senha";
$database = "rede";
```

## Execução

Inicie o servidor embutido do PHP:

```bash
php -S localhost:8000
```

Acesse `http://localhost:8000/cadastrarBanco.php` no navegador.

## Conhecimentos demonstrados

- Programação web com PHP
- Integração com banco de dados MySQL
- Tratamento de formulários HTML
- Segurança básica (SQL Injection)
- Manipulação de datas em PHP

## Melhorias futuras

- Implementar autenticação com sessões
- Adicionar validação de dados no cliente
- Melhorar interface com CSS
- Adicionar listagem e edição de usuários
- Utilizar prepared statements para maior segurança

## Licença

MIT
