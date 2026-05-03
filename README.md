# Campus Task Board API – Homework 7

## Project Description

This project is a Spring Boot REST API for managing tasks.

The application supports:

* CRUD operations
* Validation
* DTO architecture
* Global exception handling
* Soft delete
* Request logging
* Health monitoring with Spring Boot Actuator

The project uses:

* Java 21
* Spring Boot 3
* Spring Data JPA
* H2 Database
* Lombok
* Maven

---

# Features

## Task Management

* Create tasks
* View all tasks
* View task by ID
* Update tasks
* Delete tasks (soft delete)
* Restore deleted tasks

## Validation

* Title is required
* Title must be between 3 and 100 characters
* Description maximum length is 500 characters

## Exception Handling

Custom exceptions:

* TaskNotFoundException
* InvalidTaskDataException

Global exception handling using:

* @RestControllerAdvice
* @ExceptionHandler

## Soft Delete

Tasks are not permanently removed from the database.
Instead, deleted tasks are marked with:

```java
private Boolean deleted = true;
```

## Logging Filter

Every request is logged in the console.

Example:

```text
GET /api/tasks - Status: 200 - Duration: 7ms
```

## Actuator Monitoring

Spring Boot Actuator endpoints:

```text
/actuator/health
/actuator/info
/actuator/metrics
```

---

# Technologies Used

* Java 21
* Spring Boot 3.5.13
* Spring Data JPA
* H2 Database
* Lombok
* Maven
* Postman

---

# API Endpoints

## Get All Tasks

```http
GET /api/tasks
```

## Get Task By ID

```http
GET /api/tasks/{id}
```

## Create Task

```http
POST /api/tasks
```

Example JSON:

```json
{
  "title": "Finish Homework",
  "description": "Complete Homework 7",
  "priority": "HIGH"
}
```

## Update Task

```http
PUT /api/tasks/{id}
```

## Delete Task (Soft Delete)

```http
DELETE /api/tasks/{id}
```

## Restore Deleted Task

```http
PUT /api/tasks/{id}/restore
```

## Get Completed Tasks

```http
GET /api/tasks/completed
```

## Get Incomplete Tasks

```http
GET /api/tasks/incomplete
```

## Search Tasks

```http
GET /api/tasks/search?keyword=test
```

## Health Check

```http
GET /actuator/health
```

---

# Error Handling Examples

## 404 Not Found

```json
{
  "status": 404,
  "error": "Not Found",
  "message": "Task with ID 999 not found"
}
```

## 400 Validation Error

```json
{
  "status": 400,
  "error": "Validation Failed"
}
```

---

# How to Run

## Requirements

* Java 21
* Maven

## Steps

Clone repository:

```bash
git clone https://github.com/AndriiVaskivBC/homework7.git
```

Navigate into project:

```bash
cd homework7
```

Run application:

```bash
mvn spring-boot:run
```

Application runs on:

```text
http://localhost:8080
```

---

# H2 Database Console

Open:

```text
http://localhost:8080/h2-console
```

Database URL:

```text
jdbc:h2:mem:taskboarddb
```

Username:

```text
sa
```

Password:

```text
(blank)
```

---

# Homework 7 Requirements Completed

* DTO implementation
* Global exception handling
* Custom exceptions
* Soft delete
* Validation
* Logging filter
* Spring Boot Actuator
* Health monitoring
* GitHub repository
* Postman testing

