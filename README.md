
1. Pré-requisitos
Você vai precisar de:
Java JDK 17+
Maven
Uma IDE, como IntelliJ IDEA, Eclipse ou VS Code
Um cliente para testar a API, como Postman ou Insomnia


2. Criar o projeto
A maneira mais fácil é usar o Spring Initializr.

Spring Initializr

Preencha assim:
Project: Maven
Language: Java
Spring Boot: versão estável atual
Group: com.exemplo
Artifact: api
Name: api
Packaging: Jar
Java: 17 ou superior
Adicione as dependências:
Spring Web
Spring Data JPA
Validation
H2 Database — para começar sem precisar instalar um banco

Depois clique em Generate e abra o .zip na sua IDE.

3. Criar a estrutura
src/main/java/com/exemplo/api
├── controller
├── model
├── repository
└── service

4. Criar a Model
Model representa os dados da aplicação.

Exemplo: User pode ter id, nome e email.
Entity indica que a classe representa uma tabela no banco.
Cada objeto do Model representa um registro dessa tabela.

5. Criar o Repository
Repository é responsável pelo acesso ao banco de dados.
Ele permite salvar, buscar, atualizar e excluir dados.

Normalmente usamos JpaRepository.
Ele fornece métodos prontos, como save() e findAll().

Exemplo: UserRepository extends JpaRepository<User, Long>.


7. Criar o Controller

Define as rotas da API:
GET    /users
GET    /users/{id}
POST   /users
DELETE /users/{id}

7. Configurar o banco
Para começar, pode usar H2 no application.properties.
Executar
./mvnw spring-boot:run
Testar
Use Postman/Insomnia para enviar requisições para:
http://localhost:8080/users
