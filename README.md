<!--
  Copyright 2019 Ryosuke Tsutsum.
  Licensed under the terms of the MIT license.
  See LICENSE in the project root.
-->
# vespa-sample

## dockerの準備
詳細は[公式doc](https://docs.docker.com/install/linux/docker-ce/centos/)
古いバージョンのアンインストール
``` bash
$ sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```
リポジトリをセットアップ
``` bash
$ sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
$ sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```
最新バージョンのインストール
``` bash
$ sudo yum install docker-ce docker-ce-cli containerd.io
```
起動
``` bash
$ sudo systemctl restart docker 
```
確認
``` bash
$ docker -v
```

## docker-composeの準備
詳細は[公式doc](https://docs.docker.com/compose/install/)
``` bash
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Usage
Rootディレクトリ(docker-compose.ymlのあるディレクトリ)でdocker-composeにて起動
``` bash
$ sudo docker-compose up -d
```


## ライセンス
このコードは MIT ライセンスにて提供しています。
詳しくは LICENSE ファイルをご確認ください。

