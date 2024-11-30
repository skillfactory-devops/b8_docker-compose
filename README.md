# Модуль B8. Docker-Compose

## Проектная работа

* Добавил исходники приложения с помощью `git submodule`,
* Создал docker-compose.yml с двумя сервисами: php и nginx,
* Протестировал, убедился в работоспособности:
```
$ curl localhost
<html>
 <head>
  <title>Test PHP</title>
 </head>
 <body>
 <p>It works!</p> </body>
</html>
```
* Добавил healthcheck для php-сервиса,
* Увидел в логах контейнера отдачу контента браузеру и проверки healthckeck:
```
$ docker compose up
…
php-1    | 172.21.0.3 -  30/Nov/2024:17:26:43 +0000 "GET /index.php" 200
nginx-1  | 172.21.0.1 - - [30/Nov/2024:17:26:43 +0000] "GET / HTTP/1.1" 200 103 "-" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.6613.648 YaBrowser/24.10.4.648 (beta) Yowser/2.5 Safari/537.36"
php-1    | 172.21.0.3 -  30/Nov/2024:17:26:45 +0000 "GET /index.php" 200
nginx-1  | 172.21.0.1 - - [30/Nov/2024:17:26:45 +0000] "GET / HTTP/1.1" 200 103 "-" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.6613.648 YaBrowser/24.10.4.648 (beta) Yowser/2.5 Safari/537.36"
php-1    | 172.21.0.3 -  30/Nov/2024:17:26:59 +0000 "GET /index.php" 200
nginx-1  | 172.21.0.2 - - [30/Nov/2024:17:26:59 +0000] "GET / HTTP/1.1" 200 103 "-" "curl/7.74.0"
php-1    | 172.21.0.3 -  30/Nov/2024:17:27:30 +0000 "GET /index.php" 200
nginx-1  | 172.21.0.2 - - [30/Nov/2024:17:27:30 +0000] "GET / HTTP/1.1" 200 103 "-" "curl/7.74.0"
php-1    | 172.21.0.3 -  30/Nov/2024:17:28:00 +0000 "GET /index.php" 200
nginx-1  | 172.21.0.2 - - [30/Nov/2024:17:28:00 +0000] "GET / HTTP/1.1" 200 103 "-" "curl/7.74.0"
```
