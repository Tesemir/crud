# Simple PHP CRUD Application with MySQL

This is a basic CRUD (Create, Read, Update, Delete) application built with **PHP** and **MySQL**. It manages a list of products, each with a title, description, and price. Users can also leave comments on each product.

---

## Technologies Used

- PHP
- MySQL
- HTML
- CSS

---

## Project Structure

project-root/
│
├── config/
│ └── connect.php # MySQL database connection
│
├── vendor/
│ ├── create.php # Handles creation of new products
│ ├── update.php # Handles product updates
│ ├── delete.php # Deletes a product
│ └── create_comment.php # Adds a comment to a product
│
├── index.php # Displays all products and add form
├── product.php # View product details and comments
├── update.php # Product update form
└── README.md # Project documentation

---

## Features

- List all products
- View individual product details
- Add new products
- Update existing products
- Delete products
- Add comments to products

---

## 🛠️ Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/php-crud-app.git
   cd php-crud-app
Create the Database

Create a MySQL database named crud and run the following SQL:

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
Configure Database Connection
Update config/connect.php with your database credentials:

$connect = mysqli_connect("localhost", "root", "root", "crud");
Run the Application
You can place the project in your local server directory (e.g., htdocs in XAMPP or www in WAMP), then access:
http://localhost/crud/index.php