1) Выберите из таблицы orders все заказы
![image](https://github.com/user-attachments/assets/74c7760e-9425-420f-9065-b092b605e79d)
SELECT * FROM orders
2) Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in
SELECT * FROM orders
WHERE STATUS IN("cancelled","in_progress", "delivery");
![image](https://github.com/user-attachments/assets/1fbb63a4-0957-450a-9f85-060f0c00739d)
3) Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"
SELECT * FROM orders
WHERE STATUS = "cancelled"
or STATUS = "new";
![image](https://github.com/user-attachments/assets/d1b1087d-6e6b-44c0-b120-164266337371)
4) Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).Вывести нужно только номер (id) и сумму (sum) заказа.
SELECT id, SUM  FROM orders
WHERE products_count >= 3;
![image](https://github.com/user-attachments/assets/ad884836-f05b-40ac-81c1-a91d8ae7156b)
5) Выберите из таблицы orders 3 самых дешевых заказа за всё время. Данные нужно отсортировать в порядке убывания цены. Отмененные заказы не учитывайте.
SELECT * FROM orders
WHERE STATUS != "cancelled"
ORDER BY sum ASC limit 3
![image](https://github.com/user-attachments/assets/6fc58876-6591-4498-a24c-230a31f129bb)
6)Выберите из таблицы orders 2 самых дорогих заказов за всё время. Данные нужно отсортировать в порядке убывания цены. Отмененные заказы не учитывайте.
SELECT * FROM orders
WHERE STATUS != "cancelled"
ORDER BY sum DESC limit 2;
![image](https://github.com/user-attachments/assets/b706faa9-d7c4-4089-a3b2-192209b28697)
7)Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).
insert into orders (id, products, sum)
value (6, 4, 8000);
![image](https://github.com/user-attachments/assets/fc98c88c-b854-45d2-8b67-f77f9c525bb3)
8) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.
insert into products (id, name, count, price)
value (7, 'VR-очки', 2, 70000);
![image](https://github.com/user-attachments/assets/50fb9896-f070-4e47-a96c-cedfda7c7ccd)
9)В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.
update products set name='PS5' where id=7;
![image](https://github.com/user-attachments/assets/803bd8dc-4f5f-4d28-8052-94fffe4961cd)
8)Создайте таблицу users с полем id типа INT и двумя текстовыми полями, которые будут хранить имя (first_name) и фамилию (last_name). Длина имени и фамилии не превышает 50 символов.
Добавьте в таблицу трех пользователей: Дмитрия Иванова, Анатолия Белого и Дениса Давыдова.
create table users (
   id INT, 
	first_name VARCHAR(50), 
	last_name VARCHAR(50))vmusers;
INSERT INTO users (id, first_name, last_name)
VALUES
9)Создайте таблицу users для хранения информации о пользователях сайта.
В таблице должны быть следующие поля:

id – идентификатор, целое положительное;
email – адрес электронной почты, строка не более 100 символов;
date_joined – дата регистрации (достаточно хранить дату, без времени)
last_activity – дата и время последней активности (с точностью до секунд).
Create table calendar (
id int unsigned,
user_id int unsigned,
doctor_id int unsigned,
visit_date datetime);
Insert into calendar (id, user_id, doctor_id, visit_date)
Values 
(1, 1914 , 1, '2017-04-08 12:00:00'),
(2, 12, 1, '2017-04-08 12:30:00'),
(3, 4641, 2, '2017-04-09 09:00:00'),
(4, 784, 1,'2017-04-08 13:00:00'),
(5, 15, 2,'2017-04-09 10:00:00')
![image](https://github.com/user-attachments/assets/8416b71a-d28e-4595-996d-c6bd3c8a3bed)
10)Создайте таблицу calendar для хранения календаря посетителей.
В таблице должны быть следующие поля:

id – идентификатор записи в календаре, целое положительное;
user_id – идентификатор пользователя, целое положительное;
doctor_id – идентификатор доктора, целое положительное;
visit_date – дата и время визита (точность до секунд).
create table users (
id int(10) unsigned,
email varchar (100),
date_joined date,
last_activity datetime
);
insert into users (id, email, date_joined,last_activity)
values
(1,'user1@domain.com', '2014-12-12','2016-04-08 12:34:54'),
(2,'user2@domain.com', '2014-12-12','2017-02-13 11:46:53'),
(3,'user3@domain.com', '2014-12-13','2017-04-04 05:12:07');
![image](https://github.com/user-attachments/assets/56db7a5a-e70b-4f5a-a8ba-50a85635ecb7)
11)Создайте таблицу users , в которой будут следующие поля:

id — идентификатор, целые положительные числа.
first_name— имя, строки до 50 символов.
last_name — фамилия, строки до 60 символов.
bio — биография, текст до 65000 символов.
create table users (
id int (10) unsigned,
first_name varchar (50),
last_name varchar (60),
bio text
);
INSERT INTO users (id, first_name, last_name, bio)
VALUES
(1,'Антон','Кулик','С отличием окончил 39 лицей.'),
(2,'Сергей','Давыдов',''),
(3,'Дмитрий','Соколов','Профессиональный программист.');
![image](https://github.com/user-attachments/assets/681c1947-8d13-4428-bce6-b41368d6ff78)

1) Выберите из таблицы orders 4 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
SELECT * FROM orders 
WHERE STATUS != "cancelled" 
ORDER BY sum DESC LIMIT 4;
![image](https://github.com/user-attachments/assets/a4f9c000-084a-4ddf-9957-16a70242aae9)

2) Выберите из таблицы products название и цены четырех самых дешевых товаров, которые есть на складе.
SELECT NAME,price FROM products 
WHERE COUNT != 0 
ORDER BY price DESC LIMIT 4;
![image](https://github.com/user-attachments/assets/9847deb1-a587-42de-8d44-ba9056247615)

3) Выберите из таблицы orders три последних заказа (по дате date) стоимостью от 3200 рублей и выше.
Данные отсортируйте по дате в обратном порядке.
SELECT * FROM orders 
WHERE sum >= 3200 
ORDER BY date DESC LIMIT 3;
![image](https://github.com/user-attachments/assets/63b2dc84-d7d6-4ca1-9507-ba54981f2840)

4) Создайте данную таблицу:
DROP TABLE IF EXISTS products;
CREATE TABLE products(
	id INT UNSIGNED NOT NULL,
	name VARCHAR(255) NULL,
	count INTEGER NULL,
   price INTEGER NULL
	);
INSERT INTO products (id, name, count, price)
VALUES
	 (1, 'Стиральная машина', 5, 10000),
    (2, 'Холодильник', 0, 10000),
    (3, 'Микроволновка', 3, 4000),
    (4, 'Пылесос', 2, 4500),
    (5, 'Вентилятор', 0, 700),
    (6, 'Телевизор', 7, 31740),
    (7, 'Тостер', 2, 2500),
    (8, 'Принтер', 4, 3000),
    (9, 'Активные колонки', 1, 2900),
    (10, 'Ноутбук', 4, 36990),
    (11, 'Посудомоечная машина', 0, 17800),
    (12, 'Видеорегистратор', 23, 4000),
    (13, 'Смартфон', 8, 12300),
    (14, 'Флешка', 4, 1400),
    (15, 'Блендер', 0, 5500),
    (16, 'Газовая плита', 5, 11900),
    (17, 'Клавиатура', 3, 1800);
![image](https://github.com/user-attachments/assets/8d6750bf-1d77-47d5-8a53-2a69fc094902)
5) Из этой таблицы сделать выборку на основе задания: Сайт выводит товары по 5 штук. Выберите из таблицы products товары, которые пользователи увидят на 3 странице каталога при сортировке в порядке возрастания цены (price).
SELECT * FROM products
ORDER BY price DESC LIMIT 5
OFFSET 10;
![image](https://github.com/user-attachments/assets/5d0bb1c6-ff7f-469d-a313-9d65016b7ccc)

Задание 1.

Создайте таблицу orders для хранения списка заказов:

id — идентификатор, целое положительное.
user_id — идентификатор пользователя, который оформил заказ. Целое положительное, NULL запрещен.
amount — стоимость заказа. Целое положительное число не более 1 млн. NULL запрещен, по умолчанию 0.
created — дата и время создания заказа. NULL запрещен.
state — статус заказа. Выбор из new, cancelled, in_progress, delivered, completed. Можно выбрать только один вариант. NULL запрещен. По умолчанию должен стоять new.
Добавьте 3 записи
DROP TABLE IF EXISTS orders;
CREATE TABLE orders (
    id INT UNSIGNED NOT NULL PRIMARY KEY,
    user_id int UNSIGNED not NULL,
    amount int UNSIGNED not NULL DEFAULT 0 CHECK (amount <= 1000000),
    created DATETIME not NULL,
    status ENUM('new', 'cencelled', 'in_progress', 'delivered', 'completed') NOT NULL DEFAULT 'new'
);

 INSERT INTO orders (id, user_id, amount, created, status)
VALUES
    (1, 56, 5400, '2018-02-01 17:46:59', 'new'),
    (2, 90, 249, '2018-02-01 19:13:04', 'new'),
    (3, 78, 2200, '2018-02-01 22:43:09', 'new'); 
![image](https://github.com/user-attachments/assets/767991ee-cd34-4694-a3ba-45ff0f73582f)

Задание 2.

Создайте таблицу users для хранения списка пользователей сайта:

id — идентификатор, целое положительное.
first_name — имя, строка до 20 символов. NULL запрещен.
last_name — фамилия, строка до 20 символов. NULL запрещен.
patronymic — отчество, строка до 20 символов. NULL запрещен, по умолчанию пустая строка.
is_active — отметка об активности пользователя. Логическое поле, по умолчанию TRUE.
is_superuser — отметка администратора. Логическое поле, по умолчанию FALSE.
Добавьте 3 записи 
DROP TABLE IF EXISTS users;
CREATE TABLE users (
    id INT UNSIGNED NOT NULL PRIMARY KEY,
    first_name VARCHAR(20) NOT NULL,
    last_name VARCHAR(20) NOT NULL,
    patronymic VARCHAR(20) NOT NULL DEFAULT '',
     is_active TINYINT(1) NOT NULL DEFAULT TRUE,
     is_superuser TINYINT(1) NOT NULL DEFAULT FALSE 
    
);

INSERT INTO users (id, first_name, last_name, patronymic, is_active, is_superuser) VALUES
(1,'Дмитрий', 'Иванов', DEFAULT, TRUE, FALSE),
(2,'Анатолий', 'Белый', 'Сургеевич', TRUE, TRUE),
(3,'Андрей', 'Крючков', DEFAULT, FALSE, FALSE);
![image](https://github.com/user-attachments/assets/8ee231b5-92a7-41b8-a57e-126abaae59a8)

Создайте таблицу products для хранения товаров в интернет магазине:

id — идентификатор, целое положительное.
category_id — категория, целое положительное. Может принимать NULL. По умолчанию NULL.
name — название, строка до 100 символов. NULL запрещен.
count — количество, целое положительное до 255. NULL запрещен, по умолчанию 0.
price — цена типа DECIMAL с 10 знаками, 2 из которых выделены для копеек. NULL запрещен, по умолчанию 0.00.
Добавьте 3 записи так, чтобы получалась таблица ниже:
DROP TABLE IF EXISTS products;
CREATE TABLE products (
    id INT UNSIGNED NOT NULL PRIMARY KEY,
    category_id INT UNSIGNED NULL DEFAULT NULL,
    name VARCHAR(100) NOT NULL,
    count TINYINT UNSIGNED NOT NULL DEFAULT 0,
    price DECIMAL(10,2) NOT NULL DEFAULT 0.00
    
);

INSERT INTO products (id, category_id, name, count, price) VALUES
(1, 1, 'Кружка', 5, 45.90),
(2, 17, 'Фломастеры', 0, 78.00),
(3, NULL, 'Сникерс', 12, 50.80);
![image](https://github.com/user-attachments/assets/d9acc4d1-a943-48e9-abd5-a98432bbf64a)
