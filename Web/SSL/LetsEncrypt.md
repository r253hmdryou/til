# 概要

Let's Encrypt で証明書を発行する

## 手順

### 準備

Hyper-V にてUbuntuの仮想環境を用意
version: 20.04

疎通確認

```shell
ping 8.8.8.8
ping google.com
```

SSH接続できるように

```shell
sudo apt update
sudo apt install ssh -y

ip a s
```

SSH接続

参考: https://certbot.eff.org/instructions
https://dacelo.space/lets-encrypt/entry-1232.html
( https://eff-certbot.readthedocs.io/en/stable/install.html#snap )

webサーバー

```shell
sudo apt install nginx -y
sudo service nginx start
```

証明書発行サーバー

```shell
sudo apt install snapd

sudo snap install core
sudo snap refresh core
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
sudo certbot certonly --manual
xxx.domain.example.com
```

webサーバー

```shell
echo "xxx" > file
```

証明書発行サーバー

```shell
[Enter]

# 秘密鍵
sudo cat /etc/letsencrypt/live/xxx.domain.example.com/privkey.pem
# 証明書
sudo cat /etc/letsencrypt/live/xxx.domain.example.com/cert.pem
# 中間証明
sudo cat /etc/letsencrypt/live/xxx.domain.example.com/chain.pem
```
