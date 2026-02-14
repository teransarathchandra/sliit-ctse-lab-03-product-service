# Product Service - Spring Boot Microservice

A simple RESTful microservice built with Spring Boot for managing products, featuring an H2 in-memory database and Swagger API documentation.

**Module:** Current Trends in Software Engineering (SE4010) - Lab 03

## Tech Stack

- Java 21
- Spring Boot 4.0.2
- Spring Data JPA
- H2 Database (in-memory)
- Springdoc OpenAPI (Swagger UI)
- Maven

## Prerequisites

- Java 21 or higher
- Maven 3.9+ (or use the included Maven Wrapper)

## Getting Started

### Clone the repository

```bash
git clone https://github.com/teransarathchandra/sliit-ctse-lab-03-product-service.git
cd sliit-ctse-lab-03-product-service
```

### Build the project

```bash
./mvnw clean install
```

### Run the application

```bash
./mvnw spring-boot:run
```

The application starts on **http://localhost:8080**

## API Endpoints

| Method | Endpoint             | Description          |
|--------|----------------------|----------------------|
| POST   | `/api/products`      | Create a new product |
| GET    | `/api/products`      | Get all products     |
| GET    | `/api/products/{id}` | Get product by ID    |
| DELETE | `/api/products/{id}` | Delete product by ID |

### Sample Request

```bash
# Create a product
curl -X POST http://localhost:8080/api/products \
  -H "Content-Type: application/json" \
  -d '{"name": "Laptop", "price": 999.99}'

# Get all products
curl http://localhost:8080/api/products

# Get product by ID
curl http://localhost:8080/api/products/1

# Delete product
curl -X DELETE http://localhost:8080/api/products/1
```

## H2 Database Console

Access the H2 web console at: **http://localhost:8080/h2-console**

| Property    | Value                  |
|-------------|------------------------|
| JDBC URL    | `jdbc:h2:mem:productdb`|
| Username    | `sa`                   |
| Password    | *(empty)*              |

## Swagger UI

API documentation is available at: **http://localhost:8080/swagger-ui.html**

OpenAPI JSON spec: **http://localhost:8080/v3/api-docs**

## Project Structure

```
src/main/java/com/sliit/product_service/
├── ProductServiceApplication.java      # Spring Boot entry point
├── controller/
│   └── ProductController.java          # REST API endpoints
├── model/
│   └── Product.java                    # JPA entity
└── repository/
    └── ProductRepository.java          # Data access layer
```
