# 4gpi-bookworm-lite-arm64-20250508
Raspberry Pi OS (64-bit) Lite May 6th 2025 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-bookworm-lite-arm64-20250508.img.xz](https://mechatrax.com/data/4gpi/4gpi-bookworm-lite-arm64-20250508.img.xz)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
c3fc997abe81ed2b45015053561655c30acc962cf385606402ce55cbf6ab1d7c
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
  * パッケージを 20250508 時点の最新版に更新

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

