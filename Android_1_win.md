## Andoroidアプリを作成するその１（Windows）
## 環境構築
## 目次
- [Android Studioインストール](#anchor1)
- [Android Studio日本語化](#anchor2)
- [プロジェクト作成](#anchor3)
- [仮想デバイス登録・起動](#anchor4)
- [SDK追加](#anchor5)

- [メモ](#anchor99)

<a id="anchor1"></a>
## Android Studioインストール
- [https://developer.android.com/studio/](https://developer.android.com/studio/)にアクセスする。
- 「Download Android Studio」をクリックする。
- ポップアップ画面の最下部にある同意のチェックボックスにチェックしダウンロードボタンをクリックする。
- ダウンロードしたインストーラーを実行してインストールする。
  - インストールメニューは全てデフォルト
- インストールが完了したら自動起動する。
  - コンフィグインポートをポップアップで聞いてくるが必要ない。
- セットアップ画面で「No Send」選択しNext、「Standard」を選択しNext、お好みのUIを選択してNextをクリックする。
- ライセンス同意画面で各ライセンスをクリック後、右下の「Accept」をクリックする。
  - 左側のツリーのトップ階層をクリックして選択する。
- 全てのライセンスで「Accept」をクリックすると「Finish」が活性化するためクリックしてインストールを完了する。

<a id="anchor2"></a>
## Android Studio日本語化
- Android Studioを起動する。
- 画面左下の歯車 > aboutをクリックし、バージョンを確認する。

　　![image](https://user-images.githubusercontent.com/87625373/208794823-21b746d8-899b-451e-a465-849a38111bde.png)
　　![image](https://user-images.githubusercontent.com/87625373/208795180-9e6c35bb-6bd2-40ec-8a89-fd5353562655.png)

- [https://plugins.jetbrains.com/plugin/13964-japanese-language-pack------/versions](https://plugins.jetbrains.com/plugin/13964-japanese-language-pack------/versions)にアクセスする。
- バージョンが一致するプラグインをダウンロードする（メジャーバージョンのみ一致すればよい）。

　　![image](https://user-images.githubusercontent.com/87625373/208795818-2c21a8c4-6e28-4b61-92e8-241bc92142e1.png)

- ダウンロードしたzipファイルを解凍し、「C:\Program Files\Android\Android Studio\plugins」にフォルダごと配置する。
- Android Studio の Plugins > 右上の歯車 > Install Plugin from Disk を選択する。

　　![image](https://user-images.githubusercontent.com/87625373/208794100-c1d7e6e5-942e-4483-bfb1-2511743273b3.png)

- プラグイン配置したフォルダ内にある「ja.xxx.jar」を選択し、OKをクリックする。

　　![image](https://user-images.githubusercontent.com/87625373/208796680-2f47eb23-489e-4836-b001-110467e76747.png)

- 「Restart IDE」と表示されるので、Android Studio を再起動する。
- 再起動が完了すると日本語になる。

<a id="anchor3"></a>
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

<a id="anchor4"></a>
## 仮想デバイス登録・起動
Android Studio内で起動する仮想デバイス（仮想スマホ）を登録・起動する。

但し、仮想デバイスは動作が重い、画面が小さいなどのデメリットがあるため、検証する際は実際にスマホやタブレットをパソコンに直結して確認した方が良い。実機との接続については[こちら](https://pouhon.net/android-connection/4619/)を参照してください。

- デフォルトで登録済みの仮想デバイスが右上に表示される。

    ![image](https://user-images.githubusercontent.com/87625373/208850987-2613329f-e333-4c1b-8d5b-46ca8f8caf9c.png)

- 新規仮想デバイスを追加する場合は「Create device」から登録する。（手順は[こちら](https://pouhon.net/android-avd/4698/)を参照）
- 対象デバイスの「▶」をクリックするとEmulatorが起動し、仮想デバイスが表示される。
  - 初回起動時は時間がかかるためしばらく待つ 。

    ![image](https://user-images.githubusercontent.com/87625373/208850058-73d30a5c-e716-4d03-8562-3dca1534ee0d.png)

- 仮想デバイス操作可能となったら、システムやアプリの言語を日本語化する。
  - エミュレータのシステム要件と操作方法は[こちら](https://developer.android.com/studio/run/emulator?hl=ja#requirements)
  - エミュレータの日本語化は[こちら](https://pouhon.net/android-avd/4698/)
- エミュレータ操作時に「system ui isn't responding」と表示され応答しない場合はしばらく操作せずに待つ。
  - パソコンの性能による動作遅延と思われるため、メモリは16GB以上必要（8GBでは動作が重い）。
- [Android Studioおすすめ設定](https://pouhon.net/android-settings/4766/)をお好みで実施する。

<a id="anchor5"></a>
## SDK追加
SDKの追加が必要な場合は以下のメニューからダウンロード・インストールする。
- ファイル > 設定 > システム設定 > Android SDKに遷移する。
- 右下のShow Package Details にチェックを入れて詳細を表示する。
- 上部のタブでPlatform/Toolsなど遷移し、必要なパッケージにチェックを入れOKをクリックする。
- 確認ダイアログでOKをクリックするとダウンロード・インストールが始まる。
- 完了画面で完了をクリックし終了する。

![image](https://user-images.githubusercontent.com/87625373/209627683-74e4e79c-68f8-437f-8064-f4d886ee3314.png)

![image](https://user-images.githubusercontent.com/87625373/209628753-61408929-0de0-423d-b8f8-401dabac9e60.png)







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