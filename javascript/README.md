# 基礎概念
## モダンJavaScriptとは
- 仮想DOMを利用したライブラリ・フレームワーク（React）
- npm/yarnなどのパッケージマネージャーを利用
- ECMAScript 2015以降の記法を利用（アロー関数など）
- モジュールバンドラーを利用
  - 本番ビルド用に依存関係も判定して複数のjsファイルを1つにまとめるもの
- トランスパイラを利用
  - 古いブラウザ用に新しいコードを変換するもの

# 記法メモ
## アロー関数
```
const 関数名 = (引数) => {
    処理
}
```
## オブジェクト返却
```
const 関数名 = (引数1,引数2) => ({
    type1: 引数1,
    type2: 引数2,
})
```

