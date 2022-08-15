# 4gpi-bullseye-lite-armhf-20220815
Raspberry Pi OS (32-bit) Lite April 4th 2022 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-bullseye-lite-armhf-20220815.img.xz](https://mechatrax.com/data/4gpi/4gpi-bullseye-lite-armhf-20220815.img.xz)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
2e99634bd2dfcd7a294cf69936aad5f6eebb229d99f4c06218f74d711dcc0c82
```

## 変更内容
Raspberry Pi OS からの変更内容は次のとおりです。
  * 4GPi 用パッケージをインストール
  * 4G/LTE ネットワークの管理に NetworkManager を使用
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の metadata_csum と 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * APT::Periodic の無効化
  * avahi-daemon で ppp0 と wwan0 を無視
  * Raspbian のパッケージを 20220815 時点の最新版に更新

## インストールパッケージ
  * Raspbian パッケージ  
    jo  
    jq  
    modemmanager  
    network-manager  
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
    gcc-8-base  
    gcc-9-base  
    libfribidi0  
    libident  
    libraspberrypi-doc  
    libreadline6  
    libsigc++-1.2-5c2  
    rng-tools
  
  * 常駐プロセス削減のため削除  
    triggerhappy  
    udisks2

