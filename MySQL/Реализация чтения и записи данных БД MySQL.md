#mysql
Python по умолчанию включает в себя модуль sqlite3, который предоставляет встроенную поддержку для SQLite - легковесной реляционной СУБД. SQLite не требует установки сервера баз данных и может использоваться локально в приложениях Python для хранения и доступа к данным. Модуль sqlite3 обеспечивает интерфейс Python к SQLite и позволяет выполнять SQL-запросы, создавать и изменять таблицы, а также получать и изменять данные в базе данных SQLite.

Мы будем использовать MySQL, для этого необходимо установить драйвер для соответствующей СУБД и использовать модуль db-api для работы с ней.

Python DB-API - это спецификация API для доступа к базам данных из Python. Он определяет стандартный набор методов и атрибутов, которые должны быть реализованы в модулях Python для работы с различными СУБД.

Python DB-API поддерживает несколько классов, которые используются для выполнения операций с базой данных. Некоторые из этих классов включают:

-   Connection: используется для установления соединения с базой данных.
-   Cursor: используется для выполнения SQL-запросов и извлечения данных из базы данных.
-   Error: базовый класс для всех исключений, связанных с базами данных.
-   Warning: базовый класс для всех предупреждений, связанных с базами данных.

Для подключения к базе данных MySQL в Python с использованием DB-API вам нужно выполнить следующие шаги:

1.  Установите драйвер MySQL для Python, такой как mysql-connector-python или PyMySQL.
    
2.  Импортируйте модуль драйвера MySQL в ваше приложение Python.
    
3.  Используйте функцию connect() модуля драйвера MySQL для создания объекта Connection, который представляет соединение с базой данных.
    

Пример кода для подключения к базе данных MySQL с использованием модуля mysql-connector-python:

```sql
import mysql.connector

# Установить подключение к базе данных MySQL
conn = mysql.connector.connect(
    host="localhost",
    user="username",
    password="password",
    database="database_name"
)

# Выполнить запрос SQL
cursor = conn.cursor()
cursor.execute("SELECT * FROM mytable")

# Получить результаты запроса
results = cursor.fetchall()

# Закрыть соединение с базой данных
conn.close()
```

В этом примере мы используем функцию connect() модуля mysql.connector для установки соединения с базой данных MySQL. Мы передаем параметры хоста, имени пользователя, пароля и имени базы данных, чтобы установить соединение. Затем мы создаем объект Cursor и выполняем запрос SQL, после чего получаем результаты запроса и закрываем соединение с базой данных.


	DML (Data Manipulation Language) - это язык управления данными, который используется для добавления, изменения и удаления данных в базе данных. В контексте SQL, DML-запросы используются для выполнения следующих операций:
	1.  Вставка (INSERT) - добавление новых записей в таблицу
	2.  Обновление (UPDATE) - изменение существующих записей в таблице
	3.  Удаление (DELETE) - удаление записей из таблицы

