# docker 練習

建立 `nginx` `php-fpm` `mairadb` `memcached` 等開發環境。

The following three separate service containers will be used:

- An `app` service running PHP 8 FPM.
- A `db` service running MySQL.
- An `nginx` service that uses the `app` service to parse PHP code before serving the application to the final user.

## 環境設定

- copy env-sample 檔為 .env ，設定 Mairadb 及 mongodb 環境變數。


- 啟動 docker :

```bash
docker-compose up -d
```

- 查看作用中的 service container ， 執行指令:

```bash
docker-compose ps
```

你可使用 `docker-compose exec` 指令執行 container 的指令，例如 `ls -l` 列出 container 內的目錄及檔案 :

```bash
docker-compose exec app ls -l
```

- 打開瀏覽器連至 http://localhost:9910 ，可以看到 php 的版本訊息。

- 打開瀏覽器連至 http://localhost:9911 ，可以看到 phpMyAdmin。

- 你可以使用下列指令檢查 `nginx` 的 log 訊息 :

```bash
docker-compose logs nginx
```

- 如果要暫停  Docker Compose 執行環境，執行:

```bash
docker-compose pause
```

- 動啟 services ， 執行:

```bash
docker-compose unpause
```

- 如果要卸載 Docker Compose 環境並移除所有的 containers, networks, volumes, 執行:

```bash
docker-compose down
```
