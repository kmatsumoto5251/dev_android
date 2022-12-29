## Andoroidアプリを作成するその1（hellow world）
## 目次
- [プロジェクト作成](#anchor1)
- [仮想デバイス登録・起動](#anchor4)

- [メモ](#anchor99)

<a id="anchor1"></a>
## プロジェクト作成
- プロジェクト > New Projectをクリックする。
- 画面レイアウトのテンプレートを任意で選択し次へをクリックする。
- アプリ名、パッケージ名など必要な項目を入力して完了をクリックする。
  - Name : 作りたいアプリの名前を入力する。
  - Package name : 自分が持っているドメインをひっくり返したものに、アプリケーション名をドットで繋げたものを入れる。ストアに表示される。
  - Project location : プロジェクトの保存場所を指定する。
  - Language : 使いたい言語を選ぶ。
  - Minimum SDK : 必要なAPIレベル。どのくらいのデバイスで動かせるのか、下にパーセントが表示されるので、それを見ながら選ぶ良い。
  - Use legacy android.support libraries : チェック不要。従来のサポートライブラリを使用するチェックを入れる。
- プロジェクトが作成されるとネットワーク環境によってはサーバ証明書の警告が表示されるため、内容を確認し「承認」をクリックする。
  - 複数回表示される可能性あり。
- インターネット接続にプロキシサーバを経由する場合はプロキシ設定を行う。
  - プロキシ設定を行わないとhttp403エラーなどが発生する可能性あり。
- ファイル > 設定 > システム設定 > HTTPプロキシ に遷移し、IPアドレスやポート番号を入力後、OKをクリックする。

    ![image](https://user-images.githubusercontent.com/87625373/208830056-f54e6b07-59c4-4c8f-8a44-1fc9a1644871.png)

- プロキシサーバの情報はコマンドプロンプトやPowerShellから以下のコマンドで確認が可能。
```
netsh winhttp show proxy
```
- プロキシサーバ設定後、下記のようなネットワーク関連のエラーが発生する場合はLAN内のSSLデコード除外などが必要となるためネットワーク管理者に確認する。

    ![image](https://user-images.githubusercontent.com/87625373/208832806-330b3082-b8b2-4256-9db7-dfaf2e8a880f.png)

<a id="anchor99"></a>
## メモ
- [Android Developers](https://developer.android.com/?hl=ja)
- [Kotolinで始めるAndroidアプリ入門](https://qiita.com/k-ysd/items/4efdecdfd60afe333a3a)
- [新規プロジェクトを作成する方法](https://original-game.com/develop-android-app-2/)
- [エミュレータの作成とコード実行](https://pouhon.net/android-avd/4698/)
- [エミュレータのシステム要件と操作方法](https://developer.android.com/studio/run/emulator?hl=ja#requirements)
- [HUAWEI製デバイスで実機テストするための準備](https://pouhon.net/android-connection/4619/)
- [KotlinのWeb実行環境](https://developer.android.com/training/kotlinplayground?hl=ja)
- [Androidアプリの画面作っていくには](https://qiita.com/cawmate_hitomi/items/35ae7c218090ae8f60b1)
- [Android Stdioプロジェクトのディレクトリ構成](http://gmonsoon.blog96.fc2.com/blog-entry-107.html)