1. Напишіть SQL-запит, який для таблиці orders з атрибута date витягує рік, місяць і число. Виведіть на екран їх у три окремі атрибути поряд з атрибутом id та оригінальним атрибутом date (всього вийде 5 атрибутів).

**Рішення**

```sql
USE new_table;

SELECT
    id,
    date,
    YEAR(date) AS year,
    MONTH(date) AS month,
    DAY(date) AS day
FROM
    orders;
```

![Task 1](./images/Task-1.png)

2. Напишіть SQL-запит, який для таблиці orders до атрибута date додає один день. На екран виведіть атрибут id, оригінальний атрибут date та результат додавання.

**Рішення**

```sql
USE new_table;

SELECT
    id,
    date,
    DATE_ADD(date, INTERVAL 1 DAY) AS date_plus_one_day
FROM
    orders;
```

![Task 2](./images/Task-2.png)

3. Напишіть SQL-запит, який для таблиці orders для атрибута date відображає кількість секунд з початку відліку (показує його значення timestamp). Для цього потрібно знайти та застосувати необхідну функцію. На екран виведіть атрибут id, оригінальний атрибут date та результат роботи функції.

**Рішення**

```sql
USE new_table;

SELECT
    id,
    date,
    UNIX_TIMESTAMP(date) AS timestamp
FROM
    orders;
```

![Task 3](./images/Task-3.png)

4. Напишіть SQL-запит, який рахує, скільки таблиця orders містить рядків з атрибутом date у межах між 1996-07-10 00:00:00 та 1996-10-08 00:00:00.

**Рішення**

```sql
USE new_table;

SELECT
    COUNT(*) AS orders_count
FROM
    orders
WHERE
    date BETWEEN '1996-07-10 00:00:00' AND '1996-10-08 00:00:00';
```

![Task 4](./images/Task-4.png)

5. Напишіть SQL-запит, який для таблиці orders виводить на екран атрибут id, атрибут date та JSON-об’єкт {"id": <атрибут id рядка>, "date": <атрибут date рядка>}. Для створення JSON-об’єкта використайте функцію.

**Рішення**

```sql
USE new_table;

SELECT
    id,
    date,
    JSON_OBJECT('id', id, 'date', date) AS json_object
FROM
    orders;
```

![Task 5](./images/Task-5.png)
