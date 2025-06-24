# Task1-Database Setup and Schema Design.
• Objective: Learn to create databases, tables, and define relationships.
• Tools:MySQL Workbench / pgAdmin / SQLiteStudio.
• Deliverables: SQL script to create schema and ER diagram.

• Outcome: A well-structured schema.

CODE -

-- Create Author table
CREATE TABLE Author (
    author_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    country VARCHAR(100)
);

-- Create Book table
CREATE TABLE Book (
    book_id INT PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    author_id INT,
    genre VARCHAR(50),
    publisher VARCHAR(100),
    year_published YEAR,
    FOREIGN KEY (author_id) REFERENCES Author(author_id)
);

-- Create Member table
CREATE TABLE Member (
    member_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(15)
);

-- Create Loan table (junction table for Book and Member)
CREATE TABLE Loan (
    loan_id INT PRIMARY KEY,
    book_id INT,
    member_id INT,
    loan_date DATE NOT NULL,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES Book(book_id),
    FOREIGN KEY (member_id) REFERENCES Member(member_id)
);

Insert into Author (author_id,name,country) values('1','Uday','India');
Insert into Author (author_id,name,country) values('2','Sahu','India');

Insert into Book (book_id,title,author_id,genre,publisher,year_published) values('1','Developer','1','Tech','Samsung','2010'); 
Insert into Book (book_id,title,author_id,genre,publisher,year_published) values('2','Programmer','2','Tech','Apple','2011'); 


Insert into Member (member_id,name,email,phone) values('1','Uday','uday11@gmail.com','9856421478'); 
Insert into Member (member_id,name,email,phone) values('2','Sahu','sahu12@gmail.com','9745621478'); 


Insert into Loan (loan_id,book_id,member_id,loan_date,return_date) values('11','1','1','2010-01-12','2011-01-12'); author
Insert into Loan (loan_id,book_id,member_id,loan_date,return_date) values('12','2','2','2010-01-13','2011-01-13'); 


DataSets-  • Author.
           • Book.
           • Member.
           • Loan.























