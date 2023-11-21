SQL Cheatsheet

SELECT ('столбцы (* - для выбора всех столбцов); обязательно')
(могут применяться агрегатные функции COUNT, MIN, MAX, AVG и SUM; необязательно)
(и ключевое слово DISTINCT; необязательно)
FROM ('таблица; обязательно')
WHERE ('условие/фильтрация; необязательно')
GROUP BY ('столбец, по которому нужно сгруппировать данные; необязательно')
HAVING ('условие/фильтрация на уровне сгруппированных данных; необязательно')
ORDER BY ('столбец, по которому нужно ранжировать вывод; необязательно')
LIMIT ('сколько записей показывать; необязательно')
OFFSET ('начиная с какой записи показывать; необязательно')

Генерация даты:

(DATE_ADD('2020-01-01', INTERVAL FLOOR(RAND() * 365) DAY)) as Дата

SELECT buy_id, title, price, buy_book.amount
FROM buy
    JOIN buy_book ON buy.buy_id = buy_book.buy_id
    JOIN book ON buy_book.book_id = book.book_id
    JOIN client ON buy.client_id = client.client_id
WHERE name_client = "Баранов Павел" 
ORDER BY buy_id, buy_book.amount;

SELECT DISTINCT(name_genre), 
    (SELECT MAX(Total_Summ) FROM
        (SELECT SUM(buy_book.amount) AS Total_Summ
         FROM genre
            JOIN book USING(genre_id)
            JOIN buy_book USING(book_id)
            GROUP BY genre_id) AS Max_amount) AS Количество
FROM genre
    JOIN book USING(genre_id)
    JOIN buy_book USING(book_id);

SELECT ice_cream.name
    wrappers.name
FROM ice_cream
JOIN wrappers ON ice_cream.wrapper_id = wrappers.id
WHERE wrappers.name LIKE '_раздн%';

cur.executescript('''
CREATE TABLE IF NOT EXISTS categories(
    id INTEGER PRIMARY KEY,
    slug TEXT NOT NULL
);

CREATE TABLE IF NOT EXISTS ice_cream(
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    description TEXT,
    price REAL NOT NULL,
    category_id INTEGER NOT NULL,
    FOREIGN KEY(category_id) REFERENCES categories(id)

);
''')

cur.execute('''
SELECT ice_cream.name,
       categories.slug,
       MAX(ice_cream.price)
FROM ice_cream,
     categories
WHERE ice_cream.category_id = categories.id
GROUP BY categories.slug
ORDER BY ice_cream.price DESC;
''')