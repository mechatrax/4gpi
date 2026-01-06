# 4gpi-trixie-lite-arm64-20260106
Raspberry Pi OS (64-bit) Lite December 4th 2025 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-trixie-lite-arm64-20260106.img.xz](https://mechatrax.com/data/4gpi/4gpi-trixie-lite-arm64-20260106.img.xz)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
4a9e741d7c7812840c8e89cebde531ed414fbda2054cfc48fa488f8880274197
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
  * パッケージを 20260106 時点の最新版に更新

## インストールパッケージ
  * Raspbian パッケージ  
    jo  
    jq  
    ufw

  * 独自パッケージ  
    4gpi-utils  
    4gpi-net-mods  
    4gpi-networkmanager  
    mechatrax-archive-keyring

  * その他パッケージ  
    soracom

## 削除パッケージ  
  * 常駐プロセス削減のため削除  
    triggerhappy  
    udisks2

