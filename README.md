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
   (1, 'Дмитрий', 'Иванов'),
   (2, 'Анатолий', 'Белов'),
   (1, 'Денис', 'Давыдов');
   ![image](https://github.com/user-attachments/assets/56db7a5a-e70b-4f5a-a8ba-50a85635ecb7)
