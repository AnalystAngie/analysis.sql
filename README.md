# 4LIFECAFE_businessanalysis.sql

**customers**
CREATE TABLE customers ( 
  customer_id NUMBER PRIMARY KEY, 
  name VARCHAR2(50), 
  age NUMBER, 
  student_status VARCHAR2(20), 
  join_date DATE 
)
**products**
CREATE TABLE products ( 
  product_id NUMBER PRIMARY KEY, 
  product_name VARCHAR2(50), 
  category VARCHAR2(30), 
  price NUMBER(5,2) 
)
**orders**
CREATE TABLE orders ( 
  order_id NUMBER PRIMARY KEY, 
  customer_id NUMBER, 
  product_id NUMBER, 
  order_date DATE, 
  quantity NUMBER, 
  FOREIGN KEY (customer_id) REFERENCES customers(customer_id), 
  FOREIGN KEY (product_id) REFERENCES products(product_id) 
)
INSERT INTO customers (customer_id, name, age, student_status, join_date) VALUES  
(1, 'Sara Lopez', 22, 'Student', TO_DATE('2024-02-03', 'YYYY-MM-DD')),
(2, 'Jordan Kim', 25, 'Non-student', TO_DATE('2024-01-10', 'YYYY-MM-DD')), 
(3, 'Liam Nguyen', 19, 'Student', TO_DATE('2024-04-15', 'YYYY-MM-DD')), 
(4, 'Emily Davis', 21, 'Student', TO_DATE('2024-03-22', 'YYYY-MM-DD')), 
(5, 'Noah Patel', 28, 'Non-student', TO_DATE('2024-06-01', 'YYYY-MM-DD')), 
(6, 'Ava Johnson', 20, 'Student', TO_DATE('2024-05-12', 'YYYY-MM-DD')), 
(7, 'Mia Gonzalez', 23, 'Non-student', TO_DATE('2024-02-28', 'YYYY-MM-DD')), 
(8, 'Ethan Chen', 26, 'Non-student', TO_DATE('2024-03-19', 'YYYY-MM-DD')), 
(9, 'Olivia Smith', 18, 'Student', TO_DATE('2024-06-17', 'YYYY-MM-DD')), 
(10, 'Daniel Martinez', 24, 'Student', TO_DATE('2024-04-03', 'YYYY-MM-DD'));

SELECT * FROM Customers;
CUSTOMER_ID	NAME	AGE	STUDENT_STATUS	JOIN_DATE
1	Sara Lopez	22	Student	03-FEB-24
2	Jordan Kim	25	Non-student	10-JAN-24
3	Liam Nguyen	19	Student	15-APR-24
4	Emily Davis	21	Student	22-MAR-24
6	Ava Johnson	20	Student	12-MAY-24
7	Mia Gonzalez	23	Non-student	28-FEB-24
9	Olivia Smith	18	Student	17-JUN-24
10	Daniel Martinez	24	Student	03-APR-24
5	Noah Patel	28	Non-student	01-JUN-24
8	Ethan Chen	26	Non-student	19-MAR-24

10 rows selected.

INSERT INTO products (product_id, product_name, category, price) VALUES 
(1, 'Mocha Frappe', 'Frappe', 4.5), 
(2, 'Caramel Frappe', 'Frappe', 4.5), 
(3, 'Vanilla Frappe', 'Frappe', 4.5), 
(4, 'Hot Coffee', 'Coffee', 2.75), 
(5, 'Iced Coffee', 'Coffee', 3), 
(6, 'Brownie', 'Baked Good', 2.25), 
(7, 'Chocolate Chip Cookie', 'Baked Good', 2), 
(8, 'Cake Pop', 'Baked Good', 2.5)

SELECT * FROM products;
PRODUCT_ID	PRODUCT_NAME	CATEGORY	PRICE
1	Mocha Frappe	Frappe	4.5
2	Caramel Frappe	Frappe	4.5
3	Vanilla Frappe	Frappe	4.5
4	Hot Coffee	Coffee	2.75
5	Iced Coffee	Coffee	3
6	Brownie	Baked Good	2.25
7	Chocolate Chip Cookie	Baked Good	2
8	Cake Pop	Baked Good	2.5

INSERT INTO orders (order_id, customer_id, product_id, order_date, quantity) VALUES 
(1, 1, 4, TO_DATE('2025-06-24', 'YYYY-MM-DD'), 1),
(2, 5, 4, TO_DATE('2025-06-29', 'YYYY-MM-DD'), 1),
(3, 7, 8, TO_DATE('2025-06-23', 'YYYY-MM-DD'), 3), 
(4, 6, 8, TO_DATE('2025-07-14', 'YYYY-MM-DD'), 2), 
(5, 3, 1, TO_DATE('2025-07-11', 'YYYY-MM-DD'), 3), 
(6, 8, 8, TO_DATE('2025-06-25', 'YYYY-MM-DD'), 3), 
(7, 4, 3, TO_DATE('2025-06-27', 'YYYY-MM-DD'), 1), 
(8, 6, 1, TO_DATE('2025-06-30', 'YYYY-MM-DD'), 2), 
(9, 1, 5, TO_DATE('2025-07-05', 'YYYY-MM-DD'), 3), 
(10, 6, 6, TO_DATE('2025-07-10', 'YYYY-MM-DD'), 2), 
(11, 10, 5, TO_DATE('2025-07-15', 'YYYY-MM-DD'), 3), 
(12, 8, 1, TO_DATE('2025-06-22', 'YYYY-MM-DD'), 1), 
(13, 5, 6, TO_DATE('2025-06-20', 'YYYY-MM-DD'), 3), 
(14, 1, 5, TO_DATE('2025-07-10', 'YYYY-MM-DD'), 3), 
(15, 2, 6, TO_DATE('2025-06-20', 'YYYY-MM-DD'), 2), 
(16, 3, 7, TO_DATE('2025-07-05', 'YYYY-MM-DD'), 2), 
(17, 4, 2, TO_DATE('2025-06-20', 'YYYY-MM-DD'), 2), 
(18, 1, 1, TO_DATE('2025-07-14', 'YYYY-MM-DD'), 2), 
(19, 9, 2, TO_DATE('2025-06-26', 'YYYY-MM-DD'), 2), 
(20, 9, 8, TO_DATE('2025-07-09', 'YYYY-MM-DD'), 3), 
(21, 1, 7, TO_DATE('2025-07-09', 'YYYY-MM-DD'), 2), 
(22, 6, 3, TO_DATE('2025-07-07', 'YYYY-MM-DD'), 1), 
(23, 9, 6, TO_DATE('2025-07-02', 'YYYY-MM-DD'), 2), 
(24, 5, 2, TO_DATE('2025-06-20', 'YYYY-MM-DD'), 1), 
(25, 3, 3, TO_DATE('2025-07-04', 'YYYY-MM-DD'), 3), 
(26, 2, 7, TO_DATE('2025-06-27', 'YYYY-MM-DD'), 1), 
(27, 5, 8, TO_DATE('2025-07-01', 'YYYY-MM-DD'), 2), 
(28, 2, 3, TO_DATE('2025-06-18', 'YYYY-MM-DD'), 2), 
(29, 2, 4, TO_DATE('2025-06-21', 'YYYY-MM-DD'), 1), 
(30, 4, 1, TO_DATE('2025-06-15', 'YYYY-MM-DD'), 1), 
(31, 7, 8, TO_DATE('2025-06-28', 'YYYY-MM-DD'), 3), 
(32, 3, 4, TO_DATE('2025-07-07', 'YYYY-MM-DD'), 2), 
(33, 7, 1, TO_DATE('2025-06-15', 'YYYY-MM-DD'), 1), 
(34, 1, 7, TO_DATE('2025-06-23', 'YYYY-MM-DD'), 3), 
(35, 6, 1, TO_DATE('2025-07-15', 'YYYY-MM-DD'), 2), 
(36, 6, 3, TO_DATE('2025-07-04', 'YYYY-MM-DD'), 2), 
(37, 3, 3, TO_DATE('2025-06-27', 'YYYY-MM-DD'), 2), 
(38, 6, 2, TO_DATE('2025-07-12', 'YYYY-MM-DD'), 3), 
(39, 3, 5, TO_DATE('2025-06-20', 'YYYY-MM-DD'), 1), 
(40, 10, 5, TO_DATE('2025-07-03', 'YYYY-MM-DD'), 3), 
(41, 2, 2, TO_DATE('2025-06-16', 'YYYY-MM-DD'), 2), 
(42, 1, 8, TO_DATE('2025-07-09', 'YYYY-MM-DD'), 1), 
(43, 5, 3, TO_DATE('2025-06-17', 'YYYY-MM-DD'), 1), 
(44, 2, 8, TO_DATE('2025-07-05', 'YYYY-MM-DD'), 1), 
(45, 9, 3, TO_DATE('2025-07-10', 'YYYY-MM-DD'), 1), 
(46, 4, 7, TO_DATE('2025-07-13', 'YYYY-MM-DD'), 3), 
(47, 6, 6, TO_DATE('2025-06-27', 'YYYY-MM-DD'), 3), 
(48, 4, 1, TO_DATE('2025-06-23', 'YYYY-MM-DD'), 3), 
(49, 1, 4, TO_DATE('2025-06-23', 'YYYY-MM-DD'), 3), 
(50, 10, 7, TO_DATE('2025-07-11', 'YYYY-MM-DD'), 3)
