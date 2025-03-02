# Домашнее задание к занятию «Работа с данными (DDL/DML)» - Варфоломеева Марьяна


### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

```
docker run --name mysql-docker -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -d mysql:8.0
mysql -h 127.0.0.1 -P 3306  -u root -p
```
1.2. Создайте учётную запись sys_temp. 

```sql
CREATE USER 'sys_temp'@'%' IDENTIFIED BY 'root';
```

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

![](./img/1.png)

1.4. Дайте все права для пользователя sys_temp. 

```sql
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)
![](./img/2_.png)

1.6. Переподключитесь к базе данных от имени sys_temp.

![](./img/3.png)

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)
![](./img/4.png)


### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц.
```
+---------------+--------------+
| TABLE_NAME    | COLUMN_NAME  |
+---------------+--------------+
| actor         | actor_id     |
| address       | address_id   |
| category      | category_id  |
| city          | city_id      |
| country       | country_id   |
| customer      | customer_id  |
| film          | film_id      |
| film_actor    | actor_id     |
| film_actor    | film_id      |
| film_category | film_id      |
| film_category | category_id  |
| film_text     | film_id      |
| inventory     | inventory_id |
| language      | language_id  |
| payment       | payment_id   |
| rental        | rental_id    |
| staff         | staff_id     |
| store         | store_id     |
+---------------+--------------+

```