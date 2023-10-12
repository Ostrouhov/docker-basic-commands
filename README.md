# Docker - базовые команды
## Начальные команды
> **docker** - справка по всем командам
> 
> **docker -v** - версия Docker`а
> 
> **docker ps** - список запущенных контейнеров
> 
> **docker ps -all** - список всех контейнеров
## Задание 1
> **docker run -p 3306:3306 --name my-mysql -e MYSQL_ROOT_PASSWORD=pass -d mysql** - сразу прописываем порты для удаленного доступа к серверу MySQL (-p 3306:3306), присваеваем контейнеру удобное нам имя (--name my-mysql), указываем одну из переменных окружения, а именно пароль для пользователя root, т.е. для администратора (-e MYSQL_ROOT_PASSWORD=pass), запускаем контейнер в фоновом режиме (-d), имя образца (IMAGE), который docker должен развернуть в контейнере (mysql)
>
> **pull redis:lattes** - имя IMAGE - redis, latest - последняя версия. После успешного скачивания образа он появится в списке Images в Docker Desktop, но в Containers его еще нет
>
> **docker run --name my-redis -d redis** - имя будущего контейнера - my-redis, имя образа - redis. После этого контейнер появится в списке Containers в Docker Desktop.
## Заданеи 2
>**docker pull mongo:5.0**
>
>**docker run --name my-mongo -d mongo: 5.0** - скачиваем и устанавливаем MongoDB версии 5.0 и называем контейнер my-mongo
## Команды внутри контейнера
>**docker exec -it my-redis redis-cli** - -it - опция, включающая интерактивный режим работы, my-redis - имя контейнера, redis-cli - команда для Redis, запустить клиент
>
>**docker exec -it my-sql mysql -uroot -ppass** - mysql -uroot -ppass - команда самого MySQL, запускает консоль MySQL, с опциями -u и -p, логин и пароль соответственно
## Задание 3
>**docker exec -it my-mongo mongo** - запускаем консоль MongoDB
>
>**db.version()** - Узнаем версию MongoDB
>
>**exit** - команда выхода из консоли
## Команды остановки и старта контейнеров
>**docker stop my-mysql my-redis my-mongo** - останавливаются все перечисленные контейнеры
>
>**docker start my-mysql** - запускает указанные контейнер
