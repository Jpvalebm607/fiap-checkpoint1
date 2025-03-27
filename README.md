# Checkpoint 1 - API de Pedidos (Spring Boot)

## 📌 Sobre o Projeto
Este projeto faz parte do Checkpoint 1 da disciplina **Arquitetura SOA e Web Services** na FIAP. O objetivo é desenvolver uma API RESTful utilizando **Spring Boot** para cadastrar e gerenciar pedidos de clientes.

---

## 🛠️ Tecnologias Utilizadas
- **Java 17**
- **Spring Boot 3.1**
- **Spring Web** (para expor os endpoints REST)
- **Spring Data JPA** (para persistência de dados)
- **H2 Database** (banco de dados em memória)
- **Lombok** (para reduzir código boilerplate)
- **Spring Boot DevTools** (para facilitar o desenvolvimento)

---

## 📂 Estrutura do Projeto

```plaintext
📂 src/main/java/br/com/fiap/checkpoint1
├── 📂 controller  # Responsável pelos endpoints
├── 📂 model       # Representação dos dados (Entidades)
├── 📂 repository  # Interface para interação com o banco de dados
├── 📂 service     # Contém as regras de negócio
```

---

## 📌 Endpoints da API

### 📝 Criar um novo pedido
**POST** `/pedidos`
```json
{
  "clienteNome": "João Silva",
  "valorTotal": 150.50
}
```
✅ **Resposta:** `201 Created`
```json
{
  "id": 1,
  "clienteNome": "João Silva",
  "dataPedido": "2025-03-27",
  "valorTotal": 150.50
}
```

---

### 🔍 Buscar todos os pedidos
**GET** `/pedidos`
✅ **Resposta:** `200 OK`
```json
[
  {
    "id": 1,
    "clienteNome": "João Silva",
    "dataPedido": "2025-03-27",
    "valorTotal": 150.50
  }
]
```

---

### 🔎 Buscar um pedido pelo ID
**GET** `/pedidos/{id}`
✅ **Resposta:** `200 OK`
```json
{
  "id": 1,
  "clienteNome": "João Silva",
  "dataPedido": "2025-03-27",
  "valorTotal": 150.50
}
```
❌ **Se o ID não existir:** `404 Not Found`

---

### 🔄 Atualizar um pedido
**PUT** `/pedidos/{id}`
```json
{
  "clienteNome": "Maria Oliveira",
  "valorTotal": 200.00
}
```
✅ **Resposta:** `200 OK`
```json
{
  "id": 1,
  "clienteNome": "Maria Oliveira",
  "dataPedido": "2025-03-27",
  "valorTotal": 200.00
}
```

---

### ❌ Deletar um pedido
**DELETE** `/pedidos/{id}`
✅ **Resposta:** `204 No Content`

---

## ⚙️ Configuração do Banco de Dados (H2)
No arquivo `application.properties`:
```properties
# Configuração do banco H2
datasource.url=jdbc:h2:mem:pedidosdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
```
📌 O console H2 pode ser acessado em **`http://localhost:8080/h2-console`**

---

## 🚀 Como Executar o Projeto
1. **Clone o repositório:**
```sh
git clone https://github.com/seuusuario/fiap-checkpoint1.git
```
2. **Acesse a pasta do projeto:**
```sh
cd fiap-checkpoint1
```
3. **Execute o projeto com Maven:**
```sh
mvn spring-boot:run
```
4. **Acesse a API:**
- **Swagger UI:** `http://localhost:8080/swagger-ui.html`
- **H2 Console:** `http://localhost:8080/h2-console`

---

## ✅ Testes Realizados
✅ **1. Criar um novo pedido** (POST `/pedidos`)
✅ **2. Buscar todos os pedidos** (GET `/pedidos`)
✅ **3. Buscar um pedido pelo ID** (GET `/pedidos/{id}`)
✅ **4. Atualizar um pedido** (PUT `/pedidos/{id}`)
✅ **5. Deletar um pedido** (DELETE `/pedidos/{id}`)

---


## 👨‍💻 Autores
- **João Pedro Cruz** - *RM98650*
- **Tiago Paulino** - *RM551169*
- **Victor Eid** - *RM98668*

