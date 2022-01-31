# 4gpi-bullseye-lite-20220131
Raspberry Pi OS (32-bit) Lite January 28th 2022 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-bullseye-lite-20220131.zip](https://mechatrax.com/data/4gpi/4gpi-bullseye-lite-20220131.zip)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
8edf209bbf1617d74e200cfcd4f0c58ae768e2d971825fa4e95d38a486f6df0b
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
  * Raspbian のパッケージを 20220131 時点の最新版に更新

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

