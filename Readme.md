# docker-mirakurun-epgstation-for-raspi4
[docker-mirakurun-epgstation](https://github.com/l3tnun/docker-mirakurun-epgstation)をRaspberry Pi 4で動かせるようにしたもの．

## 前提条件
- Raspberry Pi 4
  - (推奨) 外部ストレージの利用とマウント
- Docker, docker-compose の導入が必須

## インストール手順
- gitからrepositoryをcloneしてきて，dockerのビルドを行います．
```sh
$ git clone https://github.com/wan-nyan-wan/docker-mirakurun-epgstation-for-raspi4.git
$ cd docker-mirakurun-epgstation-for-raspi4
$ sudo docker-compose pull
$ sudo docker-compose build
```

## 起動

```sh
$ sudo docker-compose up -d
```
mirakurun の EPG 更新を待ってからブラウザで http://DockerHostIP:8888 へアクセスし動作を確認する

## 停止

```sh
$ sudo docker-compose down
```

## 設定

### Mirakurun

* ポート番号: 40772

### EPGStation

* ポート番号: 8888
* ポート番号: 8889

### 各種ファイル保存先
- HDD等の外部ストレージに保存先を書き換える場合は，外部ストレージをそれぞれのフォルダへとマウントする．
- 録画データ
```./recorded```
- サムネイル
```./epgstation/thumbnail```
- 予約情報と HLS 配信時の一時ファイル
```./epgstation/data```
- EPGStation 設定ファイル
```./epgstation/config```
- EPGStation のログ
```./epgstation/logs```
