# Лабораторная работа №5

``` python
import pymysql

connect = pymysql.connect(host="127.0.0.1", port=3306, user="root", password="pass", db="my_db")
sql = """
SELECT first_name, last_name, date_of_birth 
FROM user 
WHERE YEAR(date_of_birth) = %s"""

year = int(input('Введите год: '))
cur = connect.cursor()
cur.execute(sql, year)
for rec in cur:
    print(rec[0], rec[1], rec[2])
```

## Вывод в консоли

```python
PS C:\Users\Саша\PycharmProjects\pythonProject> python .\main.py
Введите год: 1972
Carla Mariet 1972-12-30      
Tulip Jean-normand 1972-07-08
PS C:\Users\Саша\PycharmProjects\pythonProject> 

```
Вывод: человечки с именем Карла Мариет и у Тулип Джин-Норманд родились в один год! с: