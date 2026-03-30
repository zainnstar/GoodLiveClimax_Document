# Bool ノード

Bool型の値（`true` / `false`）を扱うノード群です。条件分岐や状態フラグ操作に使用します。

---

## ノード一覧

### And

| ピン   | 方向 | 型   | 説明     |
| ------ | ---- | ---- | -------- |
| A      | 入力 | bool | 入力値A  |
| B      | 入力 | bool | 入力値B  |
| Result | 出力 | bool | A かつ B |

### Or

| ピン   | 方向 | 型   | 説明       |
| ------ | ---- | ---- | ---------- |
| A      | 入力 | bool | 入力値A    |
| B      | 入力 | bool | 入力値B    |
| Result | 出力 | bool | A または B |

### Not

| ピン   | 方向 | 型   | 説明   |
| ------ | ---- | ---- | ------ |
| Value  | 入力 | bool | 入力値 |
| Result | 出力 | bool | 反転値 |

### Bool → Int / Float / String

bool値を他の型に変換するノードです。

| ピン   | 方向 | 型               | 説明       |
| ------ | ---- | ---------------- | ---------- |
| Value  | 入力 | bool             | 入力値     |
| Result | 出力 | int/float/string | 変換後の値 |

!!! tip
`true` → `1`（int/float）または `"True"`（string）に変換されます。
