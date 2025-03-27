#Checkpoint 1 - API de Pedidos (Spring Boot)

##Sobre o Projeto
Este projeto faz parte do Checkpoint 1 da disciplina Arquitetura SOA e Web Services na FIAP. O objetivo é desenvolver uma API RESTful utilizando Spring Boot para cadastrar e gerenciar pedidos de clientes.

##Tecnologias Utilizadas
-Java 17
-Spring Boot 3.1
-Spring Web (para expor os endpoints REST)
-Spring Data JPA (para persistência de dados)
-H2 Database (banco de dados em memória)
-Lombok (para reduzir código boilerplate)
-Spring Boot DevTools (para facilitar o desenvolvimento)

##Estrutura do Projeto
📂 src/main/java/br/com/fiap/checkpoint1
├── 📂 controller  # Responsável pelos endpoints
├── 📂 model       # Representação dos dados (Entidades)
├── 📂 repository  # Interface para interação com o banco de dados
├── 📂 service     # Contém as regras de negócio

 ##Configuração do Banco de Dados (H2)
###Configuração do banco H2
datasource.url=jdbc:h2:mem:pedidosdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true

###O console H2 pode ser acessado em http://localhost:8080/h2-console

##Testes Realizados
 - Criar um novo pedido (POST /pedidos)
 - Buscar todos os pedidos (GET /pedidos)
 - Buscar um pedido pelo ID (GET /pedidos/{id})
 - Atualizar um pedido (PUT /pedidos/{id})
 - Deletar um pedido (DELETE /pedidos/{id})

##Autores
- João Pedro Cruz - RM98650
- Tiago Paulino - RM551169
- Victor Eid - RM98668


