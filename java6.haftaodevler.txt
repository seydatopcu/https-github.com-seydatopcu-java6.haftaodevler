CREATE TABLE authors (
    author_id SERIAL PRIMARY KEY,
    author_name VARCHAR(100) NOT NULL
);

CREATE TABLE publishers (
    publisher_id SERIAL PRIMARY KEY,
    publisher_name VARCHAR(100) NOT NULL
);

CREATE TABLE books (
    book_id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author_id INT NOT NULL,
    publisher_id INT NOT NULL,
    publication_year INT NOT NULL,
    isbn VARCHAR(13),
    FOREIGN KEY (author_id) REFERENCES authors(author_id),
    FOREIGN KEY (publisher_id) REFERENCES publishers(publisher_id)
);

CREATE TABLE customers (
    customer_id SERIAL PRIMARY KEY,
    customer_name VARCHAR(100) NOT NULL,
    email VARCHAR(255)
);

-- Yazar ekleme
INSERT INTO authors (author_name) VALUES ('Yaşar Kemal');

-- Yayınevi ekleme
INSERT INTO publishers (publisher_name) VALUES ('Yapı Kredi Yayınları');

-- Kitap ekleme
INSERT INTO books (title, author_id, publisher_id, publication_year, isbn) VALUES ('İnce Memed', 1, 1, 1955, '9789750804869');

-- Müşteri ekleme
INSERT INTO customers (customer_name, email) VALUES ('Ayşe Yılmaz', 'ayse.yilmaz@example.com');
