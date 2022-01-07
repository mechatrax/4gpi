# 4gpi-bullseye-lite-20220105
Raspberry Pi OS (32-bit) Lite October 30th 2021 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-buster-lite-20220105.zip](https://mechatrax.com/data/4gpi/4gpi-bullseye-lite-20220105.zip)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
53b5c49da8c232f35a3959b46b3504310c1711950d18163c529dfced15e18279
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
  * Raspbian のパッケージを 20220105 時点の最新版に更新

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


