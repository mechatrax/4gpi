# 4gpi-stretch-lite-20181029
RASPBIAN STRETCH LITE October 2018 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-stretch-lite-20181029.zip](https://mechatrax.com/data/4gpi/4gpi-stretch-lite-20181029.zip)  

イメージファイルのハッシュは次のとおりです。  
SHA256: 9c326e523031162e73dc03bbc9c9793d3a041b3730985e5d26a32f92f51a421f  
SHA1: ef64151d2943f6565a0746202128f6e8e1a9d732  
MD5: 7c195eee0bdc73450289497f33a4adce  

## 変更内容
  * 4GPi 用パッケージをインストール
  * 4G/LTE ネットワークの管理に NetworkManager を使用
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の ⁠metadata_csum と 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * ハードウェア乱数生成器の利用に rng-tools を使用
  * systemd-timesyncd の停止
  * APT::Periodic の無効化
  * Raspbian のパッケージを 20181029 時点の最新版に更新

## インストールパッケージ
  * Raspbian パッケージ  
    jo  
    jq  
    gpsd  
    gpsd-clients  
    modemmanager  
    network-manager  
    ntpdate  
    rng-tools  
    ufw

  * 独自パッケージ  
    4gpi-utils  
    4gpi-net-mods  
    4gpi-networkmanager  
    mechatrax-archive-keyring  
    soracom-cli  

## 削除パッケージ  
  * 不要なライブラリ等を削除  
    gcc-4.6-base  
    gcc-4.7-base  
    gcc-4.8-base  
    gcc-4.9-base  
    gcc-5-base  
    libboost-iostreams1.58.0  
    libboost-iostreams1.60.0  
    libudev0  
    libsigc++-1.2-5c2
