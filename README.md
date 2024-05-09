# «Проведение нагрузочного тестирования DB»

## Решения
#### Задание 1
* <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Jmeter/WordPressDbNephedov.jmx">WordPressDbNephedov.jmx</a> - профиль нагрузки БД.
* <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Screenshots/ScreenshotJMeterMariaDbWordPress.jpg">Скриншот</a> - с временами откликов выполнения процедур БД.
* Вывод по результатам сравнения времени отклика процедур - <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/README.md">README.md</a>.
  
#### Задание 2
* <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Additional%20task/JMeter/Test%20Plan.jmx">Test Plan.jmx</a> профиль нагрузки с Web, DB сценариями.
* <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Additional%20task/Screenshots/ScreenshotWebDB.jpg">Скриншот</a> - с временами откликов выполнения сценариев.
* Вывод по результатам определения верхней границы отказа GET http запроса - <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Additional%20task/README.md">README.md</a>.


## Что было сделано
#### Задание 1
* Установлена библиотека MariaDB - <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Jmeter/mariadb-java-client-3.1.4.jar">mariadb-java-client-3.1.4.jar</a>.
* Подключен org.mariadb.jdbc.Driver к сконфигурированному профилю нагрузки - <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Jmeter/WordPressDbNephedov.jmx">WordPressDbNephedov.jmx</a>
  базы данных в JMeter.
* Зафиксировано время откликов процедур (<a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/MariaDb/Procedure.sql">Procedure.sql</a>) -
  <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Screenshots/ScreenshotJMeterMariaDbWordPress.jpg">Скриншот результата</a>.
  
#### Задание 2
* Сконфигурирован профиль нагрузки (<a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Additional%20task/JMeter/Test%20Plan.jmx">Test Plan.jmx</a>) c группой сценариев:
  * 1 WEB сценарий - пользователь читает комментарии к [посту](https://qamidhl.herokuapp.com/?p=1), обновляя страницу.
  * 1 DB сценарий
    - через БД заполнять комментариями WP 100 комментариев в 1 секунд;
    - опеределить точку отказа, при каком количестве комметариев к посту у пользователя страница начинает загружаться больше 20 секунд.
* Установлена библиотека MariaDB - <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Additional%20task/JMeter/mariadb-java-client-3.1.4.jar">mariadb-java-client-3.1.4.jar</a>.
* Зафиксировано время откликов выполнения обоих сценариев - <a href="https://github.com/Nephedov/Performance-test-Load_DB/blob/main/Additional%20task/Screenshots/ScreenshotWebDB.jpg">Скриншот результатов</a>.



## Описание Задания 1

Провести тестирование процедур dorepeat_v1 и dorepeat_v2, прислать скриншоты графиков.

Нужно провести тестирование хранимой процедуры:
1. Измерить время отклика вызова процедуры dbrepeat_v1.
2. Измерить время отклика вызова процедуры dbrepeat_v2. Для процедуры нужно дополнительно передать текст комментария p2.

## Описание Задания 2 (необязательное)

Провести тестирование Web + DB. В одном тест-плане добавить 2 потока, со своим сценарием для каждого. 

### Что нужно сделать

Проверсти веб-тестирование одного поста с одним комментарием и с одним миллионом комментариев, прислать скриншоты графиков. 
  Группа сценариев.
   
Сценарий 1:
- пользователь читает комментарии к [посту](https://qamidhl.herokuapp.com/?p=1), обновляя страницу.

Сценарий 2:  
- через БД заполнять комментариями WP 100 комментариев в 1 секунд;
- опеределить точку отказа, при каком количестве комметариев к посту у пользователя страница начинает загружаться больше 20 секунд.
