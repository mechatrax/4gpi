# 4gpi-buster-lite-20191120
Raspbian Buster Lite September 2019 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-buster-lite-20191120.zip](https://mechatrax.com/data/4gpi/4gpi-buster-lite-20191120.zip)  

イメージファイルのハッシュは次のとおりです。

| アルゴリズム | ハッシュ |
| :-- | :-- |
| SHA256 | e5a7105d273bce6599bae40aadef1aad1d232fb5ccf71c01e87f8691c774fbd8 |
| SHA1 | 2b351449938815cfc54fdb0cc083f938e4b46b51 |
| MD5 | 1e9345a7a00df28e7a63ff82fc202372 |

## 変更内容
  * 4GPi 用パッケージをインストール
  * 4G/LTE ネットワークの管理に NetworkManager を使用
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の ⁠metadata_csum と 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * APT::Periodic の無効化
  * Raspbian のパッケージを 20191120 時点の最新版に更新

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
    avahi-daemon  
    triggerhappy

