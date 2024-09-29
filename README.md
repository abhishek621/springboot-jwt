# JWT Authentication with Spring Boot

This project demonstrates a simple JWT (JSON Web Token) authentication mechanism implemented using Spring Boot. The application allows users to register and log in, providing a secure token that can be used for subsequent requests.

## Features

- User registration
- User login
- JWT generation for authenticated users
- Secure API endpoints

## Prerequisites

- Java 17 or later
- Maven
- Spring Boot 3.x
- H2 Database (for development purposes)

## Getting Started

### 1. Clone the Repository

Clone the repository to your local machine:

git clone https://github.com/abhishek621/springboot-jwt.git
cd jwt-authentication-spring-boot

### 2. Build the Application

mvn clean install

### 3. Configure application.properties

Ensure you have the following properties set in your src/main/resources/application.properties file:

spring.h2.console.enabled=true
spring.h2.console.name=testdb
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update

### 4. Run the Application

You can run the application using the following command:

mvn spring-boot:run 

### 5. Access H2 Console (Optional)

http://localhost:8080/h2-console

### 6. ## API Endpoints

The application exposes API endpoints for user authentication

### 7. User Registration

To register a user, send a `POST` request to `/auth/signup` with the following JSON request body:

```json
{
  "username": "user123",
  "password": "password",
  "email": "user@example.com"
}


A successful response will return the newly registered user's details:

{
  "id": 1,
  "username": "user123",
  "email": "user@example.com"
}

User Login : 
To log in a user, send a POST request to /auth/login with the following JSON request body:

{
  "username": "user123",
  "password": "password"
}

A successful login will return a JSON response containing the JWT token and its expiration time:

{
  "token": "your.jwt.token.here",
  "expiresIn": 3600
}