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