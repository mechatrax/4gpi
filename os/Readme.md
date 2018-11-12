# OS イメージ
ここでは、4GPi 用の SD カードの OS イメージに関する技術資料等を公開しています。

## 概要
OS には Raspbian を採用し、4GPi に必要なツールのセットアップを完了しています。

4G/LTE のネットワークの管理に NetworkManager を使用しています。  
使用する SIM に応じて[接続設定](../../../wiki/その他#接続設定)を行ってください。

ファイアウォールに ufw を使用しています。  
標準で 4GPi の受信ポートをブロックしています。

詳細についてはリリースノートのリンク先を参照してください。  

ansible を使用して同等の環境を構築することもできます。  
詳細はリンク先を参照してください。  
https://github.com/mechatrax/ansible-4gpi-playbook

## 初期ログイン情報カード
4GPi 用 microSD カードに付属している初期ログイン情報カードの .pdf ファイルを公開しています。  
次のリンクから直接ファイルをダウンロードできます。  
[初期ログイン情報カード](../../../raw/master/os/login.pdf)

## リリースノート
4GPi 用 microSD カードにインストールされている OS イメージのリリースノートを公開しています。

### 4gpi-stretch-lite-20181029
  20181029 の記載があるものは本リリースの OS イメージがインストールされています。  
  詳細は、[4gpi-stretch-lite-20181029.md](./4gpi-stretch-lite-20181029.md) を参照してください。