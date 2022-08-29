* Командой sudo docker build -f Dockerfile -t hello_world:1.0 . собираем докер файл
* Запускаем контейнер командой sudo docker run --name test -p 80:81 -t -d a5faaaa1ee37 bash

![](Screen%20Shot%202022-08-28%20at%205.49.33%20PM.png)

*  Получаем по 80 порту нашу страничку

![](Screen%20Shot%202022-08-28%20at%205.50.32%20PM.png)

* Дописать в ./nginx/nginx.conf проксирование странички /status, по которой надо отдавать статус сервера nginx status

![](Screen%20Shot%202022-08-28%20at%206.42.18%20PM.png)