
# Student Management System (CRUD)

This is a simple CRUD web application built with Spring Boot, Spring Data JPA and Thymeleaf. It allows adding, viewing, updating, and deleting student records.

This repository was prepared for an internship project. The app uses an in-memory H2 database by default for development, so you can run it locally without installing MySQL.

## Quick start (Windows / PowerShell)

Prerequisites
- Java 17 or newer installed (the project targets Java 17). JDK 23 is fine for development.
- Git (to clone or push your repo)

Build and run
```powershell
# (optional) set JAVA_HOME for this session (adjust if different)
$env:JAVA_HOME = 'C:\Program Files\Java\jdk-23'
$env:Path = "$env:JAVA_HOME\bin;$env:Path"

# build (downloads dependencies)
.\mvnw.cmd clean package -DskipTests

# run (dev)
.\mvnw.cmd spring-boot:run

# or run the packaged jar
java -jar .\target\student-management-system-crud-0.0.1-SNAPSHOT.jar
```

Open the UI
- Application: http://localhost:8080/students
- H2 console (dev): http://localhost:8080/h2-console (JDBC URL: `jdbc:h2:mem:smsdb`, user: `sa`, password: empty)

Configuration
- Default DB: `src/main/resources/application.properties` is configured to use H2 for development. If you want to connect to MySQL, update the `spring.datasource.*` properties and create the database.

Security / secrets
- Do not commit real database credentials. If you switch to MySQL, prefer environment-specific properties (profiles) or environment variables.

Making this repo your own
- If you cloned a source repo, change the `origin` remote to your new repository before pushing:
```powershell
git remote set-url origin https://github.com/YourUser/student-management-system.git
git push -u origin main
```

Continuous integration (included)
- This project includes a GitHub Actions workflow that runs `mvn -B package -DskipTests` on push and PR to verify the build.

Notes for reviewers
- The project targets Java 17 for compatibility. It builds and runs with Java 23 locally but leaving `java.version` as 17 increases portability.

If you want I can add a couple of simple unit tests or a short demo script — tell me which and I will add them.

---

Maintainer: Rajat Pandey


