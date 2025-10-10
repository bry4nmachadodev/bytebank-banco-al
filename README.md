# ByteBank - Projeto Java com JDBC

![Java](https://img.shields.io/badge/Java-17-blue) ![MySQL](https://img.shields.io/badge/MySQL-8.0-green) ![JDBC](https://img.shields.io/badge/JDBC-Yes-orange)

---

## Descrição

O **ByteBank** é um projeto de estudo desenvolvido em **Java puro com JDBC** que simula operações básicas de um banco digital, como:

- Abertura e encerramento de contas
- Saque e depósito
- Transferências entre contas
- Consulta de saldo
- Listagem de contas ativas
- Encerramento lógico de contas

O projeto utiliza **MySQL** como banco de dados e demonstra como fazer **CRUDs** e transações utilizando JDBC.

---

## Funcionalidades

- Criar novas contas com dados de cliente (nome, CPF, e-mail)
- Listar todas as contas cadastradas
- Encerrar contas fisicamente (`DELETE`) ou logicamente (`esta_ativa = false`)
- Realizar saques e depósitos
- Realizar transferências entre contas usando **transações** para garantir consistência
- Validações de saldo e valores negativos
- Tratamento de exceções com mensagens amigáveis

---

## Tecnologias

- Java 17
- JDBC
- MySQL 8.0
- HikariCP (gerenciamento de conexão)
- Maven (para gerenciamento de dependências)

---

## Banco de Dados

**Criação da tabela `conta`:**

```sql
CREATE DATABASE IF NOT EXISTS byte_bank;
USE byte_bank;

CREATE TABLE IF NOT EXISTS conta (
  id INT AUTO_INCREMENT PRIMARY KEY,
  numero INT NOT NULL UNIQUE,
  saldo DECIMAL(10,2) NOT NULL,
  cliente_nome VARCHAR(100) NOT NULL,
  cliente_cpf VARCHAR(20) NOT NULL,
  cliente_email VARCHAR(100),
  esta_ativa BOOLEAN DEFAULT TRUE
);
