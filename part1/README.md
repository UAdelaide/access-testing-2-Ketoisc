Put your files for part1 here

CREATE TABLE users (
    user_id INT AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(50) NOT NULL,
    PRIMARY KEY (user_id)
);

CREATE TABLE books (
    book_id INT AUTO_INCREMENT,
    title VARCHAR(50) NOT NULL,
    author VARCHAR(50) NOT NULL,
    isbn INT,
    PRIMARY KEY (book_id)
);

CREATE TABLE marketplace (
    listing_id INT AUTO_INCREMENT,
    seller_id INT,
    book_id INT,
    isbn INT,
    PRIMARY KEY (book_id)
);