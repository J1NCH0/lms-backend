# 🎓 Learning Management System (LMS) – Backend

A robust backend for a **Learning Management System (LMS)** tailored for schools and universities, developed using **Spring Boot** and **PostgreSQL**. It offers secure user authentication, hierarchical course management, in-person class scheduling, assessments, coding challenges, a leaderboard, and a custom chat service.

---

## 📌 Features

### 🔐 Authentication & ABAC
- OTP-based user registration and login
- JWT-based authentication (access + refresh tokens)
- **Attribute-Based Access Control (ABAC)**:
    - Permissions based on user roles, ownership, and other attributes (e.g., isOwner, isInstructorOfCourse)

### 📚 Learning Structure
- **Courses**: High-level programs (e.g., Software Engineering)
- **Technologies**: Subjects within a course (e.g., Java, Python)
- **Topics**: Units/modules under each technology
- **Meetings**: Scheduled in-person sessions (not online/Zoom-based)
- **Reservations**: Students reserve attendance for scheduled meetings

### 📝 Homework Management
- Topic/meeting-based homework
- File uploads with submission deadlines
- Grading, feedback, and status tracking

### 📁 File Storage
- Upload educational content, homework, and resources
- Configurable: local file system or AWS S3

### 🧪 Quiz Module
- Quizzes associated with topics
- Supports multiple attempts and auto/manual grading
- Score tracking with detailed question analytics

### 💻 Coding Challenge Module
- HackerRank-style problems
- Code execution via an **external service** (e.g., Judge0 API)
- Test case validation, result storage, scoring

### 💬 Custom Chat Microservice
- Built-in messaging microservice (not third-party)
- Real-time chat between students and instructors
- REST/WebSocket based communication

### 🏆 Leaderboard
- Ranking based on:
    - Quiz scores
    - Homework submissions
    - Coding challenge results
- Filterable by course, technology, and topic

---

## 🛠 Tech Stack

| Layer               | Technology                    |
|--------------------|-------------------------------|
| Backend             | Spring Boot (Java 21)        |
| Database            | PostgreSQL                   |
| Authentication      | JWT, OTP (SMS)               |
| Access Control      | **ABAC** (Attribute-Based)   |
| Code Execution      | External API (One Compiler)  |
| Chat                | Custom-built microservice    |
| File Storage        | S3 Storage                   |
| Build Tool          | Maven                        |
| Communication       | REST, WebSocket (chat)       |

---

## ⚙️ Getting Started

### ✅ Prerequisites
- Java 21
- PostgreSQL
- Maven
- One Compiler Executor API
- S3 Storage
- Chat microservice up and running

### 🔧 Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/your-username/lms-backend.git
cd lms-backend
```
2. **Configure environement**
```bash
# Database
spring.datasource.url=jdbc:postgresql://localhost:5432/lms_db
spring.datasource.username=your_username
spring.datasource.password=your_password

# JWT
jwt.secret=your_jwt_secret
jwt.expiration=3600000

# OTP
otp.enabled=true
otp.provider=email # or sms

# File Storage
storage.type=local # or s3
aws.s3.bucket=my-bucket-name
aws.access.key=your-access-key
aws.secret.key=your-secret-key

# Judge0
judge0.api.url=https://api.judge0.com
judge0.api.key=your_judge0_api_key

# Chat Service
chat.service.url=http://localhost:8081
```
3. **Run the application**
```bash
./mvnw spring-boot:run
# or
./gradlew bootRun
```
