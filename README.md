# 🧩 Design Patterns - Java Cloud Native

Este projeto é parte do **Lab "Design Patterns"** do **Bootcamp Bradesco - Java Cloud Native** realizado em parceria com a **DIO (Digital Innovation One)**.  
O objetivo principal é demonstrar a aplicação de padrões de projeto no contexto de uma API REST construída com **Spring Boot** e integração com serviços externos utilizando **Feign Client**.

---

## 📌 Descrição

A aplicação expõe uma API RESTful para gerenciamento de clientes, realizando operações de CRUD (Create, Read, Update, Delete) e integração com a API pública do **ViaCEP** para preenchimento automático de dados de endereço via CEP.



## ⚙️ Funcionalidades

- Cadastrar, atualizar, listar e deletar clientes
- Integração com a API do ViaCEP
- Reutilização de endereços já cadastrados (evita chamadas repetidas)
- Uso de padrões como **Strategy**, **Facade**, e **Singleton**

---

## 🛠️ Tecnologias Utilizadas

- Java 17+
- Spring Boot
- Spring Data JPA
- Spring Web
- Feign Client (Spring Cloud OpenFeign)
- H2 Database (para testes locais)
- API pública ViaCEP

---

## ▶️ Como Executar

### Pré-requisitos

- Java 17+
- Maven

### Passos

1. Clone o repositório:

   ```bash
   git clone https://github.com/higorv10/dio-spring.git
   cd dio-spring\demo

   ```
2. Após clonar o repositório, localize o arquivo `DemoApplication.java` no seu diretório local:
   ```css
   [CAMINHO_DO_REPOSITÓRIO]\src\main\java\dio\spring\demo\DemoApplication.java
   ```

2. Execute o projeto:

   ```bash
   ./mvnw spring-boot:run
   ```

3. Caso esteja utilizando o VSCode, basta abrir o projeto, localizar o arquivo `DemoApplication.java` e clicar com o botão direito sobre ele para selecionar a opção Run. O terminal irá exibir as instruções para interagir com a aplicação.

4. Acesse:

  - Swagger/OpenAPI: `http://localhost:8080/swagger-ui.html` (se configurado)

  - Endpoints REST: `http://localhost:8080/clientes`


---

## 🔗 Exemplos de Endpoints
  - `GET /clientes` – Lista todos os clientes

  - `GET /clientes/{id}` – Busca cliente por ID

  - `POST /clientes` – Cria um novo cliente

  - `PUT /clientes/{id}` – Atualiza cliente existente

  - `DELETE /clientes/{id}` – Remove cliente

Exemplo de payload:

```json
{
  "nome": "Maria Oliveira",
  "endereco": {
    "cep": "01001-000"
  }
}

```
---

## 🧠 Padrões de Projeto Aplicados

  - Strategy: Interface ClienteService com implementação ClienteServiceImpl

  - Facade: Integração com a API ViaCEP abstraída pela interface ViaCepService

  - Singleton: Gerenciado via Spring Container

---

## 🗂️ Estrutura do Projeto (simplificada)

```
dio.spring.demo
├── controller
│   └── ClienteRestController.java
├── model
│   ├── Cliente.java
│   ├── Endereco.java
│   ├── ClienteRepository.java
│   └── EnderecoRepository.java
├── service
│   ├── ClienteService.java
│   ├── ClienteServiceImpl.java
│   └── ViaCepService.java
└── DemoApplication.java

```
---

## 📄 Licença
Desenvolvido durante o Bootcamp Bradesco Java Cloud Native na DIO para fins educacionais.









