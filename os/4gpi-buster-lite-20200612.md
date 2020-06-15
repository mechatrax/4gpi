# 4gpi-buster-lite-20200612
Raspberry Pi OS (32-bit) Lite May 2020 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-buster-lite-20200612.zip](https://mechatrax.com/data/4gpi/4gpi-buster-lite-20200612.zip)  

イメージファイルのハッシュは次のとおりです。

| アルゴリズム | ハッシュ |
| :-- | :-- |
| SHA256 | f2aa44f68266993b819e64a7bf1378b8980c75558a1065cd406b597b9ecf01cb |
| SHA1 | 06949ef5ccc9a0fa6065fe8c0125b9c659d1566b |
| MD5 | 1d17bd991533882b981f64630eb86a59 |

## 変更内容
  * 4GPi 用パッケージをインストール
  * 4G/LTE ネットワークの管理に NetworkManager を使用
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の metadata_csum と 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * APT::Periodic の無効化
  * avahi-daemon で ppp0 と wwan0 を無視
  * Raspbian のパッケージを 20200612 時点の最新版に更新

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
    soracom-cli  

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
