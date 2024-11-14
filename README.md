# User Management Portal

A **User Management Portal** built with **Spring Boot** for backend functionality, **React + Vite** for frontend UI and **MySQL** as the database. This project provides a RESTful API to manage user data, allowing for **CRUD operations** (Create, Read, Update, Delete) on user profiles. Designed with simplicity and scalability in mind, this application can serve as a foundation for various user-based applications.

## Features

- **User Registration**: Add new users with essential profile details.
- **User Authentication**: Secure login for users using JSON Web Tokens (JWT).
- **Retrieve Users**: Fetch details of all users or a specific user by ID.
- **Update User Information**: Edit user profiles for updated information.
- **Delete Users**: Remove user profiles by ID.
- **Spring Data JPA Integration**: Smooth handling of database interactions.
- **Exception Handling**: Basic error handling for invalid requests.

## Technologies Used

- **Backend**: Java, Spring Boot
- **Database**: MySQL
- **Frontend**: React + Vite
- **Frameworks**: Spring Data JPA, Spring MVC, Spring Web
- **Dependencies**:
    - Spring Boot Starter Data JPA
    - Spring Boot Starter Web
    - MySQL Connector/J
    - Spring Security for authentication

## Getting Started

### Prerequisites

- **Java 11** or later
- **MySQL** installed and running
- **Maven** for dependency management

### Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/user-management-portal.git
   cd user-management-portal
    ```
2. **Configure the Database**:

    Update the `application.properties` file with your MySQL credentials:

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/your_database_name
    spring.datasource.username=your_username
    spring.datasource.password=your_password
    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
    ```
   Replace your_database_name, your_username, and your_password with your MySQL database information. Ensure the MySQL server is running.

3. **Build and Run**

    ```
    mvn clean install
    mvn spring-boot:run
   ```

4. Access the API at: http://localhost:1010/

### API Endpoints

| Method | Endpoint                                | Description                       |
|--------|-----------------------------------------|-----------------------------------|
| POST   | `/auth/register`                        | Register a new user               |
| POST   | `/auth/login`                           | User login and authentication     |
| GET    | `/admin/get-all-user`                   | Retrieve all users (Admin only)   |
| GET    | `/admin/get-user-by-id/{id}`            | Retrieve a specific user by ID    |
| GET    | `/auth/get-info`                        | Retrieve authenticated user's info |
| PUT    | `/auth/update-info`                     | Update authenticated user's info  |
| DELETE | `/admin/delete-user/{id}`               | Delete a user by ID (Admin only)  |

### Sample JSON for User Registration/Update

Use the following JSON structure when registering a new user or updating user information:

```json
{
  "name":"Xyz",
  "email":"xyz@example.com",
  "password": "Xyx@1234",
  "city": "abc",
  "role": "ADMIN"
}
```
### Project Structure

```
src/
├── main/
│   ├── java/com/example/usermanagementportal/
│   │   ├── controller/       # REST controllers for handling API requests
│   │   ├── model/            # User entity for database mapping
│   │   ├── repository/       # Repository interface for CRUD operations
│   │   └── service/          # Business logic services
│   └── resources/
│       └── application.properties  # Configuration file for database and server settings

```

## Future Improvements

- **Email Notifications**: Integrate email triggers for important events, such as user registration confirmations, password resets, and profile updates.
- **Task Assignment System**: Implement a task management module where users can create, assign, and manage tasks. This can include features like setting deadlines, tracking task statuses, and notifications for task-related updates.
- **Enhanced Role-Based Access Control**: Expand on existing user roles (e.g., Admin and User) by adding more granular permissions, allowing finer control over access to different parts of the application.
- **Pagination and Sorting for Large Data Sets**: Implement pagination and sorting for user lists and other large datasets to improve performance and user experience when handling many records.
- **Advanced Search and Filtering**: Enable advanced search options where users can filter results by specific criteria such as name, email, role, and other attributes.
- **Improved Error Handling and Logging**: Implement structured error handling and logging mechanisms for better debugging and to provide clearer error messages to users.
- **Automated Testing**: Develop comprehensive unit and integration tests to ensure the reliability and stability of the application, especially after updates.

## Contribution Guidelines

We welcome contributions! Please fork this repository, make your changes, and submit a pull request with a description of your update.

