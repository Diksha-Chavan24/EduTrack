# 🚀 EduTrack – Batch Management Portal

EduTrack is a **Java-based backend application** developed using **Spring Boot and MongoDB**. It provides RESTful APIs for managing classroom batch records using complete **CRUD (Create, Read, Update, Delete)** operations.

The project follows a **layered architecture** consisting of the Controller, Service, Repository, and Database layers.

---

## 📌 Overview

EduTrack is designed to provide a simple and efficient backend system for managing educational batches.

The application allows users to:

* Create new batches
* View all available batches
* View a specific batch by ID
* Update existing batch information
* Delete batches

The application exposes REST APIs that can be tested using **Postman, cURL, or IntelliJ HTTP Client**.

---

## 🧠 Tech Stack

| Technology              | Purpose                       |
| ----------------------- | ----------------------------- |
| **Java**                | Programming Language          |
| **Spring Boot**         | Backend Framework             |
| **Spring Data MongoDB** | Database Access               |
| **MongoDB**             | NoSQL Database                |
| **REST API**            | Communication/API Layer       |
| **Maven**               | Build & Dependency Management |
| **Lombok**              | Code Simplification           |
| **Postman**             | API Testing                   |

### Architecture

**Layered Architecture**

```text
REST Client / Postman
        |
        v
Controller Layer
        |
        v
Service Layer
        |
        v
Repository Layer
        |
        v
MongoDB Database
```

---

# ✨ Features

## 📚 Batch Management

* ✅ Create a new batch
* ✅ View all batches
* ✅ View a batch by ID
* ✅ Update an existing batch
* ✅ Delete a batch

## 🔁 CRUD Operations

| Operation       | HTTP Method | Endpoint           |
| --------------- | ----------- | ------------------ |
| Create Batch    | `POST`      | `/batches`         |
| Get All Batches | `GET`       | `/batches`         |
| Get Batch by ID | `GET`       | `/batches/id/{id}` |
| Update Batch    | `PUT`       | `/batches/id/{id}` |
| Delete Batch    | `DELETE`    | `/batches/id/{id}` |

---

# 🏗️ Project Architecture

EduTrack follows a layered backend architecture.

```text
                    REST Client / Postman
                            |
                            v
                 +-----------------------+
                 |   Controller Layer    |
                 +-----------------------+
                            |
                            v
                 +-----------------------+
                 |     Service Layer     |
                 +-----------------------+
                            |
                            v
                 +-----------------------+
                 |   Repository Layer    |
                 +-----------------------+
                            |
                            v
                 +-----------------------+
                 |   MongoDB Database    |
                 +-----------------------+
```

## 1️⃣ Controller Layer

The Controller layer handles incoming HTTP requests and sends appropriate responses.

Responsibilities:

* Defines REST API endpoints
* Accepts client requests
* Sends HTTP responses
* Communicates with the Service layer

---

## 2️⃣ Service Layer

The Service layer contains the application's business logic.

Responsibilities:

* Processes requests received from the Controller
* Implements application logic
* Communicates with the Repository layer
* Acts as an intermediate layer between Controller and Repository

---

## 3️⃣ Repository Layer

The Repository layer handles communication with MongoDB.

It uses **Spring Data MongoDB** to perform database operations such as:

* Insert
* Find
* Update
* Delete

Spring Data provides built-in repository functionality, reducing the amount of database-related code required.

---

## 4️⃣ MongoDB Database

MongoDB is used as the persistent NoSQL database.

Batch information is stored as MongoDB documents inside a collection.

---

# 🗄️ Database

EduTrack uses **MongoDB** for persistent data storage.

### Database Configuration

| Property   | Value                 |
| ---------- | --------------------- |
| Database   | `MarvellousFullStack` |
| Collection | `BatchDetails`        |
| Host       | `localhost`           |
| Port       | `27017`               |

MongoDB connection:

```text
mongodb://localhost:27017
```

---

# 📊 Data Model

The current Batch entity contains the following fields:

```text
Batch
├── id
├── name
└── fees
```

### Example Batch Document

```json
{
  "name": "Java Full Stack",
  "fees": 25000
}
```

---

# 📦 Project Structure

```text
EduTrack
│
├── .mvn/
│   └── wrapper/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── ...
│       │       ├── Controller/
│       │       ├── Service/
│       │       ├── Repository/
│       │       └── Entity/
│       │
│       └── resources/
│           └── application.properties
│
├── .gitattributes
├── .gitignore
├── mvnw
├── mvnw.cmd
├── pom.xml
└── README.md
```

---

# ⚙️ Prerequisites

Before running the project, make sure the following software is installed:

* ☑️ Java JDK
* ☑️ Maven
* ☑️ MongoDB
* ☑️ Git
* ☑️ IntelliJ IDEA / Eclipse / VS Code

You can verify Java installation using:

```bash
java -version
```

Verify Maven using:

```bash
mvn -version
```

---

# ▶️ How to Run

## 1️⃣ Clone the Repository

Clone the EduTrack repository:

```bash
git clone https://github.com/YOUR-USERNAME/EduTrack.git
```

Navigate into the project directory:

```bash
cd EduTrack
```

> Replace `YOUR-USERNAME` with your GitHub username.

---

## 2️⃣ Start MongoDB

Make sure MongoDB is running locally on:

```text
mongodb://localhost:27017
```

---

## 3️⃣ Run the Spring Boot Application

### Windows

You can use the Maven Wrapper:

```cmd
mvnw.cmd spring-boot:run
```

Or, if Maven is installed globally:

```cmd
mvn spring-boot:run
```

---

## 4️⃣ Application URL

Once the application starts successfully, it will be available at:

```text
http://localhost:8080
```

---

# 🧪 API Testing

The REST APIs can be tested using:

* Postman
* cURL
* IntelliJ HTTP Client
* Any REST API testing tool

---

# 🔗 REST API Endpoints

## 1. Create Batch

**POST**

```text
http://localhost:8080/batches
```

### Request Body

```json
{
  "name": "Java Full Stack",
  "fees": 25000
}
```

---

## 2. Get All Batches

**GET**

```text
http://localhost:8080/batches
```

This endpoint returns all available batch records.

---

## 3. Get Batch by ID

**GET**

```text
http://localhost:8080/batches/id/{id}
```

Example:

```text
http://localhost:8080/batches/id/1
```

---

## 4. Update Batch

**PUT**

```text
http://localhost:8080/batches/id/{id}
```

### Example Request Body

```json
{
  "name": "Advanced Java Full Stack",
  "fees": 30000
}
```

---

## 5. Delete Batch

**DELETE**

```text
http://localhost:8080/batches/id/{id}
```

Example:

```text
http://localhost:8080/batches/id/1
```

---

# 📋 API Summary

| Method   | Endpoint           | Description        |
| -------- | ------------------ | ------------------ |
| `POST`   | `/batches`         | Create a new batch |
| `GET`    | `/batches`         | Get all batches    |
| `GET`    | `/batches/id/{id}` | Get batch by ID    |
| `PUT`    | `/batches/id/{id}` | Update batch       |
| `DELETE` | `/batches/id/{id}` | Delete batch       |

---

# 🔄 Application Flow

When a client sends a request, it follows this flow:

```text
Client
  |
  | HTTP Request
  v
Controller
  |
  | Method Call
  v
Service
  |
  | Database Operation
  v
Repository
  |
  | Query
  v
MongoDB
  |
  | Result
  v
Repository
  |
  v
Service
  |
  v
Controller
  |
  | HTTP Response
  v
Client
```

This separation makes the application easier to maintain, test, and extend.

---

# 🛠️ Key Concepts Demonstrated

This project demonstrates practical implementation of:

* Java Programming
* Spring Boot
* REST API Development
* CRUD Operations
* MongoDB Integration
* Spring Data MongoDB
* Layered Architecture
* Dependency Injection
* Lombok
* Maven Project Management
* Backend Application Development
* NoSQL Database Management

---

# 🎯 Learning Objectives

The main learning objectives of this project are:

1. Understand Spring Boot application development.
2. Build RESTful APIs using Spring Boot.
3. Implement CRUD operations.
4. Connect a Spring Boot application with MongoDB.
5. Use Spring Data MongoDB repositories.
6. Understand layered backend architecture.
7. Apply dependency injection.
8. Manage Java dependencies using Maven.
9. Use Lombok to reduce boilerplate code.
10. Test REST APIs using Postman or other API testing tools.

---

# 🚀 Future Enhancements

The application can be extended with additional functionality such as:

* 👨‍🎓 Student Management
* 👨‍🏫 Trainer Management
* 🔗 Student-to-Batch Mapping
* 🔐 Authentication and Authorization
* 🛡️ Input Validation
* ⚠️ Global Exception Handling
* 📖 Swagger/OpenAPI Documentation
* 🔎 Pagination and Search
* 💻 Java CLI Client
* 🌐 Web-based Frontend
* 👥 Role-Based Access Control
* 📊 Dashboard and Reporting

---

# 🔮 Future Architecture

With additional modules, the application can evolve into a complete educational management system:

```text
                         EduTrack
                            |
          +-----------------+-----------------+
          |                 |                 |
          v                 v                 v
     Batch Module      Student Module     Trainer Module
          |                 |                 |
          +-----------------+-----------------+
                            |
                            v
                    Service Layer
                            |
                            v
                   Repository Layer
                            |
                            v
                        MongoDB
```

---

# 📌 Project Highlights

* ✅ Java-based backend
* ✅ Spring Boot REST APIs
* ✅ MongoDB NoSQL database
* ✅ Complete CRUD implementation
* ✅ Layered architecture
* ✅ Spring Data MongoDB
* ✅ Lombok integration
* ✅ Maven project
* ✅ REST API testing support
* ✅ Easily extensible architecture

---

# 👩‍💻 Author

**Diksha Chavan**

Computer Engineering Student

---

# ⭐ Conclusion

EduTrack demonstrates the development of a **RESTful backend application using Java, Spring Boot, and MongoDB**.

The project provides a practical implementation of **CRUD operations, layered architecture, dependency injection, Spring Data MongoDB, and REST API development**.

The modular architecture makes EduTrack easy to maintain and provides a strong foundation for developing a complete **Educational Batch Management System** in the future.

---

⭐ **If you find this project useful, consider giving the repository a star!**
