# Модуль B8. Docker-Compose

## [Задания 8.x](https://github.com/skillfactory-devops/b7_docker/tree/main/task%20B8.3)

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