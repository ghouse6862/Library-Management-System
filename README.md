# Library-Management-System
This project was done as part of my CS6360 Database Design course

This is a database host application where users can Search, Issue, and Check-in books. The user can also add details of new borrowers.


DATABASE DETAILS:
The SQL database used here is MySQL.
The database consists of the following tables:
1.​Librarians: It consists of two columns “Empid” and “Password”, both the columns has a unique constraint on them.
Column “Empid” is of type integer, whereas “Password” is of type varchar.
2.​Authors: It consists of two columns “Author_id” and “Name” , here “Author_id” is the primary key.
Column “Author_id” is of type integer and “Name” is of type varchar.
3. ​Book:​ It consists of two columns “Isbn” and “Title”, here Isbn is the primary key. “Isbn” is of type bigint and “Title” is of type varchar.
4.​Book_Authors: It consists of two columns “Author_id” and “Isbn”, here both columns combined form a primary key.
“Author_id” is of type integer and “Isbn” is of type bigint
“Author_id” has a foreign key constraint and it refers to “Author_id” of Authors.
“Isbn” has a foreign key constraint and it refers to “Isbn” of Book table.
5.​Book_Loans: It consists of six columns, “Loan_id”, “Isbn”, “Card_id”, “Date_out”, “Due_date”, “Date_in”, here “Loan_id” column is the primary key.
“Isbn” and “Card_id” have foreign key constraints and they refer to “Isbn” of Book and “Card_id” of Borrower respectively.
6.​Borrower: It consists of six columns, “Card_id”, “Ssn”, “Bname”, “Address”, “Phone”, here “Card_id” column is the primary key and “Ssn” column has a unique constraint on it.
7.​Fines: It consists of 3 columns “Loan_id”, “Fine_amt”, “Paid”, here “Loan_id” is the primary key.
“Loan_id” also has a foreign key constraint and it refers to “Loan_id” of Book_Loans.


GUI DETAILS:
The GUI is implemented using Python programming language. Here, Tkinter which is the standard GUI library for Python is used and we query the database using pymysql.
       
At first, the user is prompted to either register or login. After this, the user can perform the following things:
1. The user can search for a book, after which he is given the option to issue the book to the borrower provided the borrower hasn’t already borrowed 3 books and the book is available.
2. The user can add details of new borrowers.
3. When the user clicks the refresh button, the fine amounts of all the checked out books is updated.
4. The user can check-in a book by searching for a book and then clicking the check-in button, before the book check-in the user will be asked to confirm whether the borrower has cleared the fine amount or not related to the book.


Dependencies:
1. You need to install Python 3 and MySQL.

2. The tkinter, pymysql, numpy and pandas libraries of python needs to be installed. This can be done by running following commands from command line:

pip install tkinter (or) pip3 install tkinter
pip install pymysql (or) pip3 install pymysql  
pip install numpy (or) pip3 install numpy
pip install pandas (or) pip3 install pandas

Set-up:
1. Then you should run pre_processing.py file to process the CSV files and make them suitable to be mapped to tables.
Make sure that before running this, you change the file paths at lines 11,31,37,42

2. Then run the Library-database-MySQL.sql file from mysql prompt using the “source” command:   source Library-database-MySQL.sql
Make sure before running this file that for last 4 queries you replace the given file path with your own correct file path.

3. After successfully completing the above steps, change the parameters “host”, “user” , “password” of the pymysql.connect() method to your values in each .py file except pre_processing.py file.
