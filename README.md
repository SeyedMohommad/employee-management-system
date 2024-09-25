# Employee Management System

This is a simple **Employee Management System** built using **Spring Boot** and **Hibernate (JPA)**. The application provides RESTful APIs to perform CRUD operations on employee data. It includes features for adding, retrieving, updating, and deleting employee records in a relational database.

## Features

- Add a new employee.
- Get all employees.
- Get employee by ID.
- Update employee information.
- Delete an employee.

## Technologies Used

- **Java 11** or later
- **Spring Boot 2.5** or later
    - Spring Web (REST API development)
    - Spring Data JPA (Hibernate ORM for database interaction)
- **Hibernate** (Object-Relational Mapping)
- **MySQL** (or H2 for in-memory database during development)
- **JUnit 5** (for unit testing)
- **Mockito** (for mocking dependencies in tests)
- **Maven** (for project management)

## Project Structure
```
EmployeeManagementSystem/
├── .idea/                   # IntelliJ IDEA specific files
├── .mvn/                    # Maven wrapper files
├── src/
│    ├── main/
│    │    ├── java/
│    │    │    └── com/SeyedMohammad/EmployeeManagementSystem/
│    │    │         ├── EmployeeManagementApplication.java  # Main class to run the Spring Boot application
│    │    │         ├── controller/
│    │    │         │    └── EmployeeController.java        # REST Controller to handle HTTP requests
│    │    │         ├── model/
│    │    │         │    └── Employee.java                  # Employee entity class
│    │    │         ├── repository/
│    │    │         │    └── EmployeeRepository.java        # JPA Repository interface for Employee
│    │    │         └── service/
│    │    │              └── EmployeeService.java           # Business logic service for Employee
│    │    └── resources/
│    │         └── application.properties                   # Configuration for the database and other settings
│    └── test/
│         ├── java/
│         │    └── com/SeyedMohammad/EmployeeManagementSystem/
│         │         ├── EmployeeControllerTest.java         # Unit tests for EmployeeController
│         │         ├── EmployeeServiceTest.java            # Unit tests for EmployeeService
│         │         └── EmployeeManagementSystemApplicationTests.java  # Tests for the Spring Boot application setup
└── pom.xml                  # Maven configuration file
```


### Endpoints

| HTTP Method | URL               | Description                    |
| ----------- | ----------------- | ------------------------------ |
| GET         | /api/employees     | Get all employees               |
| GET         | /api/employees/{id} | Get employee by ID              |
| POST        | /api/employees     | Create a new employee           |
| PUT         | /api/employees/{id} | Update employee information     |
| DELETE      | /api/employees/{id} | Delete employee                 |

## Setup Instructions

### Prerequisites

- Java 11 or later
- Maven
- MySQL (optional: H2 for testing purposes)

### Clone the repository

```bash
git clone https://github.com/your-username/employee-management-system.git
cd employee-management-system
```

## Configure the Database

In the src/main/resources/application.properties file, configure the MySQL (or H2) database connection:
 - For MySQL:
```
spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```
 - For H2 (In-Memory):
```
spring.datasource.url=jdbc:h2:mem:employeedb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=update
```
```bash
mvn spring-boot:run
```

## Example Usage
1. Create a new employee:
```
POST /api/employees
Content-Type: application/json

{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com"
}

```
2. Get all employees:
```
GET /api/employees
```
3. Update an employee:
```
PUT /api/employees/1
Content-Type: application/json

{
  "firstName": "Jane",
  "lastName": "Doe",
  "email": "jane.doe@example.com"
}
```

Author

SeyedMohammad Aminaltolieh 
```
    GitHub: SeyedMohammad
    Email: a.amin771116@yahoo.com
```