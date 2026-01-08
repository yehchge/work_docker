# My Local Office Docker

## How to Remove all Docker images

```bash
$ docker system prune -a
```

## How to Run docker-composer ?
### Remember stop local apache2 or httpd, because docker will use port: 80

```bash
$ docker-compose up
```

ref: https://www.itread01.com/content/1549814584.html

ref: https://teratail.com/questions/161849

Mongo
ref: https://testerhome.com/topics/12768
ref: https://hub.docker.com/_/mongo

### 部屬 portainer

```bash
docker compose -f portainer-compose.yaml up -d
```

### 修改完 docker compose 腳本, 要重新部屬

```bash
docker compose up -d --build (對所有服務)
docker compose up -d --build <服務名稱> (對特定服務)
```