# OS イメージ（Legacy）
ここでは、4GPi 用の Legacy 版 OS イメージに関する技術資料等を公開しています。

## 概要
OS には Raspberry Pi OS (Raspbian) Legacy を採用し、4GPi の動作に必要なツールをセットアップしています。

4G/LTE のネットワークの管理に NetworkManager を使用しています。  
使用する SIM に応じて[接続設定](../../../wiki/その他#接続設定)を行ってください。

ファイアウォールに ufw を使用しています。  
標準で 4GPi の受信ポートをブロックしています。

詳細についてはリリースノートのリンク先を参照してください。

ansible を使用して同等の環境を構築することもできます。  
詳細はリンク先を参照してください。  
https://github.com/mechatrax/ansible-mechatrax-playbook

## 初期ログイン情報カード
4GPi 用 microSD カードに付属している初期ログイン情報カードの .pdf ファイルを公開しています。  
次のリンクから直接ファイルをダウンロードできます。  
[初期ログイン情報カード](../../../raw/main/os-legacy/login.pdf)

## リリースノート
4GPi 用の Legacy 版 OS イメージのリリースノートを公開しています。

* ### 4gpi-buster-lite-armhf-20230309
  20230309 の記載があるものは本リリースの OS イメージがインストールされています。  
  詳細は、[4gpi-buster-lite-armhf-20230309.md](./4gpi-buster-lite-armhf-20230309.md) を参照してください。

* ### 4gpi-buster-lite-armhf-20220727
  20220727 の記載があるものは本リリースの OS イメージがインストールされています。  
  詳細は、[4gpi-buster-lite-armhf-20220727.md](./4gpi-buster-lite-armhf-20220727.md) を参照してください。

* ### 4gpi-buster-lite-20220202
  20220202 の記載があるものは本リリースの OS イメージがインストールされています。  
  詳細は、[4gpi-buster-lite-20220202.md](./4gpi-buster-lite-20220202.md) を参照してください。

* ### 4gpi-buster-lite-20220114
  20220114 の記載があるものは本リリースの OS イメージがインストールされています。  
  詳細は、[4gpi-buster-lite-20220114.md](./4gpi-buster-lite-20220114.md) を参照してください。

