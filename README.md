# 開発環境構築
## インストール
```
mise install
npm install -g typescript
```

## セットアップ

### yarnコマンド
- `yarn create`コマンドは、`create-<starter-kit-package>`のグローバルインストール（あれば最新アップデート）と、`create-<starter-kit-package>`の実行を同時に行うコマンドである
    ```
    例
    yarn create react-app my-app
    ```
- `yarn install`コマンドは、実行ディレクトリにある`package.json`ファイルに記述されているパッケージを`node_modules`ディレクトリにインストールする（結果は`package-lock.json`に記録される）
- `package.json`ファイルが存在しない場合は、`yarn init`コマンドで作成する（依存関係記録のためにあった方がいい）
    ```
    yarn install
    ```
- `install`コマンドオプションの使い分け
    |コマンド|用途|
    |---|---|
    |`yarn install <package>`|`package.json`に対して、本番環境でも使用するローカルインストールパッケージを追加したい時|
    |`yarn install -D <package>`|`package.json`に対して、開発環境でしか使用しないローカルインストールパッケージを追加したい時|
    |`yarn install`|`package.json`を元に`node_modules`を作成・更新したい時|
    |`yarn install -g <package>`|対象パッケージをグローバルインストールしたい（どのディレクトリでも使用できる状態にしたい）時|
    |`yarn install --production`|`npm install -D <package>`で`package.json`に追加したパッケージを除外して`node_module`にパッケージをインストールしたい時|


# 構成
- `src`ディレクトリ
    - コンパイル前のソースを格納
    - React開発の場合、ページコンポーネントは`components`ディレクトリを作成して格納するのが一般的



# 開発Tips
## 流れ
- まずHTMLだけでデザインする
- ボタンに関数を設定する(最初はalertで発火だけ確認してから処理を実装する)


## 実装
- ボタンに対するイベントを呼び出す方法
```
document.getElementById("HTMLタグに指定したid").addEventListener("リッスンするイベント（clickなど）", 受信した時に実行するFunction名);
```


## デバッグ
 - console.log(変数)で出力