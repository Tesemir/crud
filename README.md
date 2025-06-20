🚀 PHP CRUD Application with MySQL
A sleek and efficient product management system built with PHP and MySQL that lets you handle products and customer comments with ease.

🌟 Features
Full CRUD Functionality
Create, Read, Update, and Delete products effortlessly

Interactive Comments
Engage with customers through product comments

Clean Interface
Simple and intuitive user interface

Responsive Design
Works well on various devices

🛠 Tech Stack
https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white
https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white
https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white
https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white

📂 Project Structure
text
php-crud-app/
├── config/
│   └── connect.php        # Database connection
├── vendor/
│   ├── create.php         # Product creation handler
│   ├── update.php         # Product update handler
│   ├── delete.php         # Product deletion handler
│   └── create_comment.php # Comment creation handler
├── index.php              # Product listing and creation form
├── product.php            # Product details view
├── update.php             # Product edit form
└── README.md              # Project documentation
🚀 Quick Start
Prerequisites
PHP 7.0+

MySQL 5.7+

Web server (Apache/Nginx)

Installation
Clone the repository

bash
git clone https://github.com/yourusername/php-crud-app.git
cd php-crud-app
Set up the database

sql
CREATE DATABASE crud;
USE crud;

CREATE TABLE `products` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `title` VARCHAR(255) NOT NULL,
  `price` DECIMAL(10,2) NOT NULL,
  `description` TEXT,
  PRIMARY KEY (`id`)
);

CREATE TABLE `comments` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `product_id` INT NOT NULL,
  `body` TEXT,
  PRIMARY KEY (`id`),
  FOREIGN KEY (`product_id`) REFERENCES products(`id`) ON DELETE CASCADE
);
Configure database connection
Edit config/connect.php with your credentials:

php
$connect = mysqli_connect("localhost", "your_username", "your_password", "crud");
Launch the application

Place the project in your web server's root directory

Access via: http://localhost/php-crud-app/index.php

📝 Usage
View all products - Browse through your product catalog

Add new products - Expand your inventory with ease

Edit products - Keep your product information up-to-date

Delete products - Remove outdated items

Manage comments - Interact with your customers
