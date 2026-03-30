# Int ノード

整数（int型）の演算ノード群です。

---

## ノード一覧

### Add / Subtract / Multiply / Divide

基本四則演算です。

| ピン   | 方向 | 型  | 説明     |
| ------ | ---- | --- | -------- |
| A      | 入力 | int | 左辺     |
| B      | 入力 | int | 右辺     |
| Result | 出力 | int | 演算結果 |

### Modulo (余り)

A を B で割ったときの余りを返します。

| ピン   | 方向 | 型  | 説明   |
| ------ | ---- | --- | ------ |
| A      | 入力 | int | 被除数 |
| B      | 入力 | int | 除数   |
| Result | 出力 | int | 余り   |

### Greater (int)

A > B なら `true` を出力します。

| ピン   | 方向 | 型   | 説明            |
| ------ | ---- | ---- | --------------- |
| A      | 入力 | int  | 比較対象A       |
| B      | 入力 | int  | 比較対象B       |
| Result | 出力 | bool | A > B なら true |

### Less (int)

A < B なら `true` を出力します。

### Equal (int)

A == B なら `true` を出力します。

### Clamp (int)

値を最小・最大範囲内に収めます。

### Int → Float / Int → String

int値を他の型に変換します。

### Int Literal

固定のint値を出力します。エディタ上で値を直接入力します。

!!! note
この章は作成中です。詳細は追って追記されます。
