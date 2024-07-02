---
sidebar_position: 2
---

# Android

:::warning
PolyQAを使用するためには、ゲームとの接続に使用するネットワークにおいて、ポート `8818` での受信接続を許可していただく必要があります。
:::

PolyQAに接続するためにいくつかの起動方法を用意しています。
環境に合わせてご利用できる起動方法を使用してください。

## 自動接続

ローカルネットワーク内からPolyQAを検索して接続しますので、まずはそのまま起動してください。

:::warning
ネットワーク設定により、ローカルネットワーク内での検索が制限されている場合がございます。
その場合、この機能は利用できませんので、他の起動方法を使用してください
:::

## QRコードで起動する

PolyQAの「Config」画面でゲームの起動URL（Deep Link）を設定してください。

![](./img/application_link.png)

「Receiver」画面で「Launch Game」ボタンを押してください

![](./img/launch_game.png)

QRコードが表示されますので、Androidのカメラで読み取ったURLからゲームを起動してください。

:::warning
Android標準のカメラアプリですと、読み取ったURLからゲームを起動できない場合があります。
その場合は、QRコードアプリをお試しください
:::

:::tip
インストール後、初回だけQRコードから起動する必要があります。前回の接続先は保存されるので、２回目以降は不要です。
一度アンインストールした場合は、再度QRコードから起動する必要があります。
:::

## adbコマンドで起動する

- adbコマンドを使用して、インテント引数にIPアドレスを設定して起動します。
- adbコマンドでUnityアプリを起動する方法は下記となります。

```
adb shell am start -n <パッケージ名>/<アクティビティ名>
```

:::info 例
`adb shell am start -n com.HogeCompany.HogeProduct/com.unity3d.player.UnityPlayerActivity`
:::

- *polyqa_address*という引数にIPアドレスを設定して呼び出します

:::info 例
`adb shell am start -n com.HogeCompany.HogeProduct/com.unity3d.player.UnityPlayerActivity --es "polyqa_address" 192.168.10.8`
:::

:::tip
インストール後、初回だけadbコマンドを使用して起動する必要があります。前回の接続先は保存されるので、２回目以降は不要です。
一度アンインストールした場合は、再度adbコマンドを使用して起動する必要があります。
:::