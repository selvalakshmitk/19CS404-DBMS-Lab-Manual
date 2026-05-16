Experiment 2: DDL Commands
AIM
To study and implement DDL commands and different types of constraints.

THEORY
1. CREATE
Used to create a new relation (table).

Syntax:

CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
2. ALTER
Used to add, modify, drop, or rename fields in an existing relation. (a) ADD

ALTER TABLE std ADD (Address CHAR(10));
(b) MODIFY

ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
(c) DROP

ALTER TABLE relation_name DROP COLUMN field_name;
(d) RENAME

ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
3. DROP TABLE
Used to permanently delete the structure and data of a table.

DROP TABLE relation_name;
4. RENAME
Used to rename an existing database object.

RENAME TABLE old_relation_name TO new_relation_name;
CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).

1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
2. UNIQUE
Ensures that values in a column are unique. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
3. CHECK
Specifies a condition that each row must satisfy. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
4. PRIMARY KEY
Used to uniquely identify each record in a table. Properties: Must contain unique values. Cannot be null. Should contain minimal fields. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
5. FOREIGN KEY
Used to reference the primary key of another table. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:

CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
Question 1
image
CREATE TABLE Employees(
EmployeeID PRIMARY KEY,
FirstName NOT NULL,
LastName NOT NULL,
Email UNIQUE,
Salary DECIMAL CHECK(Salary > 0 ),
DepartmentID INTEGER,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
Output: image

Question 2
image
ALTER TABLE Student_details
ADD Date_of_birth Date;
Output: image

Question 3
image
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE);
Output: image

Question 4
image
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate > InvoiceDate),
Amount REAL CHECK(Amount > 0)
);
Output: image

Question 5
image
INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES (201, 'David Lee', 'M', 'Physics', 92)
Output: image

Question 6
image
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL CHECK(BonusAmount > 0),
BonusDate DATE,
Reason TEXT NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES  Employees(EmployeeID)
);
Output: image

Question 7
image
ALTER TABLE Student_details
ADD State TEXT;
Output: image

Question 8
image
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER,
FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
Output: image

Question 9
image
INSERT INTO student_details(RollNo,Name,Gender,Subject,MARKS)

SELECT RollNo,Name,Gender,Subject,MARKS FROM Archived_students;
Output: image

Question 10
image
alter table Student_details
add mobilenumber  number 
     
Output:

image
Grade
image
RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
