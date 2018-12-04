
# Установка

### Запуск и сборка окружения
    docker-compose up --build

### Структура приложения
    |-httpd
        |-log
            |-error_log
        |-httpd.conf
    |-mysql
        |-config
            |-my.cnf
        |-data
        |-dump
    |-nginx
        |-certs
        |-log
            |-access.log
            |-error.log
        |-nginx.conf
    |-php
        |-Dockerfile
        |-php.ini
    |-phpmyadmin
    |-src
    |-docker-compose.yml
    |-README.md

### Создание SSL Сертификата

#### Генерируем ключ безопасности
    openssl genrsa -out server.key 2048
#### Генерируем файл на запрос сертификата
    openssl req -new -key server.key -out %имя_вашего_сайта%.csr
#### Создаем самоподписанный сертификат
    openssl x509 -req -extensions v3_req -days 365 -in %your_website%.csr -signkey server.key -out %your_website%.crt
***
