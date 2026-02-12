#  Inventory Management API  
### Autoflex Technical Challenge

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/SpringBoot-4.0.2-brightgreen)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue)
![Status](https://img.shields.io/badge/Status-Active-success)

##  Overview
The Inventory Management API is a RESTful backend service developed to manage industrial inventory operations. It provides complete control over raw materials, product composition, and production feasibility calculations based on real stock availability.

The main goal of this system is to simulate real industrial decision-making by prioritizing high-value products to maximize potential revenue under stock constraints.

---

##  Core Business Logic
• Full CRUD operations for Raw Materials  
• Full CRUD operations for Products  
• Product composition system (recipe-based structure)  
• Automatic production feasibility calculation  
• Revenue maximization through value-based prioritization  
• Health monitoring endpoint  

---

##  Architecture
The project follows a clean layered architecture pattern:

Controller → Service → Repository → Database

- Controller Layer: Handles HTTP requests and responses  
- Service Layer: Contains business logic and production algorithm  
- Repository Layer: Manages persistence using Spring Data JPA  
- Database Layer: PostgreSQL relational database  

This separation ensures scalability, maintainability, and clarity.

---

##  Technical Stack
- Java 17  
- Spring Boot 4  
- Spring Data JPA  
- PostgreSQL  
- Maven  
- RESTful Architecture  

---

##  Production Algorithm
The system calculates:

• Maximum producible quantity per product  
• Required raw materials for each production batch  
• Total estimated revenue  
• Production priority based on product value  

This guarantees optimal industrial output according to current stock levels.

---

##  Main API Endpoints

Raw Materials:
GET     /raw-materials  
POST    /raw-materials  
PUT     /raw-materials/{id}  
DELETE  /raw-materials/{id}  

Products:
GET     /products  
POST    /products  
PUT     /products/{id}  
DELETE  /products/{id}  

Production Plan:
GET     /production/plan  

Health Check:
GET     /health  

---

##  Installation & Setup

1. Clone the repository:
git clone <repository-url>
cd inventory-api

2. Configure PostgreSQL credentials in:
src/main/resources/application.properties

Example:
spring.datasource.url=jdbc:postgresql://localhost:5432/inventory  
spring.datasource.username=your_user  
spring.datasource.password=your_password  

3. Run the application:
mvn spring-boot:run

The API will start at:
http://localhost:8080

---

##  Example Request

POST /products

{
  "name": "Steel Frame",
  "price": 150.00,
  "recipe": [
    { "rawMaterialId": 1, "quantity": 3 },
    { "rawMaterialId": 2, "quantity": 5 }
  ]
}

---

##  Possible Improvements
- JWT Authentication & Authorization  
- Swagger/OpenAPI documentation  
- Unit & Integration tests  
- Docker containerization  
- Production-grade monitoring (Spring Actuator + Prometheus)  

---
