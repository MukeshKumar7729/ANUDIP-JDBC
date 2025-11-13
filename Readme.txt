☕ Employee Management System (JDBC)This project demonstrates a simple Java Console Application that performs CRUD (Create, Read, Update, Delete) operations on an Employee table in a MySQL database using JDBC (Java Database Connectivity).🚀 Key FeaturesDatabase Setup: SQL script to create the Infosys database and Employee table.Connection: Establishes a connection to MySQL using the com.mysql.cj.jdbc.Driver.Menu-Driven Interface: Provides a simple console menu for interacting with the database.CRUD Operations:Insert (Create): Add new employee records.View (Read): Display all employee records.Update: Modify an employee's salary based on their ID.Delete: Remove an employee record based on their ID.Security: Uses PreparedStatement to prevent SQL Injection for all parameterized queries.🛠️ PrerequisitesBefore running this project, ensure you have the following installed and configured:Java Development Kit (JDK) 8+MySQL ServerMySQL Connector/J JDBC Driver (You will need to include the JAR file in your project's classpath/dependencies).⚙️ Setup and Configuration1. Database Setup (MySQL)Run the following SQL script in your MySQL client (e.g., MySQL Workbench, command line) to create the database and table:SQLCREATE DATABASE Infosys;

USE Infosys;

CREATE TABLE Employee (
    eid INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    address VARCHAR(255) NOT NULL,
    salary INT NOT NULL
);

INSERT INTO Employee (name, address, salary) VALUES
('Ravi', 'Chennai', 45000),
('Priya', 'Coimbatore', 52000),
('Arun', 'Madurai', 48000);
2. Java Code ConfigurationYou must update the connection credentials in the EmployeeJDBC.java file:Java// Inside EmployeeJDBC.java
static final String URL = "jdbc:mysql://localhost:3306/Infosys";
static final String USER = "root";
static final String PASS = "YOUR_MYSQL_PASSWORD"; // <-- ⚠️ IMPORTANT: Change this!
Replace "YOUR_MYSQL_PASSWORD" with your actual MySQL root password.🏃 How to RunCompile: Compile the EmployeeJDBC.java file.Run: Execute the compiled class.Follow the on-screen menu to perform operations (Insert, View, Update, Delete, Exit).Example Session OutputA sample run of the application would look like this (simplified):✅ Connected to Infosys database.

📋 MENU:
1. Insert Employee
...
Choose an option: 2

📊 Employee Table:
ID: 1, Name: Ravi, Address: Chennai, Salary: 45000
ID: 2, Name: Priya, Address: Coimbatore, Salary: 52000
ID: 3, Name: Arun, Address: Madurai, Salary: 48000

📋 MENU:
...
Choose an option: 5
👋 Connection closed. Exiting...
📝 Code OverviewThe main class, EmployeeJDBC, contains the following static methods for database interaction:MethodDescriptionJDBC Interface UsedmainApplication entry point; handles connection and main menu loop.Connection, DriverManagerinsertEmployeePrompts for employee details and inserts a new record.PreparedStatementviewEmployeesFetches and prints all records from the Employee table.Statement, ResultSetupdateEmployeePrompts for eid and new salary to update a record.PreparedStatementdeleteEmployeePrompts for eid and deletes the corresponding record.PreparedStatement