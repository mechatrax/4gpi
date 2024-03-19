# 4gpi-bookworm-lite-arm64-20240320
Raspberry Pi OS (64-bit) Lite March 15th 2024 を元に変更を加えています。

## イメージファイル
イメージファイルは次のリンクからダウンロードできます。  
[4gpi-bookworm-lite-arm64-20240320.img.xz](https://mechatrax.com/data/4gpi/4gpi-bookworm-lite-arm64-20240320.img.xz)  

イメージファイルの SHA256 ハッシュ値は次のとおりです。
```
616e74a828b9e4c37a0a283e854bdecba82bc1dad6ffdec2899df95f88da41c1
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
  * NetworkManager の radio 設定にて WiFi を無効化
  * パッケージを 20240320 時点の最新版に更新

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

