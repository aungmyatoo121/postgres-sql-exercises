Postgres SQL Exercises
This repository provides a collection of exercises to gain hands-on experience with PostgreSQL, covering topics from basic queries to advanced database management techniques. 
These exercises are inspired by and adapted from the GeeksforGeeks SQL Exercises.

Getting Started
Follow these steps to set up the environment, connect to the PostgreSQL database, and create the necessary tables.

Prerequisites
Install PostgreSQL: Ensure PostgreSQL is installed on your system. You can download it from the official PostgreSQL website.
Install Jupyter Notebook: If not already installed, you can install it with pip:

pip install notebook

Install ipython-sql extension:

pip install ipython-sql

Set Up the Database:
Create a PostgreSQL database named my_practise.
Create a user my_test with password mypractise and grant them access to the my_practise database.
Connecting to the Database
Open the Jupyter Notebook.

Use the following code snippet to connect to your database:

%reload_ext sql
%env DATABASE_URL=postgresql://my_test:mypractise@localhost:5433/my_practise
Replace localhost:5433 with the correct host and port of your PostgreSQL server, if different.

Creating Tables
Run the following SQL commands in a Jupyter Notebook cell with the %%sql magic:

1. Create the Products Table

CREATE TABLE Products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    unit_price DECIMAL(10, 2)
);

2. Create the Sales Table

CREATE TABLE Sales (
    sale_id INT PRIMARY KEY,
    product_id INT,
    quantity_sold INT,
    sale_date DATE,
    total_price DECIMAL(10, 2)
);
Sample Data
Optionally, add sample data to test the tables:

Insert Data into Products

%%sql
INSERT INTO Products (product_id, product_name, category, unit_price) 
values
(101, 'Laptop', 'Electronics', 500.00),
(102, 'Smartphone', 'Electronics', 300.00),
(103, 'Headphones', 'Electronics', 30.00),
(104, 'Keyboard', 'Electronics', 20.00),
(105, 'Mouse', 'Electronics', 15.00);

Insert Data into Sales

%%sql
INSERT INTO Sales (sale_id, product_id, quantity_sold, sale_date, total_price) VALUES
(1, 101, 5, '2024-01-01', 2500.00),
(2, 102, 3, '2024-01-02', 900.00),
(3, 103, 2, '2024-01-02', 60.00),
(4, 104, 4, '2024-01-03', 80.00),
(5, 105, 6, '2024-01-03', 90.00);


Verifying the Setup
Use the following query to ensure your tables were created successfully and data was inserted:

View Products
SELECT * FROM Products;

View Sales
SELECT * FROM Sales;
