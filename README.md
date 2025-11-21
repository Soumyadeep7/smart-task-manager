📌 Smart Task Manager – Spring Boot Project

Smart Task Manager is a Java Spring Boot backend application designed to manage tasks, track priorities, analyze productivity, and automate cleanup actions. It’s built in a production-style architecture suitable for learning, internships, and portfolio projects.

🚀 Features
✔ Task Management

Create, update, delete, and fetch tasks

Priority support: LOW, MEDIUM, HIGH

Status tracking: TODO, IN_PROGRESS, DONE, ARCHIVED

✔ Advanced Querying

Pagination

Sorting

Filter tasks by user

Count completed tasks

✔ Scheduled Jobs

Automatic daily cleanup job that archives tasks older than 30 days.

✔ Clean Architecture

Controller → Service → Repository

Entities + Enums

H2 in-memory database (runs instantly)

MySQL support available

🧠 Tech Stack
Layer	Technology
Language	Java 17
Framework	Spring Boot 3
Database	H2 (default) / MySQL
Build	Maven
Other	Spring Data JPA, Scheduling
📂 Project Structure
smart-task-manager/
 ├── src/main/java/com/smarttask
 │    ├── controller/       # REST endpoints
 │    ├── service/          # Business logic
 │    ├── repository/       # JPA repositories
 │    ├── entity/           # Task + Enums
 │    ├── scheduler/        # Scheduled jobs
 │    ├── SmartTaskApplication.java
 │
 ├── src/main/resources/
 │    ├── application.properties
 │
 ├── pom.xml
 └── README.md

⚙️ Installation & Running
1. Clone this repository
git clone https://github.com/yourusername/smart-task-manager.git
cd smart-task-manager

2. Build & Run
mvn spring-boot:run


The app starts at:

http://localhost:8080

🗄 Database Configuration
Default: H2 In-Memory (Auto-Configured)

No setup required.
Console available at:

http://localhost:8080/h2-console

To enable MySQL instead

Open application.properties and replace:

spring.datasource.url=jdbc:mysql://localhost:3306/smarttask
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update

📡 API Endpoints
Create Task
POST /api/tasks

List Tasks

Supports pagination and sorting:

GET /api/tasks?userId=1&page=0&size=10&sort=priority

Update Task
PUT /api/tasks/{id}

Delete Task
DELETE /api/tasks/{id}

🕒 Scheduled Job (Auto Cleanup)

A daily job runs at 2:00 AM to archive tasks older than 30 days:

0 0 2 * * ?


Implemented in:

TaskCleanupScheduler.java

📘 Future Enhancements

Potential improvements you can add:

JWT authentication (User login system)

Swagger / OpenAPI documentation

Docker setup

React / Angular frontend

Notification/alarm system for due tasks

🤝 Contribution

Feel free to fork, improve, and submit pull requests.

📜 License

This project is open-source and free to use.
