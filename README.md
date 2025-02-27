1) Выберите из таблицы orders все заказы
![image](https://github.com/user-attachments/assets/74c7760e-9425-420f-9065-b092b605e79d)
SELECT * FROM orders
3) Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in
SELECT * FROM orders
WHERE STATUS IN("cancelled","in_progress", "delivery");
![image](https://github.com/user-attachments/assets/1fbb63a4-0957-450a-9f85-060f0c00739d)
5) Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"
SELECT * FROM orders
WHERE STATUS = "cancelled"
or STATUS = "new";
![image](https://github.com/user-attachments/assets/d1b1087d-6e6b-44c0-b120-164266337371)
7) Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).Вывести нужно только номер (id) и сумму (sum) заказа.
SELECT id, SUM  FROM orders
WHERE products_count >= 3;
![image](https://github.com/user-attachments/assets/ad884836-f05b-40ac-81c1-a91d8ae7156b)
