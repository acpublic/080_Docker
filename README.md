## Dockerfile
- https://docs.docker.com/
- https://docs.docker.jp/index.html#

## Dockerfile
### https://qiita.com/gon0821/items/f9e3bcbb6cb01d4ef7fa
- FROM
- RUN
- CMD
- COPY
- ENV
- WORKDIR

## docker-compose.yml
### https://qiita.com/gon0821/items/77369def082745d19c38
- services
- image
- build
- volumes :ファイルをリアルタイム共有。コンテナ内ファイルを残す。
- environment
- ports
- depends_on



## コマンド
https://zenn.dev/en2enzo2/articles/95b73cacfe0eb1

## イメージ作成
```
docker build -t ubuntu-image:1.0 .
```

## コンテナ作成
```
docker container run -itd --name <コンテナIDまたはコンテナ名> ubuntu-image:1.0
```

## Docker Composeで起動
```
docker-compose up -d --build
```

## Dockerイメージを表示
```
docker images
```

##  実行中のコンテナを表示
```
docker ps
```

## すべてのコンテナを表示（停止中のコンテナも含む）
```
docker ps -a
```

## 停止したコンテナを起動
```
docker start <コンテナIDまたはコンテナ名>
```

## コンテナを停止
```
docker stop <コンテナIDまたはコンテナ名>
```

## コンテナに入る
```
docker container exec -it <コンテナIDまたはコンテナ名> /bin/bash
```
## コンテナ内ログ
```
docker logs <container_id>
```

## インストール
https://www.stuffy.site/computers/archives/12082
```
1．システムにインストール済みの古いDockerをアンインストール
$ for pkg in docker.io docker-doc docker-compose docker-compose-v2

2．apt のgpgキーをインストール
$ sudo apt-get update
$ sudo apt-get install ca-certificates curl
$ sudo install -m 0755 -d /etc/apt/keyrings
$ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
$ sudo chmod a+r /etc/apt/keyrings/docker.asc
$ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt-get update

3．docker, docker-compose, プラグインなどまとめてインストール
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

4．docker compose のバージョン確認

$ docker compose version
Docker Compose version v2.28.1

＄sudo usermod -aG docker $USER
```

## Ubuntu アンインストール
https://arkgame.com/2022/05/14/post-308016/
```
# dpkg -l | grep -i docker
ii docker-ce 5:20.10.15~3-0~ubuntu-jammy amd64 Docker: the open-source application container engine
ii docker-ce-cli 5:20.10.15~3-0~ubuntu-jammy amd64 Docker CLI: the open-source application container engine
ii docker-ce-rootless-extras 5:20.10.15~3-0~ubuntu-jammy amd64 Rootless support for Docker.
ii docker-scan-plugin 0.17.0~ubuntu-jammy amd64 Docker scan cli plugin.

# sudo apt-get purge -y docker-engine docker docker.io docker-ce docker-ce-cli
# sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce

# sudo rm -rf /var/lib/docker /etc/docker
# sudo groupdel docker
# sudo rm -rf /var/run/docker.sock

# docker --version
-bash: /usr/bin/docker: そのようなファイルやディレクトリはありません
```
## 使用例
https://qiita.com/ryome/items/ab23eeadf3c2ff6b35bd
https://zenn.dev/trailer/articles/5348cf57403acd

## Windows + WSL + docker + gitlab
https://qiita.com/magiclib/items/d0ec68886aead86ad510
