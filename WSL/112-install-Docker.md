# WSL2でDockerを使用する

出典:[WSL2でのDockerリモートコンテナーの概要 | Microsoft Docs](https://docs.microsoft.com/ja-jp/windows/wsl/tutorials/wsl-containers)

## Docker Desktopのインストール

1. [Docker Desktop](https://docs.docker.com/desktop/windows/wsl/)をダウンロードし、インストールする
2. Docker Desktopを起動し、タスクバーのアイコンを右クリック、設定(Settings)を選択
3. 設定 > 全般(General) > WSL2ベースのエンジンを使用する(Use the WSL 2 based engine) がオンになっていることを確認する
4. 設定 > Resources > wsl integration に移動し、Docker結合を有効にするインストール済みのwsl2ディストリビューションを選択する
5. DockerがインストールされていることをWSL2で確認する

```shell
docker --version
```

## VS Codeを使用したリモートコンテナーでの開発

WSL2でDockerを使用したアプリの開発には、[Remote - WSLPreview 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) と [Remote - Containers 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) と [Docker 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) をVS Codeに導入することを推奨する。

WSL2を開き、以下のコマンドを実行する

```shell
mkdir test
cd test
code .
```
