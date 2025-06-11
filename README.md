# Air-Ticket-Reservation-System – Microservices Project

A **Air Ticket Reservation System** built using **Spring Boot Microservices**. The system supports two primary roles: **Admin** and **Passenger**. Each role has dedicated services with secure access using **Spring Security**. The system also supports **H2-Database**, **SonarLint** for Code Quality, and uses **JUnit 5**, **Mockito**, and **JaCoCo** for testing and code coverage.

---

## ⚙️ Technology

| Category        | Technology                          |
|----------------|--------------------------------------|
| Language        | Java 17+                            |
| Framework       | Spring Boot, Spring Cloud           |
| Security        | Spring Security                     |
| Microservices   | Eureka Server, API Gateway          |
| Databases       | H2(in-memory database)              |
| Frontend        | Thymeleaf(HTML), Bootstrap CSS, JS  |
| Testing         | JUnit 5, Mockito                    |
| Code Coverage   | JaCoCo                              |
| Build Tool      | Maven                               |
| REST Client     | RestTemplate                        |

---

## 🧱 Microservices Overview

### 1. Admin Microservice

**Features:**
- Admin login
- View All Passengers
- View All Bookings

### 2. Passenger Microservice

**Features:**
- Register and Login with Spring Security
- Search Available Flights by Route/Date
- Book Flight Tickets
- View Booked Flight Tickets
- Update Profile and Password

---

## 🧱Microservice Architecture
                   +----------------+
                   |  Eureka Server |
                   +--------+-------+
                            |
             +--------------+-------------+
             |                            |
    +--------v--------+          +--------v--------+
    |   Admin Service |          |  User Service   |
    +--------+--------+          +--------+--------+
             \                       /
              \                     /
               \                   /
           +----v-----+    +-------v-----+
           |H2 Database|   |  H2 Database  |
           +----------+    +-------------+
                    |
           +--------v--------+
           |  API Gateway     |
           +------------------+
           

---

## 🧪 Testing and Code Coverage

**Run unit test:**
```bash
mvn test
```

**Run all tests and generate coverage in one step:**
```bash
mvn clean verify
```
**Reports Location:**
```bash
target/site/jacoco/index.html
```

---
## 🔐 JWT Authentication and Security

**Public Endpoints:**

- /admin/login
- /passenger/login

**Secured Endpoints (require JWT token):**

- Admin: /admin/**
- Passenger: /passenger/**, /bookings/**, /flights/**

---

**Token Usage:**
**Include in headers:**

```ardunio
Authorization: Bearer <JWT_TOKEN>
```
---

## 🚀 How to Run the Project

**Start Eureka Server:**

```bash
http://localhost:8761
```

**Start API Gateway:**

```bash
http://localhost:9191
```

**Start Microservices:**

```bash
Admin Service: http://localhost:8081
Passenger Service: http://localhost:8082
```

**Start Config Server:**

```bash
http://localhost:8888/
```

**Start Zipkin Dashboard:**

```bash
http://localhost:9411/
```
---
## 📁 Directory Structure

``` text
air-ticket-reservation-system/
├── eureka-server/
├── ApiGateway/
├── AdminService/
│   ├── conf/
│   ├── controller/
│   ├── service/
│   ├── entity/
│   ├── repository/
├── PassengerService/
│   ├── config/
│   ├── controller/
│   ├── service/
│   ├── entity/
│   ├── repository/
└── ConfigServer/
```

