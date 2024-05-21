---
sidebar_position: 2
---

# ビルドの起動方法
:::warning
IPAddressを指定してリモート端末で実行する場合は、`Port:8818`にビルドを動かす端末からアクセス出来る必要があります。接続できない場合はネットワーク設定を確認してください。
:::
## Windows
- 起動する端末がPolyQAが動いている端末の場合
  - 何も設定する必要は無いのでそのまま起動してください
- 起動する端末がPolyQAを動いている端末と**違う**場合
  - 起動時にコマンドライン引数で、PolyQAが動いているマシンのIPAddressを与える必要があります
:::info 例
`GamePlayerFromUnity.exe -polyqa_address 192.168.10.8`
:::

## Android
- adbコマンドを用いて起動をして、インテント引数の設定をする必要があります
- adbコマンドでUnityアプリを起動する方法は `adb shell am start -n <パッケージ名>/<アクティビティ名>`
:::info 例
`adb shell am start -n com.HogeCompany.HogeProduct/com.unity3d.player.UnityPlayerActivity`
:::
- stringで*polyqa_address*という引数にIPAddressを入れて呼び出します
:::info 例
`adb shell am start -n com.HogeCompany.HogeProduct/com.unity3d.player.UnityPlayerActivity --es "polyqa_address" 192.168.10.8`
:::