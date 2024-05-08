---
sidebar_position: 3
sidebar_label: CLI
---

# CLI
コマンドラインモードで起動することで、AutoPlayをバッチ処理化することが出来ます。

## コマンド
- **--cli**
  - CLIモードで起動するオプション
- **--autoRun**
  - 自動でアプリケーションを実行する
  - アプリケーションパスはConfigに設定されているパスが使われる
- **--timeout \<minutes>**
  - 実行する時間を分単位で設定する
  - 例）**PolyQA.exe --cli --autoRun --timeout 20**
- **--output \<folder>**
  - 結果を出力するフォルダを設定する
  - 例）**PolyQA.exe --cli --autoRun --timeout 20 --output ExampleFolder**