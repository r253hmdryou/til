# Windows Subsystem for Linux 2 を使ってみる

## WSLとは

簡単に言うと、Windows上でHyper-Vを使用せずにLinuxを使用する技術らしい。

出典:[Linux 用 Windows サブシステムとは | Microsoft Docs](https://docs.microsoft.com/ja-jp/windows/wsl/about)

細かいことを言えば、Hyper-Vのコア機能であるHyper-Vアーキテクチャと、それを利用したHyper-Vコンテナーの上で動いている。
Hyper-V自体はWindows Proでしか動かないが、コア機能及びコンテナはWindows Homeでも動くとのこと。

出典:[WSL2とHyper-Vの関係](https://qiita.com/matarillo/items/ca1eecf8f9a3cd76f9ce)

## WSL1とWSL2の比較

出典:[WSL1 と WSL2 の比較 | Microsoft Docs](https://docs.microsoft.com/ja-jp/windows/wsl/compare-versions)

基本的にはWSL2の方が高機能なため、原則はWSL2を使用することになる。
ただし例外がいくつかある。

### Windows のファイルを参照する場合

プロジェクトファイルをWindows ファイルシステムに格納し、Linux にマウントするシナリオにおいてはWSL1の方がパフォーマンスが期待できる。

### シリアルポートまたはUSBデバイスへのアクセスが必要な場合

WSL2ではシリアルポートにアクセスできない。

### 厳密なメモリ要件がある

WSL2ではWSLインスタンスがシャットダウンされるまでメモリ内のキャッシュページが開放されてWindowsに戻ることがない。
そのためWSLセッションが長時間実行されている場合や非常に大量のファイルにアクセスする場合はこれらのキャッシュによりWindows上のメモリが専有される可能性がある。
