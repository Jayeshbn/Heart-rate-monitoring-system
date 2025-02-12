# Instructions to Set Up and Run the Project

## Prerequisites
Before setting up the project, ensure you have the following installed:
- **Java Development Kit (JDK) 17 or later**
- **Maven (Latest Version)**
- **Spring Boot CLI (Optional, but recommended)**
- **MySQL Database (or any other preferred database)**
- **Postman or any API testing tool**
- **IDE (IntelliJ IDEA, Eclipse, or VS Code with Spring Boot extensions)**

---

## Step 1: Clone the Repository
```sh
 git clone <repository_url>
 cd <project_directory>
```

## Step 2: Configure Database
1. Open `application.properties` or `application.yml` in `src/main/resources/`.
2. Update the database configurations:

For MySQL (application.properties):
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/heart_rate_monitor
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
```

## Step 3: Build and Run the Project
Navigate to the project directory and run the following commands:

### Using Maven:
```sh
mvn clean install
mvn spring-boot:run
```

### Using IDE:
- Open the project in your preferred IDE.
- Run the `main` method inside `HeartRateMonitorApplication.java`.

---

## Step 4: API Endpoints
### 1. User Registration & Login
#### Register User:
```http
POST /api/users/register
```
Request Body (JSON):
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```
#### Login User:
```http
POST /api/users/login
```
Request Body (JSON):
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

### 2. Manage Patients
#### Add Patient:
```http
POST /api/patients
```
Request Body:
```json
{
  "name": "Jane Smith",
  "age": 45,
  "contactNumber": "1234567890"
}
```
#### Get Patient Details:
```http
GET /api/patients/{patientId}
```

### 3. Heart Rate Details
#### Record Heart Rate:
```http
POST /api/heartrate
```
Request Body:
```json
{
  "patientId": 1,
  "heartRate": 75,
  "timestamp": "2025-02-13T12:34:56Z"
}
```
#### Retrieve Heart Rate Data:
```http
GET /api/heartrate/{patientId}
```

---

## Step 5: Running Tests (Optional)
To run unit tests:
```sh
mvn test
```

---

## Step 6: Stopping the Application
To stop the Spring Boot application running in the terminal:
```sh
CTRL+C
```

---

## Additional Notes
- You can use **Postman** to test the API endpoints.
- Make sure MySQL is running before starting the application.
- Extend functionality by implementing authentication, authorization, or additional features as needed.

### Happy Coding! 🚀

