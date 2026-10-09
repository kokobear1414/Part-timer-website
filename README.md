# Part-Timer

Part-Timer is a simple job portal web app. Companies post part-time and full-time jobs, job seekers browse and apply for them, and an admin manages the whole system.

## What the System Does

The app has **3 types of users**. Each one sees their own dashboard after logging in.

### 👤 Job Seeker (User)
- Register and log in
- Browse available jobs
- Apply for jobs
- See their applications and status (Pending / Accepted / Rejected)
- Withdraw one application or all of them
- Update their profile

### 🏢 Company
- Log in to a company dashboard
- Post new jobs
- Edit or delete their jobs
- See who applied to their jobs
- Accept or reject applicants
- Update the company profile

### 🛠️ Admin
- View, add, edit and delete users
- View and delete companies
- View all jobs in the system

## Tech Stack

| Part | Technology |
|---|---|
| Language | Java 17 |
| Framework | Spring Boot 3.5 |
| Web | Spring Web (MVC) |
| Security / Login | Spring Security |
| Database access | Spring Data JPA (Hibernate) |
| Database | H2 (in-memory) |
| Frontend | Thymeleaf, HTML, CSS, Bootstrap 5 |
| Build tool | Maven |

## How to Run

**You need:** Java 17 or newer.

1. Clone the project:
   ```bash
   git clone <your-repo-url>
   cd part-timer
   ```
2. Start the app:
   ```bash
   # Windows
   mvnw.cmd spring-boot:run

   # Mac / Linux
   ./mvnw spring-boot:run
   ```
3. Open your browser and go to **http://localhost:9090**

## Demo Accounts

The app loads sample data every time it starts, so you can log in straight away:

| Role | Email | Password |
|---|---|---|
| Admin | bob@example.com | password2 |
| User | alice@example.com | password1 |
| Company | contact@techcorp.com | compassword1 |

## Database

The app uses an **H2 in-memory database**, so you don't need to install a database.
- The data resets every time the app restarts.
- Sample data comes from `src/main/resources/data.sql`.
- To look inside the database, open **http://localhost:9090/h2-console**
  - JDBC URL: `jdbc:h2:mem:jobdb`
  - Username: `sa`
  - Password: `1`

## Project Structure

```
src/main/java/com/csc3402/security/parttimer/
├── config/       # Security and login settings
├── controller/   # Handles web pages and requests
├── dto/          # Objects used to send data to pages
├── model/        # Database tables (User, Company, Job, Application)
├── repository/   # Database queries
└── service/      # Business logic

src/main/resources/
├── templates/    # HTML pages (Thymeleaf)
├── static/       # Images, videos, CSS
├── data.sql      # Sample data
└── application.properties  # App settings
```

> **Note:** This is a learning project. Passwords are stored as plain text to keep it simple, so don't use it for real users without adding password encryption.
