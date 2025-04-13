-- Create database
CREATE DATABASE company_db;

-- Use the created database
USE company_db;

-- TASK 1: Create employees table
CREATE TABLE employees_tbl (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    employee_name VARCHAR(255) NOT NULL,
    manager_id INT,
    FOREIGN KEY (manager_id) REFERENCES employees_tbl(employee_id)
);

-- TASK 2: Create departments table
CREATE TABLE departments_tbl (
    department_id INT AUTO_INCREMENT PRIMARY KEY,
    department_name VARCHAR(255) NOT NULL
);

-- TASK 4: Create employee_projects table
CREATE TABLE employee_projects (
    employee_id INT,
    project_name VARCHAR(255) NOT NULL,
    FOREIGN KEY (employee_id) REFERENCES employees_tbl(employee_id)
);

-- TASK 5: Create managers table
CREATE TABLE managers_tbl (
    manager_id INT UNIQUE AUTO_INCREMENT PRIMARY KEY,
    employee_id INT,
    FOREIGN KEY (employee_id) REFERENCES employees_tbl(employee_id)
);
