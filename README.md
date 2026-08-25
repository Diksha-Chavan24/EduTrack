🚀 EduTrack – Batch Management Portal
📌 Overview

EduTrack is a Java-based backend application developed using Spring Boot and MongoDB. It provides RESTful APIs for managing classroom batch records using complete CRUD (Create, Read, Update, Delete) operations.

The project follows a layered architecture consisting of the Controller, Service, Repository, and Database layers.

🧠 Tech Stack
Programming Language: Java
Backend: Spring Boot
Database: MongoDB
Data Access: Spring Data MongoDB
API: RESTful API
Build Tool: Maven
Code Simplification: Lombok
Architecture: Layered Architecture
✨ Features
📚 Batch Management
Create a new batch
View all batches
View a batch by ID
Update an existing batch
Delete a batch
🔁 CRUD Operations
Operation	HTTP Method	Endpoint
Create Batch	POST	/batches
Get All Batches	GET	/batches
Get Batch by ID	GET	/batches/id/{id}
Update Batch	PUT	/batches/id/{id}
Delete Batch	DELETE	/batches/id/{id}
🏗️ Architecture
                REST Client / Postman
                         |
                         v
              Spring Boot REST Controller
                         |
                         v
                   Service Layer
                         |
                         v
              MongoDB Repository Layer
                         |
                         v
                      MongoDB
Architecture Components
Controller Layer
Handles HTTP requests and responses.
Provides REST API endpoints.
Communicates with the Service layer.
Service Layer
Contains the application's business logic.
Processes requests received from the Controller.
Communicates with the Repository layer.
Repository Layer
Uses Spring Data MongoDB.
Handles database operations.
Provides CRUD functionality for batch records.
MongoDB
Stores batch information as documents.
Provides persistent NoSQL data storage.
🗄️ Database

This project uses MongoDB for persistent data storage.

Database Configuration
Database: MarvellousFullStack
Collection: BatchDetails
Host: localhost
Port: 27017
📊 Data Model

The current Batch entity contains:

Batch
├── id
├── name
└── fees
📦 Project Structure
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
⚙️ Prerequisites

Before running the project, make sure you have the following installed:

Java JDK
Maven
MongoDB
Git
IntelliJ IDEA / Eclipse / VS Code
▶️ How to Run
1. Clone the Repository
git clone https://github.com/YOUR-USERNAME/EduTrack.git

Navigate into the project:

cd EduTrack
2. Start MongoDB

Make sure MongoDB is running locally on:

mongodb://localhost:27017
3. Run the Spring Boot Application

On Windows:

mvnw.cmd spring-boot:run

Or using Maven:

mvn spring-boot:run

The application will start on:

http://localhost:8080
🧪 API Testing

The REST APIs can be tested using:

Postman
cURL
IntelliJ HTTP Client
Any REST API testing tool
Example API Request
GET http://localhost:8080/batches
Create a Batch
POST http://localhost:8080/batches
Content-Type: application/json

Example request body:

{
  "name": "Java Full Stack",
  "fees": 25000
}
🔗 REST API Endpoints
Method	Endpoint	Description
POST	/batches	Create a new batch
GET	/batches	Get all batches
GET	/batches/id/{id}	Get batch by ID
PUT	/batches/id/{id}	Update batch
DELETE	/batches/id/{id}	Delete batch
🎯 Learning Objectives

This project demonstrates practical implementation of:

Java programming
Spring Boot
REST API development
CRUD operations
MongoDB integration
Spring Data MongoDB
Layered architecture
Dependency Injection
Lombok
Maven project management
Backend application development
🚀 Future Enhancements

The project can be extended with the following features:

Student management
Trainer management
Student-to-batch mapping
Authentication and authorization
Input validation
Global exception handling
Swagger/OpenAPI documentation
Pagination and search
Java CLI client
Web-based frontend
Role-based access control
👩‍💻 Author

Diksha Chavan

Computer Engineering Student