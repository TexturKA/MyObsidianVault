### Что это?

SQL (structured query language) - известнейший декларативный язык программирования, используемый при создании, модификации и управлении данными в реляционных БД.

### Виды SQL-команд

Выделяют 3 вида SQL-команд:

1. **DDL (Data Definition Language)**. Команды для изменения структуры БД и связанных объектов: ALTER, CREATE, DROP.
2. **DML (Data Manipulation Language)**. Для управления данными (для вставки, просмотра и выборки, обновления, удаления и пр.): INSERT, SELECT, UPDATE, DELETE.
3. **DCL (Data Control Language)**. Для управления пользователями: GRANT, REVOKE.

### Оптимизация запросов

1. Конкретные имена столбцов после SELECT.
2. Минимум подзапросов
3. Обход низкопроизводительных операторов\
4. Соблюдение правильного порядка соединения таблиц
5. Использование в разделе WHERE как можно больше ограничивающих условий

### JOIN

##### INNER JOIN
```sql
FROM left_table JOIN right_table ON condition
```
Из строк `left_table` и `right_table` объединяются и возвращаются только те строки, по которым выполняются `condition`.
##### LEFT OUTER JOIN
```sql
FROM left_table LEFT JOIN right_table ON condition
```
Возвращаются все строки `left_table`. Данными `right_table` дополняются только те строки `left_table`, для которых выполняются condition. Для недостающих данных вместо строк `right_table` вставляются NULL-значения.
##### RIGHT OUTER JOIN
```sql
FROM left_table RIGHT JOIN right_table ON condition
```
Возвращаются все строки `right_table`. Данными `left_table` дополняются только те строки `right_table`, для которых выполняются `condition`. Для недостающих данных вместо строк `left_table` вставляются NULL-значения.
##### FULL OUTER JOIN
```sql
FROM left_table FULL JOIN right_table ON condition
```
Возвращаются все строки `left_table` и `right_table`. Если для строк `left_table` и `right_table` выполняются `condition`, то они объединяются в одну строку. Для строк, для которых не выполняются `condition`, NULL-значения вставляются на место `left_table`, либо на место `right_table`, в зависимости от того данных какой таблицы в строке не имеется.
##### CROSS JOIN
```sql
FROM left_table CROSS JOIN right_table
```
Объединение каждой строки `left_table` со всеми строками `right_table`. Этот вид соединения иногда называют декартовым произведением.

### В чём отличие HAVING и WHERE?

`HAVING` используется для фильтрации результатов вычисления агрегирующих функций

### Какой запрос найдёт количество дублирующихся фамилий (surname) у пользователей в таблице users и выведет поля surname и count?

```sql
SELECT surname, COUNT(surname) as count
FROM users
GROUP BY surname
HAVING COUNT(surname) > 1;
```

### Какие стили в SQL?

Руководство по стилю SQL: https://www.sqlstyle.guide/ru/