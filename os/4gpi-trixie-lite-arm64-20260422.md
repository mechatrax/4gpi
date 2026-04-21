# 4gpi-trixie-lite-arm64-20260422
Raspberry Pi OS (64-bit) Lite April 21st 2026 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-trixie-lite-arm64-20260422.img.xz](https://mechatrax.com/data/4gpi/4gpi-trixie-lite-arm64-20260422.img.xz)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
1b103311f0dbf7ab86dc5d0de59e86a62d922cb2b71dbf655ffe886631b9b441
```

## 変更内容
Raspberry Pi OS からの変更内容は次のとおりです。
  * 4GPi 用パッケージをインストール
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * APT::Periodic の無効化
  * avahi-daemon で ppp0 と wwan0 を無視
  * パッケージを 20260422 時点の最新版に更新

## インストールパッケージ
  * Raspbian パッケージ  
    jo  
    jq  
    ufw

  * 独自パッケージ  
    4gpi-utils  
    4gpi-net-mods  
    4gpi-networkmanager  

  * その他パッケージ  
    soracom

## 削除パッケージ  
  * 常駐プロセス削減のため削除  
    udisks2

