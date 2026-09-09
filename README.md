# Student Management API

A beginner-friendly REST API built with **Java 21 + Spring Boot + Spring Data JPA + MySQL**.

## Features

- Create, read, update and delete students
- Request validation
- Global exception handling
- JPA/Hibernate persistence
- Clean Controller → Service → Repository architecture

## Project structure

```text
src/main/java/com/vercetti/studentapi/
├── StudentApiApplication.java
├── controller/
│   └── StudentController.java
├── entity/
│   └── Student.java
├── exception/
│   ├── GlobalExceptionHandler.java
│   └── StudentNotFoundException.java
├── repository/
│   └── StudentRepository.java
└── service/
    └── StudentService.java
```

## Requirements

- Java 21+
- Maven 3.9+
- MySQL 8+

## Database setup

Create the database in MySQL:

```sql
CREATE DATABASE studentdb;
```

The application reads these environment variables when provided:

```text
DB_URL=jdbc:mysql://localhost:3306/studentdb
DB_USERNAME=root
DB_PASSWORD=your_password
```

Do not commit real passwords or secrets to GitHub.

## Run

```bash
mvn spring-boot:run
```

The API starts on `http://localhost:8080` by default.

## API endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/students` | Get all students |
| GET | `/api/students/{id}` | Get one student |
| POST | `/api/students` | Create a student |
| PUT | `/api/students/{id}` | Update a student |
| DELETE | `/api/students/{id}` | Delete a student |

### Example POST body

```json
{
  "name": "Arun Kumar",
  "email": "arun@example.com",
  "department": "Artificial Intelligence and Machine Learning",
  "year": "3rd Year"
}
```

## Architecture

```text
Client
  ↓
StudentController
  ↓
StudentService
  ↓
StudentRepository
  ↓
MySQL
```

## Interview concepts covered

- `@RestController`
- `@RequestMapping`
- `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`
- `@RequestBody` and `@PathVariable`
- Dependency Injection
- Spring Data JPA
- Entity mapping
- Bean Validation
- Exception handling
- REST API status codes
