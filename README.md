https://docs.docker.com/

https://docs.docker.jp/index.html#

## インストール

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


## Windows + WSL + docker + gitlab
https://qiita.com/magiclib/items/d0ec68886aead86ad510
