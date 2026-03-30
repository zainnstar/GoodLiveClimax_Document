# Float ノード

浮動小数点数（float型）の演算ノード群です。

---

## ノード一覧

### Add / Subtract / Multiply / Divide

基本四則演算です。

| ピン   | 方向 | 型    | 説明     |
| ------ | ---- | ----- | -------- |
| A      | 入力 | float | 左辺     |
| B      | 入力 | float | 右辺     |
| Result | 出力 | float | 演算結果 |

### Greater (float)

A > B なら `true` を出力します。

| ピン   | 方向 | 型    | 説明            |
| ------ | ---- | ----- | --------------- |
| A      | 入力 | float | 比較対象A       |
| B      | 入力 | float | 比較対象B       |
| Result | 出力 | bool  | A > B なら true |

### Less (float)

A < B なら `true` を出力します。

### Clamp (float)

値を最小・最大範囲内に収めます。

| ピン   | 方向 | 型    | 説明             |
| ------ | ---- | ----- | ---------------- |
| Value  | 入力 | float | クランプする値   |
| Min    | 入力 | float | 最小値           |
| Max    | 入力 | float | 最大値           |
| Result | 出力 | float | クランプされた値 |

### Lerp (float)

2つのfloat値を線形補間します。

| ピン   | 方向 | 型    | 説明            |
| ------ | ---- | ----- | --------------- |
| A      | 入力 | float | 開始値          |
| B      | 入力 | float | 終了値          |
| T      | 入力 | float | 補間係数 (0〜1) |
| Result | 出力 | float | 補間された値    |

### Abs / Ceil / Floor / Round

絶対値・切り上げ・切り捨て・四捨五入。

### Sin / Cos / Tan

三角関数ノード（ラジアン入力）。

### Float Literal

固定のfloat値を出力します。エディタ上で値を直接入力します。

### Float → Int / Float → String

float値を他の型に変換します。

!!! note
この章は作成中です。詳細は追って追記されます。
