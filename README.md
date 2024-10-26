# Employee-Management-System-Using-Python-and-MySQL
Manage employee records efficiently with this Employee Management System, a Python program backed by a MySQL database. This system offers essential functions for adding, displaying, updating, removing, and searching for employee records.
# Features
- Add Employees: Easily input employee details, including name, email, phone number, address, post, and salary.

- Display Records: View a list of all employee records in an organized manner.

- Update Information: Modify employee records by updating their email, phone number, and address.

- Remove Records: Delete employee records when they are no longer needed.

- Search Functionality: Find employee records based on their unique employee ID, name, manager ID etc.

- User-Friendly Interface: A menu-driven interface makes navigation and data management a breeze.
# Prerequisites
Before you get started, ensure you have the following components installed on your system:

1.Python (3.x): Download Python

2.tkinter library: You can install it using pip:

- pip install tk

3.MySQL Database: Download MySQL

4.MySQL Connector for Python: You can install it using pip:

- pip install mysql-connector-python
# Database Setup
Before using the system, you need to set up the MySQL database and table. Follow these steps:

1.Log in to MySQL as the root user.

2.Create the 'employee_management_system' Database.

3.Switch to the 'employee_management_system' Database:

4.Create the following Table:

 - CREATE TABLE employee (
 Emp_ID INT AUTO_INCREMENT PRIMARY KEY,  
 Manager_ID INT,                                                     
 Department VARCHAR(50),                 
Designation VARCHAR(50),                
Name VARCHAR(50),                       
Mobile_Number VARCHAR(15),              
DOJ DATE,                                                                     
Email VARCHAR(100),                     
Country VARCHAR(50),                    
City VARCHAR(50),                       
Married_Status VARCHAR(50),             
DOB DATE,                                                                     
ID_Type VARCHAR(50),                    
ID_Proof VARCHAR(100),                  
Gender VARCHAR(10),                     
Salary DECIMAL(10, 2),                                               
Password VARCHAR(50)
);
CREATE TRIGGER generate_password_before_insert 
BEFORE INSERT ON employee 
FOR EACH ROW 
SET NEW.Password = CONCAT(UPPER(SUBSTRING(NEW.Name, 1, 4)), YEAR(NEW.DOB));

- CREATE TABLE manager (
 Manager_ID INT AUTO_INCREMENT PRIMARY KEY,
 Department VARCHAR(50),                     
Name VARCHAR(50),                           
Mobile_Number VARCHAR(15),                  
DOJ DATE,                                                                          
 Email VARCHAR(100),                         
Country VARCHAR(50),                        
City VARCHAR(50),                           
Married_Status VARCHAR(10),                                  
DOB DATE,                                                                           
ID_Type VARCHAR(50),                        
ID_Proof VARCHAR(50),                       
Gender VARCHAR(10),                         
Salary DECIMAL(10, 2),                                                      
Password VARCHAR(50)                                                    
); 
CREATE TRIGGER set_password_before_insert
 BEFORE INSERT ON manager
 FOR EACH ROW
 SET NEW.Password = CONCAT(UPPER(SUBSTRING(NEW.Name, 1, 4)), YEAR(NEW.DOB));

- CREATE TABLE admin (
 First_Name VARCHAR(50),               
Last_Name VARCHAR(50),                
Contact_No VARCHAR(15),               
Email VARCHAR(100) PRIMARY KEY,       
ID_Type VARCHAR(50),                  
ID_Proof VARCHAR(50),                 
Password VARCHAR(255)              
);

- CREATE TABLE leave_applications (
 Application_ID INT AUTO_INCREMENT PRIMARY KEY,  
Emp_ID INT,                                    
LeaveType VARCHAR(50),                        
StartDate DATE,                                
EndDate DATE,                                  
Reason TEXT,                                    
Status VARCHAR(20)                       
);
# Getting Started
Open Employee Management folder in any source code editor.
# Update MySQL Connection Details:
con = mysql.connector.connect(host="localhost", user="root", password="your_root_password", database="employee_management_system") Replace "your_root_password" with your MySQL root password.
# Usage
To run the Employee Management System, execute the login.py file.



