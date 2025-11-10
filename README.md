# 🩺 Health Care Life Plan

Sistema backend desenvolvido em **Java** com foco na gestão de informações de **usuários**, **consultas médicas** e **receitas**.  
O projeto segue os princípios de **Domain Driven Design (DDD)** e arquitetura em **camadas (DAO, BO, Resource e TO)**, oferecendo uma API RESTful para integração com aplicações web e mobile.

---

## DOCUMENTAÇÃO

Pasta com PDF e DOCX:
https://drive.google.com/drive/folders/1SWy7dLip3hKo6bd0SEs9XgNIfyUOiFCF?usp=sharing


## 📘 Objetivo

O **Health Care Life Plan** tem como objetivo permitir o **cadastro, listagem e gerenciamento** de informações médicas e de usuários.  
O sistema foi construído com **Jakarta EE** e **Maven**, visando escalabilidade, modularidade e fácil manutenção.

---

## 🧩 Estrutura do Projeto

```
src/main/java/br/com/fiap
│
├── bo/           # Camada de regras de negócio (Business Object)
│   ├── ConsultaBO.java
│   ├── ReceitaBO.java
│   └── UsuarioBO.java
│
├── dao/          # Camada de persistência (Data Access Object)
│   ├── ConnectionFactory.java
│   ├── ConsultaDAO.java
│   ├── ReceitaDAO.java
│   └── UsuarioDAO.java
│
├── resource/     # Endpoints REST (API)
│   ├── ConsultaResource.java
│   ├── ReceitaResource.java
│   ├── UsuarioResource.java
│   └── CorsFilter.java
│
└── to/           # Objetos de Transferência de Dados (Transfer Object)
    ├── ConsultaTO.java
    ├── ReceitaTO.java
    └── UsuarioTO.java
```

---

## ⚙️ Tecnologias Utilizadas

- **Java 17+**
- **Jakarta EE / JAX-RS**
- **Maven**
- **REST API**
- **JDBC**
- **Docker (opcional)**

---

## 🚀 Funcionalidades

### 👤 Usuários
- Cadastro, listagem, atualização e exclusão de usuários.
- Validação de dados de entrada.

### 🩺 Consultas Médicas
- Registro de novas consultas.
- Consulta de histórico médico por usuário.

### 💊 Receitas Médicas
- Associação de receitas a consultas e usuários.
- Gerenciamento completo via CRUD.

---

## 🗃️ Modelo de Entidade-Relacionamento (MER)

**Relações principais:**

```
Usuário (1) ─── (N) Consulta (1) ─── (N) Receita
```

| Entidade | Campos principais |
|-----------|------------------|
| **Usuário** | id_usuario, nome, email, senha |
| **Consulta** | id_consulta, data, descricao, id_usuario |
| **Receita** | id_receita, descricao, id_consulta |

---

## 🧠 Arquitetura

O projeto segue a arquitetura em **camadas**, separando responsabilidades:

| Camada | Responsabilidade |
|--------|------------------|
| **Resource** | Receber requisições REST e retornar respostas HTTP |
| **BO (Business Object)** | Aplicar regras de negócio e validações |
| **DAO (Data Access Object)** | Comunicação com o banco de dados via JDBC |
| **TO (Transfer Object)** | Estrutura de dados trafegada entre as camadas |

---

## 🧪 Endpoints Principais

| Método | Endpoint | Descrição |
|---------|-----------|-----------|
| **GET** | `/usuarios` | Lista todos os usuários |
| **POST** | `/usuarios` | Cria um novo usuário |
| **PUT** | `/usuarios/{id}` | Atualiza um usuário existente |
| **DELETE** | `/usuarios/{id}` | Remove um usuário |
| **GET** | `/consultas` | Lista todas as consultas |
| **POST** | `/consultas` | Cadastra uma nova consulta |
| **GET** | `/receitas` | Lista todas as receitas |
| **POST** | `/receitas` | Cadastra uma nova receita |

---

## 🧰 Como Executar o Projeto

### 1️⃣ Pré-requisitos
- Java 17+
- Maven 3.8+
- IDE (IntelliJ / Eclipse / VS Code)
- Servidor compatível com Jakarta EE (Payara, TomEE, Quarkus, etc.)

### 2️⃣ Clonar o repositório
```bash
git clone https://github.com/seu-usuario/healthcare-lifeplan.git
cd healthcare-lifeplan
```

### 3️⃣ Compilar e executar
```bash
mvn clean install
mvn quarkus:dev
```

A aplicação estará disponível em:
```
http://localhost:8080
```

---

## 🧑‍💻 Autores

- **Lucas Tavares Dagrosa** – RM563424  
- **Henrique Gonçalves Pacheco Costa** – RM562086  
- **Leonardo Zerbinatti de Sales** – RM562992

---

## 📄 Licença

Este projeto foi desenvolvido como parte do curso de **Análise e Desenvolvimento de Sistemas** da **FIAP**.  
Uso educacional e acadêmico — distribuição livre com créditos aos autores.
