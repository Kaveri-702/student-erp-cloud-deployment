# Backend – Spring Boot REST API

## Prerequisites
- JDK 17 or higher
- Maven
- MariaDB running with `student_db` created (see [../database/README.md](../database/README.md))

## Step 1: Install Java
```bash
sudo apt update && sudo apt install openjdk-17-jdk -y
java -version
```

## Step 2: Install Maven
```bash
sudo apt install maven -y
mvn -version
```

## Step 3: Configure the database connection
Edit `src/main/resources/application.properties`:
```properties
server.port=8080
spring.datasource.url=jdbc:mariadb://<DB_HOST>:3306/<DB_NAME>
spring.datasource.username=<DB_USER>
spring.datasource.password=<DB_PASS>
```
> Do not commit real passwords. Use placeholders in GitHub.

## Step 4: Build
```bash
cd backend
mvn clean package
```

## Step 5: Run
```bash
cd target/
java -jar <your-jar-file>.jar
```
The API runs on `http://<BACKEND_PUBLIC_IP>:8080`.

## API Endpoints
Fill in the exact paths from your controller:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/... | List all students |
| POST | /api/... | Add a student |
| DELETE | /api/.../{id} | Delete a student |

Test them in Postman and add screenshots to the `screenshots/` folder.

## Security Group
Allow inbound port **8080** only as needed, and SSH (22) only from your IP.
