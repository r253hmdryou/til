# Installation

出典:[WSL 開発環境を設定するためのベストプラクティス](https://docs.microsoft.com/ja-jp/windows/wsl/setup/environment#set-up-your-linux-user-info)

注意！Windowsの初期セットアップ時に色々と準備をしてしまっているため、すべての環境で当てはまる手順では無いと思う。

## 前提

Windows 10 version 2004 以降(ビルド 19041 以降)
またはWindows 11

```PowerShell
PS> winver
```

## WSL2のインストール

```PowerShell
PS> wsl --install
```

以下が実行される

- 必要なオプションコンポーネントの有効化
- 最新Linuxカーネルのダウンロード
- WSL2の既定としての設定
- Linuxディストリビューションのインストール(既定ではUbuntu)

既定のバージョンの確認

```PowerShell
PS> wsl --status
```

>既定のバージョン: 2
>
>Linux 用 Windows サブシステムの最終更新日: 2021/11/14
>WSL の自動更新が有効になっています。
>
>カーネル バージョン: 5.10.16

## ユーザー情報の設定

インストールされたLinuxディストリビューションを起動すると、初回起動時にユーザー名とパスワードを設定するよう求められる。

```shell
Installing, this may take a few minutes...
Please create a default UNIX user account. The username does not need to match your Windows username.
For more information visit: https://aka.ms/wslusers
Enter new UNIX username:
Retype new password:
passwd: password updated successfully
Installation successful!
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.10.16.3-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sun Nov 14 11:11:53 JST 2021

  System load:  0.02               Processes:             8
  Usage of /:   0.5% of 250.98GB   Users logged in:       0
  Memory usage: 0%                 IPv4 address for eth0: 172.22.235.76
  Swap usage:   0%

1 update can be applied immediately.
To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


This message is shown once a day. To disable it please create the
```

## パッケージ更新とアップデート

```Bash
sudo apt update
sudo apt upgrade
```
