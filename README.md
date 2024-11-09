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
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/create%20database.png)

__
2-  Inserting into students:

      INSERT INTO students (roll_no, name, enrollment_no, address, dob, gender)
      VALUES
        (1, 'Alice Johnson', 'EN12345', '123 Main St', '2001-01-01', 'Female'),
        (2, 'Bob Smith', 'EN23456', '456 Elm St', '2002-02-02', 'Male'),
        (3, 'Charlie Brown', 'EN34567', '789 Oak St', '2003-03-03', 'Male'),
        (4, 'Daisy Miller', 'EN45678', '101 Pine St', '2004-04-04', 'Female');
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/create%20and%20insert.png)

3- Retrieve all students:

          SELECT * FROM students;
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/select%20all.png)

4- Sort students by name:

         SELECT * FROM students ORDER BY name ASC;

![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/order%20by.png)
         
5- Retrieve students with a specific gender:


            SELECT * FROM students WHERE gender = 'Female';
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/5ac8cb863ee6b493151025d4f850c41925849c4a/output/Screenshot%20(52).png)

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
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/0012c1621a9246acdf1b3df6b9a7196da2f92a5d/output/creat2.png)

  8- Inner Join :An inner join returns rows that have matching values in both tables

              SELECT s.name, c.course_name
              FROM students s
              INNER JOIN courses c ON s.roll_no = c.roll_no;
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/inner%20join.png)

  9- Left Join
    A left join returns all rows from the left table (first table), and the matched rows from the right table


         SELECT s.name, c.course_name
        FROM students s
        LEFT JOIN courses c ON s.roll_no = c.roll_no
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/left%20join.png)

10-  Right Join
    A right join returns all rows from the right table (second table), and the matched rows from the left table. 
    
         SELECT s.name, c.course_name
          FROM students s
          RIGHT JOIN courses c ON s.roll_no = c.roll_no;
![image alt](https://github.com/DivyarajSingh24/SQL-Assignment/blob/452426d2fdaff825dd12548be8dfa471a1978d2c/output/right%20join.png)
    
        
        
          
      
      

      



