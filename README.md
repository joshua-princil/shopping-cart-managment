# shopping-cart-managment
A system using Python code and MySQL for adding, removing, and signing out items from the cart in shopping websites and it follows OOPs concepts and SOLID principles.
The python code stores the data inputted by the user into MySQL.

system prerequisites:
  -Python should be installed
  -MySQL server, workbench and shell must installed

things to do in order to run the code:
  -pip should be installed
  -Python should be connected to MySQL for database storage(windows command prompt code - pip install mysql-connector-python)
  -the below details should be adjusted according to the MySQL configuration of the user:
            host="localhost",
            user="yourusername",
            password="yourpassword",
            database="yourdatabasename"

  -the following commands must be implemented in MySQL before running the code:
  
CREATE TABLE IF NOT EXISTS Users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(50) NOT NULL
);
CREATE TABLE IF NOT EXISTS Products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    stock_quantity INT NOT NULL
);
CREATE TABLE IF NOT EXISTS Cart (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    product_id INT,
    quantity INT,
    total_price DECIMAL(10, 2),
    FOREIGN KEY (user_id) REFERENCES Users(id) ON DELETE CASCADE,
    FOREIGN KEY (product_id) REFERENCES Products(id)
);
INSERT INTO products (name, price, stock_quantity) VALUES
('Product 1', 10.99, 100),
('Product 2', 20.99, 150),
('Product 3', 15.49, 80),
('Product 4', 5.99, 200),
('Product 5', 25.99, 120),
('Product 6', 12.99, 90),
('Product 7', 18.99, 110),
('Product 8', 8.49, 160),
('Product 9', 22.99, 130),
('Product 10', 9.99, 180);


      
