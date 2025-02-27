1) Выберите из таблицы orders все заказы
![1000006962](https://github.com/user-attachments/assets/ee97ffa4-752d-4276-90d1-187d819d9566)

SELECT * FROM orders
3) Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in
SELECT * FROM orders
WHERE STATUS IN("cancelled","in_progress", "delivery");
![image](https://github.com/user-attachments/assets/5a8a3566-1363-4df7-8182-c491309c0916)
5) Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"
SELECT * FROM orders
WHERE STATUS = "cancelled"
or STATUS = "new";
![image](https://github.com/user-attachments/assets/63283e37-ab3c-476e-ba82-7fb02200313e)
7) Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).Вывести нужно только номер (id) и сумму (sum) заказа.
SELECT id, SUM  FROM orders
WHERE products_count >= 3
![image](https://github.com/user-attachments/assets/2cb558e1-c437-48b9-8610-a77304edd3e7)
