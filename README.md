# user-management-system
User Management System
A simple User Management System built with Spring Boot and Thymeleaf. The application allows users to register, log in, and view their profile. The system includes form validation, user authentication, and database integration.

Features
User Registration: Users can sign up by providing their username, email, and password.
Login System: Users can log in with their email and password.
User Profile: After logging in, users can view their profile information.
Form Validation: Basic form validation (e.g., email format, required fields) for login and registration.
Password Encryption: Passwords are stored securely using BCrypt.
Responsive Design: The application is styled with Bootstrap to ensure a responsive UI.
Technologies Used
Spring Boot: Backend framework for creating the application.
Thymeleaf: Java-based template engine for rendering HTML views.
Spring Security: For user authentication and authorization.
Spring Data JPA: For interacting with the database.
H2 Database: In-memory database (can be replaced with MySQL, PostgreSQL, etc.).
Bootstrap: Frontend framework for responsive UI design.
BCrypt: For password hashing.
Prerequisites
Before running the project, ensure you have the following installed:

Java (JDK 11 or higher)
Maven (for building the project)
IDE (e.g., IntelliJ IDEA, Eclipse)
Database (Optional, defaults to H2)
Getting Started
1. Clone the Repository
First, clone the repository to your local machine.

bash
Copy code
git clone https://github.com/yourusername/user-management-system.git
2. Install Dependencies
Navigate to the project directory and run the following command to install the required dependencies:

bash
Copy code
mvn clean install
3. Configure Database (Optional)
If you want to use an external database, configure your application.properties:

properties
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/user_db
spring.datasource.username=root
spring.datasource.password=root
spring.jpa.hibernate.ddl-auto=update
spring.jpa.database-platform=org.hibernate.dialect.MySQL5InnoDBDialect
For an H2 database, the default configuration will work without any changes.

4. Run the Application
Run the Spring Boot application using the following command:

bash
Copy code
mvn spring-boot:run
The application will be accessible at:

Login Page: http://localhost:8080/login
Registration Page: http://localhost:8080/register
Profile Page: http://localhost:8080/profile
5. User Authentication Flow
Go to the login page to sign in using your email and password.
If you don't have an account, go to the register page to create a new account.
After logging in successfully, you will be redirected to the profile page, where you can view your profile information.
6. Stopping the Application
To stop the application, press Ctrl + C in the terminal where the application is running.

Folder Structure
bash
Copy code
user-management-system
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── example
│   │   │           └── userapp
│   │   │               ├── controller
│   │   │               │   └── UserController.java
│   │   │               ├── model
│   │   │               │   └── User.java
│   │   │               ├── repository
│   │   │               │   └── UserRepository.java
│   │   │               ├── service
│   │   │               │   └── UserDetailsServiceImpl.java
│   │   │               └── UserManagementApplication.java
│   │   ├── resources
│   │   │   ├── application.properties
│   │   │   ├── static
│   │   │   └── templates
│   │   │       ├── login.html
│   │   │       ├── register.html
│   │   │       └── profile.html
└── pom.xml
Project Structure
src/main/java/com/example/userapp: Contains the Java classes for your application.

UserController.java: Handles all user-related requests like login, registration, and profile.
User.java: Entity class representing the user.
UserRepository.java: Repository interface for database operations related to users.
UserDetailsServiceImpl.java: Service for loading user details during authentication.
UserManagementApplication.java: The main Spring Boot application class.
src/main/resources/templates: Contains Thymeleaf HTML templates for the views.

login.html: Login page.
register.html: Registration page.
profile.html: User profile page after login.
src/main/resources/application.properties: Configuration file for database, logging, and other Spring settings.

pom.xml: Maven configuration file that defines project dependencies.

Configuration
Database Configuration
The project uses H2 Database by default. You can switch to an external database like MySQL by modifying the application.properties file.

For MySQL, set the following properties:

properties
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/user_db
spring.datasource.username=root
spring.datasource.password=root
spring.jpa.hibernate.ddl-auto=update
Troubleshooting
404 Error: If you see a 404 error for a page, ensure that the controller methods return the correct view name.

Database Connection Issues: Ensure that the database is running (if using MySQL) and that the credentials are correct.
