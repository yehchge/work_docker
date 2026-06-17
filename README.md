# My Local Office Docker

## How to Remove all Docker images

```bash
$ docker system prune -a
```

## How to Run docker-composer ?
### Remember stop local apache2 or httpd, because docker will use port: 80

```bash
$ docker compose up
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

### 套用更改

```bash
docker compose up -d --force-recreate
```

### 重新編譯並啟動

因為修改了 Dockerfile，必須強制 Docker 重新建置（Rebuild）才能載入新模組：

```bash
# 1. 停止並編譯
docker compose down
docker compose up -d --build
```


### 修改完 docker compose 腳本, 要重新部屬

```bash
docker compose up -d --build (對所有服務)
docker compose up -d --build <服務名稱> (對特定服務)
```

# 加入此行到 ~/.bashrc
alias dphp='docker compose exec php-fpm php'

# 之後你就可以直接執行
dphp -v
dphp /var/www/html/test.php
dphp artisan schedule:run


alias dphp='docker compose -f /data/sites/work_docker/docker-compose.yml exec -it php-fpm php'

# 因為你將資料庫放在 /data/mysql，請確保該目錄的權限允許 Docker 讀寫：
sudo chown -R 999:999 /data/mysql  # 999 通常是 MySQL 容器內的用戶 ID