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
