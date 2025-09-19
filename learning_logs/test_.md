1 - (4)
2 - (2)
3 - (4)
4 - (1)
5 - (2)
6 - (3)
7 - (2)
8 - (4)
9 - (2)
10 - (1)
11 - (3)
12 - (4)
13 - (2)
14 - (2)
15 - (2)
16 - (1)
17 - (2)
18 - (2)
19 - (3)
20 - (3)
21 - (3)
22 - (4)
23 - (2)
24 - (3)
25 - (3)
26 - (2)
27 - (4)
28 - (3)
29 - (3)
30 - (4)

# part 1
```sql
1. create database sql_finals;
2. use sql_finals;
3. CREATE TABLE users (
	id INT AUTO_INCREMENT PRIMARY KEY,
	created_at VARCHAR(100),
	username VARCHAR(100) NOT null,
  phone VARCHAR(100),
  country VARCHAR(50)
);
4. ALTER TABLE users ADD COLUMN is_marketing_agree INT;

5. ALTER TABLE users RENAME COLUMN Phone TO user_phone;

6. ALTER TABLE users DROP COLUMN created_at;

7.
 CREATE TABLE products (
	id INT AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(255) NOT null,
  price DECIMAL(10, 2) NOT NULL,
  discount_price DECIMAL(10, 2) NOT NULL
);

8.ALTER TABLE products CHANGE COLUMN name name VARCHAR(500) NOT NULL;

9.  CREATE TABLE staff (
	id INT AUTO_INCREMENT PRIMARY KEY,
	user_id INT NOT null,
	last_name VARCHAR(50) NOT null,
  first_name VARCHAR(50) NOT NULL,
  birth_date DATE
);

10. CREATE TABLE orders (
	id INT AUTO_INCREMENT PRIMARY KEY,
	user_id INT ,
	staff_id INT,
  order_date DATE,
  FOREIGN KEY (user_id) REFERENCES users(id),
  FOREIGN KEY (staff_id) REFERENCES staff(id)
);

11. CREATE TABLE orderdetails (
	id INT AUTO_INCREMENT PRIMARY KEY,
	order_id INT ,
	product_id INT,
  quantity INT NOT NULL,
  FOREIGN KEY (order_id) REFERENCES orders(id),
  FOREIGN KEY (product_id) REFERENCES products(id)
);

12. ALTER TABLE users DROP is_marketing_agree ;

13. ALTER TABLE orderdetails RENAME COLUMN quantity TO amount;

14. DROP TABLE orderdetails;

15. DROP database sql_finals;
```
# part 2
```sql
1. INSERT INTO users (username,user_phone,city,country)
VALUES ('joejoe@joecompany.com', '010-1234-5678', 'Seoul', 'Korea'),
('phk4938@never.com', '010-9876-5432', 'Buenos Aires', 'Argentina');

2. INSERT INTO users (username,user_phone,city,country)
VALUES ('inr01@never.com', '010-1111-2222', 'New York', 'USA'),
('fuxp76@never.com', '010-3333-4444', 'Seoul', 'Korea');

3. INSERT INTO products (name,price,discount_price)
VALUES ('Terrarossa Coffee Back', 18.00, 15.00);

4. INSERT INTO products (name,price,discount_price)
VALUES ('Mini Cheese Ball', 19.00, 19.00),
('Stabucks Drip Coffee', 22.00, 22.00);

5. INSERT INTO staff (user_id,last_name,first_name,birth_date)
VALUES (2, 'Carter', 'Joe','1990-10-20'),
(10, 'Jang', 'Ken','1991-02-19');

6. INSERT INTO orders (user_id,staff_id,order_date)
VALUES (2, 1,'2025-09-18');

7. INSERT INTO orderdetails (order_id,product_id,quantity)
VALUES (1,1,2),(1,2,3);

8. UPDATE users
SET phone = '010-5555-6666'
WHERE username = 'inr01@never.com';

9. UPDATE products
SET price = 20.00
WHERE name = 'Mini Cheese Ball';

10. UPDATE staff
SET first_name = 'Minjun'
WHERE user_id = 10;

11. DELETE FROM users WHERE username = 'phk4938@never.com';

12. DELETE FROM products WHERE id = 3;

13. DELETE FROM orderdetails WHERE order_id = 1;

14. TRUNCATE TABLE users;

15. DELETE FROM orders WHERE order_date = '2025-09-18';
```
# part3
```sql

1. 
SELECT id, username, phone
FROM users;

2.
SELECT order_date, count(id) as ordersCnt
FROM orders
WHERE order_date BETWEEN '2015-01-01' AND '2015-12-31'

3.
SELECT name FROM products WHERE price = (SELECT MAX(price) FROM products);

4.
SELECT country, id , username
FROM users
where country = 'Korea';

5.
SELECT birth_date,last_name,first_name
FROM staff
where birth_date <='1960-01-01';

6.
SELECT user_id , id ,order_date
FROM orders
WHERE user_id = 20;

7.
SELECT product_id , sum(quantity) as qsum
FROM orderdetails
WHERE product_id = 17;

8.
SELECT round(avg(price),2) as pAvg
FROM products;

9.
SELECT country , count(id)
FROM users
GROUP BY country
HAVING count(id) > 4;
10.
SELECT staff_id , count(id) as idCnt
FROM orders
GROUP BY staff_id
ORDER BY idCnt DESC;

11.
SELECT u.id , username, count(DISTINCT o.id) as orderCnt
FROM users u INNER JOIN orders o ON u.id = o.user_id
GROUP BY u.id
HAVING orderCnt > 1;

12.
SELECT u.id,u.username,s.last_name,s.first_name
FROM users u INNER JOIN staff s ON u.id = s.user_id;

13.
SELECT o.id , sum(quantity)as qSum
FROM orders o INNER JOIN orderdetails od ON o.id = od.order_id
GROUP BY o.id
HAVING qSum > 100;

14.
SELECT country,count(o.id)
FROM orders o INNER JOIN  users u ON o.user_id = u.id
WHERE country = 'USA'

15.
SELECT order_date,staff_id,count(id)
FROM (SELECT * FROM orders
    where order_date >= '2015-12-01' AND order_date < '2015-12-31'
  ) temp
WHERE staff_id = 3;

16.
SELECT name , price
FROM products
WHERE (SELECT avg(price) as priceAvg FROM products) > price;

17.
SELECT city,(SELECT count(id)as idCnt FROM users)
FROM users
WHERE city = 'Seoul'
GROUP BY city;

18.
SELECT o.id , (SELECT SUM(price*quantity))as pqSum
FROM orders o INNER JOIN orderdetails od ON o.id = od.order_id
INNER JOIN products p ON od.product_id = p.id
GROUP BY o.id
HAVING pqSum >= 2000;

19.
SELECT name,price
FROM products
WHERE NAME IN (SELECT name FROM products WHERE name like '%Coffee%');
20. 
(SELECT last_name FROM staff WHERE birth_date <= '1960-01-01')
UNION
(SELECT first_name FROM staff WHERE birth_date >= '1990-01-01')