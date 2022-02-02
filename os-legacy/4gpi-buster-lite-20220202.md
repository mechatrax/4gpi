# 4gpi-buster-lite-20220202
Raspberry Pi OS (32-bit) Lite (Legacy) January 28th 2022 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-buster-lite-20220202.zip](https://mechatrax.com/data/4gpi-legacy/4gpi-buster-lite-20220202.zip)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
325fe2608143bbcf960103f34c7ee7d9294a5a95c72827d7425866e830a2b935
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
  * Raspbian のパッケージを 20220202 時点の最新版に更新

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
    gcc-4.9-base  
    gcc-5-base  
    gcc-6-base  
    gcc-7-base  
    libboost-iostreams1.58.0  
    libudev0  
    libsigc++-1.2-5c2

  * 容量削減のため削除  
    freetype2-doc  
    libraspberrypi-doc

  * 常駐プロセス削減のため削除  
    triggerhappy

