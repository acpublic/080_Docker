https://docs.docker.com/

https://docs.docker.jp/index.html#

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

gusachan@shop:~$ docker compose version
Docker Compose version v2.28.1
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

## Windows + WSL + docker + gitlab
https://qiita.com/magiclib/items/d0ec68886aead86ad510
