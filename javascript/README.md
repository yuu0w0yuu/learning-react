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

## propsとstate
- Props
  - 親コンポーネント - 子コンポーネント間の属性の受け渡しに利用するオブジェクト
  - 親側
    ```
    <ColorMessage color="blue">元気です</ColorMessage>
    ```
  - 小側
    ```
    export const ColorMessage = (props) => {
      const { color, children } = props; //propsの分割代入
      const style = {
        color, //オブジェクト省略記法
        fontSize: "18px",
      };

      return <p stype={style}>{children}</p>;
    };
    ```

- State
  - コンポーネント内に閉じたコンポーネントの状態を持つデータ
    - 例：ドロップダウンの開いている状態、ログインユーザ名などの外部データ
  - 仮想DOMとの差分をとり、実際のDOMを更新し、コンポーネントを再描画するための基本的な方法
  - `useState()`関数の戻り値（Stateの実際の値と、Stateを更新するための関数）を配列の分割代入で受け取る
    ```
    const [var, setVar] = useState(0);
    ```
  - 例：以下の関数を使うことで、`var`をインクメントできる
    ```
    const setNumber = () => {
      setVar( var + 1);
    }
    ```
  - State更新関数は、特定の関数の中で複数定義されている場合、まとめて一括で評価される

  - ボタンのOn/Offで顔文字の表示を切り替えるコード
    ```
    export const App = () => {
      const [isShowFace, setIsShowFace] = useState(true);
      const onClickToggle = () => {
        setIsShowFace(!isShowFace);
      };

      return (
        <>
          <button onClick={onClickToggle}>on/off</button>
          {isShowFace && <p>(*´ω｀)</p>}
        </>
      );
    }
    ```