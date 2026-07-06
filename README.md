# Translation Filter

ゲーム画面などをキャプチャして文字を検出し、その場所に翻訳結果を重ねて表示するツールです。単一のHTMLファイル(`TranslateFilter.html`)をブラウザで開くだけで動作します。

## 使い方

1. `TranslateFilter.html` をブラウザ(Chrome推奨)で開く
2. Google Cloud APIキーを入力して保存
3. 「画面を選択」でキャプチャしたい画面・ウィンドウ・タブを選ぶ
4. 「翻訳」ボタンで、その瞬間の画面を翻訳して重ねて表示

APIキーはブラウザのlocalStorageにのみ保存され、外部には送信されません。

## APIキーの取得方法

このツールはGoogle Cloudの **Cloud Vision API**(文字認識)と **Cloud Translation API**(翻訳)を使用します。以下の手順でAPIキーを取得してください。

1. [Google Cloud Console](https://console.cloud.google.com/) にアクセスし、Googleアカウントでログイン
2. 新しいプロジェクトを作成(または既存のプロジェクトを選択)
3. 左メニューの「APIとサービス」→「ライブラリ」から、以下の2つを検索して有効化する
   - **Cloud Vision API**
   - **Cloud Translation API**
4. 「APIとサービス」→「認証情報」→「認証情報を作成」→「APIキー」を選択してキーを発行
5. 発行したキーを選択し、「APIキーを制限」で以下を設定することを推奨
   - **APIの制限**: 「キーを制限」を選び、`Cloud Vision API` と `Cloud Translation API` のみを許可
6. 発行されたAPIキーをコピーし、このツールの入力欄に貼り付けて「保存」

> **注意**: Cloud Vision API・Cloud Translation APIはいずれも従量課金制です。無料枠を超えると課金が発生するため、Google Cloud Consoleで料金・予算アラートを設定しておくことを推奨します。

## 注意事項

- 画面共有機能(`getDisplayMedia`)はHTTPS環境、または`localhost`でのみ動作します
- APIキーには前述の制限をかけ、第三者に漏れないよう管理してください
