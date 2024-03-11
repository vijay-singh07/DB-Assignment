Below are the answers to the questions from the git repository - https://github.com/iAmritMalviya/DB-Assignment/tree/main?tab=readme-ov-file

Answer-1) "Product" and "Product_Category" entities from the class diagram typically represents a many-to-one relationship. This means that many instances of the "Product" class can be associated with one instance of the "Product_Category" class. Each product belongs to one category, but also multiple products can belong to the same category.

In the context of the "Product" and "Product_Category" entities, a one-to-one relationship would imply that each product is associated with one specific category, and each category is associated with one specific product.


Answer-2) To ensure that each product in the "Product" table has a valid category assigned to it, I can use a foreign key constraint.

-- Create a Category table(not exactly how class diagram has stated but a dummy one)
CREATE TABLE IF NOT EXISTS Category (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL
);

-- Create a Product table with a foreign key constraint(not exactly how class diagram has stated but a dummy one)
CREATE TABLE IF NOT EXISTS Product (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    category_id INT NOT NULL,
    FOREIGN KEY (category_id) REFERENCES Category(id)
);

In this example, the "Product" table includes a column category_id that references the id column in the "Category" table. The FOREIGN KEY (category_id) REFERENCES Category(id) statement ensures that every category_id in the "Product" table must exist in the "Category" table's id column, thus ensuring that each product has a valid category assigned to it.