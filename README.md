# SQL-Assignment

1-Creating the Student Database and Table

       CREATE DATABASE student_db;
       USE student_db;
    
       CREATE TABLE students (
        roll_no INT PRIMARY KEY,
        name VARCHAR(50),
        enrollment_no VARCHAR(20),
        address VARCHAR(100),
        dob DATE,
        gender VARCHAR(10)
    );
2-  Inserting into students:

      INSERT INTO students (roll_no, name, enrollment_no, address, dob, gender)
      VALUES
        (1, 'Alice Johnson', 'EN12345', '123 Main St', '2001-01-01', 'Female'),
        (2, 'Bob Smith', 'EN23456', '456 Elm St', '2002-02-02', 'Male'),
        (3, 'Charlie Brown', 'EN34567', '789 Oak St', '2003-03-03', 'Male'),
        (4, 'Daisy Miller', 'EN45678', '101 Pine St', '2004-04-04', 'Female');


3- Retrieve all students:

          SELECT * FROM students;

4- Sort students by name:

         SELECT * FROM students ORDER BY name ASC;

         
5- Retrieve students with a specific gender:

            SELECT * FROM students WHERE gender = 'Female';

6- Creating Additional Tables and Joining

     CREATE TABLE courses (
      course_id INT PRIMARY KEY,
      course_name VARCHAR(50),
      roll_no INT,
      FOREIGN KEY (roll_no) REFERENCES students(roll_no)
     );

  7- Insert some sample data into the courses table:

         INSERT INTO courses (course_id, course_name, roll_no)
          VALUES
            (1, 'Math', 1),
            (2, 'Science', 1),
            (3, 'History', 2),
            (4, 'English', 3);

  8- Inner Join :An inner join returns rows that have matching values in both tables

              SELECT s.name, c.course_name
              FROM students s
              INNER JOIN courses c ON s.roll_no = c.roll_no;

  9- Left Join
    A left join returns all rows from the left table (first table), and the matched rows from the right table


         SELECT s.name, c.course_name
        FROM students s
        LEFT JOIN courses c ON s.roll_no = c.roll_no;

10-  Right Join
    A right join returns all rows from the right table (second table), and the matched rows from the left table. 
    
         SELECT s.name, c.course_name
          FROM students s
          RIGHT JOIN courses c ON s.roll_no = c.roll_no;
    
        
        
          
      
      

      



