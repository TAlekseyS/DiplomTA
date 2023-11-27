## Описание приложения

### Бизнес часть

Приложение представляет из себя веб-сервис по покупку тура.

![](https://raw.githubusercontent.com/netology-code/qa-diploma/master/pic/service.png)

Приложение предлагает купить тур по определённой цене с помощью двух способов:

1. Обычная оплата по дебетовой карте
2. Уникальная технология: выдача кредита по данным банковской карты

Само приложение не обрабатывает данные по картам, а пересылает их банковским сервисам:

* сервису платежей (далее - Payment Gate)
* кредитному сервису (далее - Credit Gate)

---
## Необходимые процедуры для запуска автотестов:


1. Склонировать с помощью Git репозиторий на локальный компьютер командой:

   ```
   "git clone https://github.com/TAlekseyS/DiplomTA.git"
   ```
2. Запустить Docker Desktop.
3. Запустить IntelliJ IDEA и в нем открыть проект.
4. Установить NodeJS.  
5. В IntelliJ IDEA в терминале ввести команду:
```
docker-compose up -d
```
6. В новой вкладке терминала ввести команду в для запуска приложения:<br>

`java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar artifacts/aqa-shop.jar
`   - для MySQL

`java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar artifacts/aqa-shop.jar
`   - для PostgreSQL


7. В новой вкладке терминала ввести команду в зависимости от желаемой СУБД:<br>
`./gradlew clean test "-Ddb.url=jdbc:mysql://localhost:3306/app"
`   - для MySQL

`./gradlew clean test "-Ddb.url=jdbc:postgresql://localhost:5432/app"
`   - для PostgreSQL




## Формирование отчета AllureReport по результатам тестирования
В новой вкладке терминала или нажав двойной Ctrl ввести команду:
```
gradlew allureServe
```
Сгенерированный отчет откроется в браузере автоматически.
