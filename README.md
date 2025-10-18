# Spring Boot JWT Authentication & Role-Based Authorization

Proyek ini adalah contoh implementasi **Spring Boot REST API** dengan fitur:
- **Autentikasi JWT (JSON Web Token)**
- **Role-based Access Control (Admin & User)**
- **CRUD untuk Product**
- **Integrasi Database MySQL**
- **Struktur kode modular dan clean architecture**

## Struktur Proyek

src/main/java/com/example/app/
│
├── config/
│   └── SecurityConfig.java
│
├── security/
│   ├── JwtAuthFilter.java
│   └── JwtUtil.java
│
├── user/
│   ├── User.java
│   ├── UserRepository.java
│   └── UserService.java
│
├── auth/
│   ├── AuthController.java
|	LoginRequest.java	
│   └── RegisterRequest.java
│
├── product/
│   ├── Product.java
│   ├── ProductRepository.java
│   ├── ProductService.java
│   └── ProductController.java
│
└── resources/
    └── application.properties

## Persiapan & Instalasi

### syarat
Pastikan kamu sudah menginstal:
- JDK 17+
- Apache Maven
- MySQL Server
- Postman

### Setup Database

Buat database di MySQL:
```sql
CREATE DATABASE appdb;
```

Lalu ubah konfigurasi di `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/spring_jwt_crud?useSSL=false&serverTimezone=Asia/Jakarta
spring.datasource.username=root
spring.datasource.password=
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

jwt.secret=secretKeyForJWT12345
jwt.expiration=3600000

### Jalankan Proyek

bash
mvn spring-boot:run

Aplikasi berjalan di: http://localhost:8080


### Product CRUD

| Endpoint | Method | Role |
|-----------|---------|------|
| /api/products | GET | ADMIN, USER |
| /api/products/{id} | GET | ADMIN, USER |
| /api/products | POST | ADMIN, USER |
| /api/products/{id} | PUT | ADMIN |
| /api/products/{id} | DELETE | ADMIN |

## Teknologi
- Spring Boot 3.2.5
- Spring Security
- JWT
- MySQL
- JPA
- Lombok

## Developer
**Nama: Mochamad Raihan Siddiq  
**Role: Backend 
**Framework: Spring Boot  
**Database: MySQL  
