# Docker

[CheeSheet](https://quickref.me/docker.html)

### Полезные команды

Поднять в фоне все сервисы, описанные в конфигурации:

```
docker compose up -d
```

Вывести список контейнеров:
```
docker compose ps
```

Вывести логи указанного сервиса (контейнера):
```
docker compose logs <service>
```

Рестартануть сервис:
```
docker compose restart <service>
```

Посмотреть итоговую конфигурацию контейнеров:
```
docker compose config
```

Остановить все контейнеры из текущей конфигурации:
```
docker compose stop
```

Удалить все контейнеры из текущей конфигурации:
```
docker compose rm
```

Остановить и удалить все контейнеры из текущей конфигурации (последовательное выполнение двух предыдущих команд):
```
docker compose down
```

Удалить все не запущенные контейнеры и все не использующиеся образы:
```
docker system prune --all
```

Вывести список образов:
```
docker images
```

### Docker. Работа с сетью
IP адреса в Линуксе
```
ip a
```


Показать сети в Докере
```
docker network ls
```

Создать сеть в Докере;
```
docker network create --driver host/bridge <Network>
```
или
```
docker network create --driver bridge backend
```


Исследовать сеть:
```
docker network inspect <Network>
```


Создать сеть:
```
docker network create - d bridge --subnet 192.168.10.0/24 --gatway 192.168.10.1 <Network>
```


Удалить сеть:
```
docker network rm <Network1> <Network2> ...
```


Контейнеры для тестирования работы сети:
[nicolaka/netshoot](https://hub.docker.com/r/nicolaka/netshoot)
```
docker run rm --rm -it --name netshoot nicolaka/netshoot /bin/bash
```
или
```
docker run rm --rm -it --name netshoot --net bridge nicolaka/netshoot /bin/bash
```


Создаем новую сеть и тестируем ее:
```
docker network create --driver bridge myNet
```
```
docker run --rm -it --name netshoot1 --net myNet nicolaka/netshoot /bin/bash
```
```
docker run --rm -it --name netshoot2 --net myNet nicolaka/netshoot /bin/bash
```
