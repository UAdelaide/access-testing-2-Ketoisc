Put your files for part1 here

CREATE TABLE users (
    user_id INT AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(50) NOT NULL,
    location VARCHAR(50) NOT NULL,
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
    price INT,
    seller_location VARCHAR(50) NOT NULL,
    PRIMARY KEY (listing_id),
    FOREIGN KEY (seller_id) REFERENCES users(user_id),
    FOREIGN KEY (book_id) REFERENCES books(book_id)
);

CREATE TABLE history (
    transaction_id INT AUTO_INCREMENT,
    buyer_id INT,
    seller_id INT,
    book_id INT,
    price INT,
    timestamp TIMESTAMP,
    PRIMARY KEY (transaction_id),
    FOREIGN KEY (seller_id) REFERENCES users(user_id),
    FOREIGN KEY (book_id) REFERENCES books(book_id),
    FOREIGN KEY (buyer_id) REFERENCES users(user_id)
);

INSERT INTO users (username, password, location) VALUES ("user1", "14dsfkjhw4", "Adelaide");

INSERT INTO users (username, password, location) VALUES ("user2", "sdkjsdfk", "Melbourne");

INSERT INTO users (username, password, location) VALUES ("user2", "sdkjsdfk", "Melbourne");