Simple PHP CRUD Application with MySQL
This is a basic CRUD (Create, Read, Update, Delete) web application built using PHP and MySQL. It allows users to manage a list of products, each with a title, description, and price. Additionally, users can leave comments on individual product pages.

Features
List all products

View detailed information for each product

Add new products

Update existing products

Delete products

Add comments to products

Technologies Used
PHP
MySQL
HTML
CSS

Project Structure
project-root/
│
├── config/
│   └── connect.php         
│
├── vendor/
│   ├── create.php           
│   ├── update.php           
│   ├── delete.php           
│   └── create_comment.php  
│
├── index.php                
├── product.php              
├── update.php               
└── README.md               
⚙️ Setup Instructions
1. Clone the Repository
git clone https://github.com/yourusername/crud.git
cd crud
2. Create the Database
Open your MySQL client (e.g., phpMyAdmin, MySQL CLI) and run the following SQL to create the required tables:

CREATE DATABASE crud;

USE crud;

CREATE TABLE products (
  id INT NOT NULL AUTO_INCREMENT,
  title VARCHAR(255) NOT NULL,
  price DECIMAL(10,2) NOT NULL,
  description TEXT,
  PRIMARY KEY (id)
);

CREATE TABLE comments (
  id INT NOT NULL AUTO_INCREMENT,
  product_id INT NOT NULL,
  body TEXT,
  PRIMARY KEY (id),
  FOREIGN KEY (product_id) REFERENCES products(id) ON DELETE CASCADE
);
3. Configure Database Connection
Update the database credentials in config/connect.php:


<?php
$connect = mysqli_connect("localhost", "root", "root", "crud");

if (!$connect) {
    die("Connection failed: " . mysqli_connect_error());
}
?>

4. Run the Application
Place the project folder inside your local web server directory (e.g., htdocs/ for XAMPP or www/ for WAMP).

Start your web server and navigate to:
http://localhost/crud/index.php
