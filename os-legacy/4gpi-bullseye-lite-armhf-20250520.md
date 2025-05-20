# 4gpi-bullseye-lite-armhf-20250520
Raspberry Pi OS (32-bit) Lite (Legacy) May 6th 2025 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-bullseye-lite-armhf-20250520.img.xz](https://mechatrax.com/data/4gpi/4gpi-bullseye-lite-armhf-20250520.img.xz)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
4af365c6f53d7fcb398a81fac3a564b535568f5bacf583d782a8aef2d26d6b2b
```

## 変更内容
Raspberry Pi OS からの変更内容は次のとおりです。
  * 4GPi 用パッケージをインストール
  * 4G/LTE ネットワークの管理に NetworkManager を使用
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * APT::Periodic の無効化
  * avahi-daemon で ppp0 と wwan0 を無視
  * WiFi の地域設定を日本（JP）に設定
  * Raspbian のパッケージを 20250520 時点の最新版に更新

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
  * 不要なライブラリ等を削除  
    eject  
    mksh  
    gcc-8-base  
    gcc-9-base  
    libfribidi0  
    libident  
    libraspberrypi-doc  
    libreadline6  
    libsigc++-1.2-5c2  
    raspinfo  
    rng-tools
  
  * 常駐プロセス削減のため削除  
    triggerhappy  
    udisks2

