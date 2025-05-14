This is a Demo SQL database for Cognizant Digital Nurture 4.0 registration.
Code:
create database School;
use School;
CREATE TABLE IF NOT EXISTS Teachers (
    TeacherID INT AUTO_INCREMENT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Subject VARCHAR(100),
    Email VARCHAR(100) UNIQUE
);
CREATE TABLE IF NOT EXISTS Students (
    StudentID INT AUTO_INCREMENT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Age INT,
    Class VARCHAR(20),
    Email VARCHAR(100) UNIQUE,
    TeacherID INT,
    FOREIGN KEY (TeacherID) REFERENCES Teachers(TeacherID)
        ON DELETE SET NULL
        ON UPDATE CASCADE
);
INSERT INTO Teachers (FirstName, LastName, Subject, Email) VALUES
('Anita', 'Sharma', 'Physics', 'anita.sharma@school.edu'),
('Rahul', 'Verma', 'Chemistry', 'rahul.verma@school.edu'),
('Sonia', 'Das', 'Mathematics', 'sonia.das@school.edu');

INSERT INTO Students (FirstName, LastName, Age, Class, Email, TeacherID) VALUES
('Rohit', 'Sen', 16, '10-B', 'rohit.sen@student.edu', 1),
('Meena', 'Patel', 15, '9-A', 'meena.patel@student.edu', 2),
('Aarav', 'Kumar', 14, '8-C', 'aarav.kumar@student.edu', 3),
('Sneha', 'Roy', 16, '10-A', 'sneha.roy@student.edu', 1),
('Vikram', 'Singh', 15, '9-B', 'vikram.singh@student.edu', 2);

Teacher table:
+-----------+-----------+----------+-------------+-------------------------+
| TeacherID | FirstName | LastName | Subject     | Email                   |
+-----------+-----------+----------+-------------+-------------------------+
|         1 | Anita     | Sharma   | Physics     | anita.sharma@school.edu |
|         2 | Rahul     | Verma    | Chemistry   | rahul.verma@school.edu  |
|         3 | Sonia     | Das      | Mathematics | sonia.das@school.edu    |
+-----------+-----------+----------+-------------+-------------------------+

Student table:
+-----------+-----------+----------+------+-------+--------------------------+-----------+
| StudentID | FirstName | LastName | Age  | Class | Email                    | TeacherID |
+-----------+-----------+----------+------+-------+--------------------------+-----------+
|         1 | Rohit     | Sen      |   16 | 10-B  | rohit.sen@student.edu    |         1 |
|         2 | Meena     | Patel    |   15 | 9-A   | meena.patel@student.edu  |         2 |
|         3 | Aarav     | Kumar    |   14 | 8-C   | aarav.kumar@student.edu  |         3 |
|         4 | Sneha     | Roy      |   16 | 10-A  | sneha.roy@student.edu    |         1 |
|         5 | Vikram    | Singh    |   15 | 9-B   | vikram.singh@student.edu |         2 |
+-----------+-----------+----------+------+-------+--------------------------+-----------+
