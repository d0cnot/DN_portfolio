# Портфолио: инженер по тестированию

<div id="header" align="center">
  <img src="https://media0.giphy.com/media/UPqYp2tj61XlBhlPbH/200w.webp?cid=ecf05e47v2ozmryrqr4hkhp131ckshkx0kni5ft0g5keaa6g&ep=v1_gifs_search&rid=200w.webp&ct=g" width="300"/>
</div>

<div id="badges" align="center">
  <a href="https://vk.com/docnot">
    <img src="https://img.shields.io/badge/vk-blue?style=for-the-badge&logo=vk&logoColor=white" alt="vk Badge"/>
    <a href="https://t.me/d0cnot">
    <img src="https://img.shields.io/badge/telegram-blue?style=for-the-badge&logo=telegram&logoColor=white" alt="telegram Badge"/>
  </a>
</div>
    <img src="https://komarev.com/ghpvc/?username=your-github-username&style=flat-square&color=blue" alt=""/>
# Обо мне

Всем привет! Меня зовут Дмитрий, я начинающий тестировщик. Имею 12 летний опыт сисадмина в бюджетной организации, с ПО и сайтами знаком не по наслышке.
В этом репозитории вы можете найти некоторые из моих проектов, выполненных во время обучения и практики.

# Навыки и технологии
<img src="https://img.shields.io/badge/vk-blue?style=for-the-badge&logo=vk&logoColor=white" alt="vk Badge"/>
Jira,qase.io,SQL, Postman,Fiddler, Swagger, Trello,
SoapUI, Android Studio, xCode, Charles, Git, Chrome DevTools.

_[План автоматизации](/documents/Plan.md)_

_[Отчёт о проведённом тестировании](/documents/Report.md)_

_[Отчёт о проведённой автоматизации](/documents/Summary.md)_

_[баги](https://github.com/shpilkaQA/diplom-portfolio/issues)_

## Инструкция по запуску:

### ***для Windows***
**(*для остальных ОС использовать localhost вместо ip*)**

1. Клонировать текущий репозиторий
1. Перейти в директорию с клонированным репозиторием
1. Из папки с репозиторием запустить контейнеры
    ```
    docker-compose up -d
    ```
3. Запустить SUT
    * ***Для работы с MySQL***
   
    ```
    java -Dspring.datasource.url=jdbc:mysql://192.168.99.100:3306/app -jar artifacts/aqa-shop.jar
    ```
    
    * ***Для работы с Postgres***
   
    ```
    java -Dspring.datasource.url=jdbc:postgresql://192.168.99.100:5432/app -jar artifacts/aqa-shop.jar
   ```  
    дополнительно можно передать логин и пароль, установленные по умолчанию, добавив
    ```
    -Duser=app –Dpassword=pass
    ```

1. Запустить тесты
    * ***Для работы с MySQL***
       
    ```
    gradlew test
    ```
    Запуск в mysql установлен по умолчанию

    параметры:
    ```
    db.url=jdbc:mysql://192.168.99.100:3306/app
    user=app
    password=pass
    ```
        
    * ***Для работы с Postgres***
    
    ```
    gradlew test -Ddb.url=jdbc:postgresql://192.168.99.100:5432/app
    ```
    
1. Для формирования отчета Allure и его открытия в браузере выполнить команды
    ```
    gradlew allureReport
    gradlew allureServe
    ```

1. Остановить и удалить контейнеры    
    ```
    docker-compose down
    ```
