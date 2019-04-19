# 4gpi-stretch-lite-20190419
Raspbian Stretch Lite Release 2019-04-08 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-stretch-lite-20190419.zip](https://mechatrax.com/data/4gpi/4gpi-stretch-lite-20190419.zip)  

イメージファイルのハッシュは次のとおりです。  
SHA256: 31f232f938a130544d188c41848e250a24091b006193d30dfcf91060b5b0ed9a  
SHA1: 4748215a168b0529c2e9da534f3cbc701addeeeb  
MD5: c48c405ba5575b718eb8012bb2d76074

## 変更内容
  * 4GPi 用パッケージをインストール
  * 4G/LTE ネットワークの管理に NetworkManager を使用
  * ファイアウォールに ufw を使用（デフォルトは許可、wwan0 と ppp0 のみ受信拒否）
  * シリアルコンソールを有効化
  * rootfs で ext4 の ⁠metadata_csum と 64bit オプションを有効化
  * ハードウェアウォッチドッグタイマの監視に systemd を使用
  * systemd-timesyncd の停止
  * APT::Periodic の無効化
  * Raspbian のパッケージを 20190419 時点の最新版に更新

## インストールパッケージ
  * Raspbian パッケージ  
    jo  
    jq  
    modemmanager  
    network-manager  
    ntpdate  
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
