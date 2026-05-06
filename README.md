# Projeto GM4 System
# 🏥 Sistema GMED

Sistema web desenvolvido para gestão clínica/médica, com foco em controle de usuários, logs e estrutura modular para expansão.

---

## 🚀 Tecnologias Utilizadas

* ☕ Java (Jakarta EE / JSF)
* 🧠 CDI (Contexts and Dependency Injection)
* 🗄️ PostgreSQL
* 🌐 XHTML + CSS3
* ⚙️ Apache Tomcat 10
* 🧩 Maven

---

## 📌 Funcionalidades

### 🔐 Autenticação

* Login de usuários
* Controle de sessão
* Logout seguro

### 👤 Cadastro de Usuários

* Cadastro com validação de CPF
* Geração automática de login
* Ativar / Desativar usuários
* Filtro por:

  * Data
  * Status (Ativo/Inativo)

### 📜 Logs do Sistema

* Registro automático de ações:

  * Login
  * Logout
  * Cadastro
  * Alterações
* Exibição com filtros
* Controle de auditoria completo

### 🖥️ Interface

* Layout moderno estilo sistema web
* Menu lateral com navegação
* Dashboard com atalhos
* Tabelas com scroll e organização

---

## 📂 Estrutura do Projeto

```
gmed/
│
├── src/
│   ├── main/
│   │   ├── java/com/ge/sistema/
│   │   │   ├── model/
│   │   │   ├── usuario/
│   │   │   ├── log/
│   │   │   ├── util/
│   │   │   └── login/
│   │   │
│   │   ├── webapp/
│   │   │   ├── *.xhtml
│   │   │   ├── css/
│   │   │   └── WEB-INF/
│
├── pom.xml
└── README.md
```

---

## ⚙️ Configuração do Ambiente

### 1️⃣ Pré-requisitos

* Java JDK 17+
* Maven instalado
* PostgreSQL instalado
* Tomcat 10 configurado

---

### 2️⃣ Banco de Dados

Crie o banco:

```sql
CREATE DATABASE gmed_db;
```

Tabela de usuários:

```sql
CREATE TABLE usuarios (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(150),
    cpf VARCHAR(14),
    telefone VARCHAR(20),
    login VARCHAR(50),
    senha VARCHAR(100),
    ativo BOOLEAN,
    data_cadastro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Tabela de logs:

```sql
CREATE TABLE logs (
    id SERIAL PRIMARY KEY,
    usuario VARCHAR(50),
    acao VARCHAR(50),
    descricao TEXT,
    ip VARCHAR(50),
    maquina VARCHAR(100),
    tela VARCHAR(50),
    data_hora TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

### 3️⃣ Configuração do Banco no Projeto

Arquivo:

```
UsuarioDAO.java
```

```java
private final String url = "jdbc:postgresql://localhost:5432/gmed_db";
private final String user = "postgres";
private final String pass = "admin";
```

---

### 4️⃣ Rodando o Projeto

```bash
mvn clean install
```

Depois:

* Deploy no Tomcat
* Acesse:

```
http://localhost:8080/gmed
```

---

## 👨‍💻 Como Contribuir

1. Faça um fork do projeto
2. Crie uma branch:

```bash
git checkout -b minha-feature
```

3. Commit suas alterações:

```bash
git commit -m "Minha melhoria"
```

4. Envie:

```bash
git push origin minha-feature
```

5. Abra um Pull Request

---

## 📌 Padrões do Projeto

* Código organizado por camadas (DAO, Bean, Model)
* Uso de logs para auditoria
* Interface padronizada
* Nomes claros e objetivos

---

## 🔒 Segurança (Melhorias Futuras)

* Criptografia de senha (BCrypt)
* Controle de perfil de acesso
* Proteção contra SQL Injection (já usando PreparedStatement)
* JWT ou sessão avançada

---

## 📈 Roadmap

* [ ] Agenda médica
* [ ] Cadastro de pacientes
* [ ] Prontuário eletrônico
* [ ] Relatórios avançados
* [ ] Dashboard com gráficos

---

## 🧑‍💼 Autor

Desenvolvido por **Jonathan Carlos Alves**
📍 Goiânia - GO

---

## 📄 Licença

Este projeto está sob a licença MIT.

---

## ⭐ Apoie o Projeto

Se esse projeto te ajudou:

👉 Deixe uma estrela no repositório
👉 Compartilhe com outros devs

---

💡 *Sistema em evolução contínua*
