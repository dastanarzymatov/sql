CREATE TABLE products (
                          id SERIAL PRIMARY KEY,
                          productName VARCHAR(30) NOT NULL,
                          company VARCHAR(20) NOT NULL,
                          productCount INT DEFAULT 0,
                          price NUMERIC NOT NULL,
                          isDiscounted BOOL
);

INSERT INTO products (productName, company, productCount, price, isDiscounted)
VALUES
    ('iPhone X', 'Apple', 3, 76000, false),
    ('iPhone 8', 'Apple', 2, 71000, true),
    ('iPhone 7', 'Apple', 5, 42000, true),
    ('Galaxy S9', 'Samsung', 2, 46000, false),
    ('Galaxy S8 Plus', 'Samsung', 1, 56000, true),
    ('Desire 12', 'HTC', 5, 28000, true),
    ('Nokia 9', 'HMD Global', 6, 38000, true);
--1--
SELECT * FROM products where company NOT LIKE 'HTC';
--2--
SELECT * FROM products  where company='Apple'   AND price < 75000;
--3--
SELECT * FROM products  where price >= 46000 ;
--4--
SELECT * FROM products order by price desc limit 2;
--5--
SELECT  productName FROM products order by price limit 1;
--6--
SELECT * FROM products where isDiscounted=true;
--7--
SELECT * FROM products where isDiscounted=false;
--8--
SELECT * FROM products order by price desc;
--9--
SELECT sum(price)as prise_sum FROM products;
--10--
SELECT company, COUNT(*) AS modelsCount
FROM products
GROUP BY company
HAVING COUNT(*) <= 2;



