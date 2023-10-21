# Портфолио: инженер по тестированию

<div id="header" align="center">
  <img src="https://media0.giphy.com/media/UPqYp2tj61XlBhlPbH/200w.webp?cid=ecf05e47v2ozmryrqr4hkhp131ckshkx0kni5ft0g5keaa6g&ep=v1_gifs_search&rid=200w.webp&ct=g" width="300"/>
</div>

<div id="badges" align="center">
  <img src="https://img.shields.io/badge/vk-blue?style=for-the-badge&logo=vk&logoColor=white" alt="vk Badge"/>
  <img src="https://img.shields.io/badge/YouTube-red?style=for-the-badge&logo=youtube&logoColor=white" alt="Youtube Badge"/>
  <img src="https://img.shields.io/badge/telegram-blue?style=for-the-badge&logo=telegram&logoColor=white" alt="telegram Badge"/>
</div>

# Обо мне

Всем привет! Меня зовут Дмитрий, я начинающий тестировщик. Имею 12 летний опыт сисадмина в бюджетной организации, с ПО и сайтами знаком не по наслышке.
В этом репозитории вы можете найти некоторые из моих проектов, выполненных во время обучения и практики.

# Навыки и технологии
<svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Postman</title><path d="M13.527.099C6.955-.744.942 3.9.099 10.473c-.843 6.572 3.8 12.584 10.373 13.428 6.573.843 12.587-3.801 13.428-10.374C24.744 6.955 20.101.943 13.527.099zm2.471 7.485a.855.855 0 0 0-.593.25l-4.453 4.453-.307-.307-.643-.643c4.389-4.376 5.18-4.418 5.996-3.753zm-4.863 4.861l4.44-4.44a.62.62 0 1 1 .847.903l-4.699 4.125-.588-.588zm.33.694l-1.1.238a.06.06 0 0 1-.067-.032.06.06 0 0 1 .01-.073l.645-.645.512.512zm-2.803-.459l1.172-1.172.879.878-1.979.426a.074.074 0 0 1-.085-.039.072.072 0 0 1 .013-.093zm-3.646 6.058a.076.076 0 0 1-.069-.083.077.077 0 0 1 .022-.046h.002l.946-.946 1.222 1.222-2.123-.147zm2.425-1.256a.228.228 0 0 0-.117.256l.203.865a.125.125 0 0 1-.211.117h-.003l-.934-.934-.294-.295 3.762-3.758 1.82-.393.874.874c-1.255 1.102-2.971 2.201-5.1 3.268zm5.279-3.428h-.002l-.839-.839 4.699-4.125a.952.952 0 0 0 .119-.127c-.148 1.345-2.029 3.245-3.977 5.091zm3.657-6.46l-.003-.002a1.822 1.822 0 0 1 2.459-2.684l-1.61 1.613a.119.119 0 0 0 0 .169l1.247 1.247a1.817 1.817 0 0 1-2.093-.343zm2.578 0a1.714 1.714 0 0 1-.271.218h-.001l-1.207-1.207 1.533-1.533c.661.72.637 1.832-.054 2.522zM18.855 6.05a.143.143 0 0 0-.053.157.416.416 0 0 1-.053.45.14.14 0 0 0 .023.197.141.141 0 0 0 .084.03.14.14 0 0 0 .106-.05.691.691 0 0 0 .087-.751.138.138 0 0 0-.194-.033z"/></svg>
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
