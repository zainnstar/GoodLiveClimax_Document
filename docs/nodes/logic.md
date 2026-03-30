# Logic ノード

比較・論理演算を行い、bool値を出力するノード群です。

---

## ノード一覧

### Equal

A と B が等しければ `true` を出力します。float / int / string / bool に対応。

| ピン   | 方向 | 型   | 説明             |
| ------ | ---- | ---- | ---------------- |
| A      | 入力 | 任意 | 比較対象A        |
| B      | 入力 | 任意 | 比較対象B        |
| Result | 出力 | bool | A == B なら true |

### Not Equal

A と B が等しくなければ `true` を出力します。

### Greater Than / Less Than

数値の大小比較です。

| ピン   | 方向 | 型        | 説明                           |
| ------ | ---- | --------- | ------------------------------ |
| A      | 入力 | float/int | 比較対象A                      |
| B      | 入力 | float/int | 比較対象B                      |
| Result | 出力 | bool      | A > B (または A < B) なら true |

### Greater Than Or Equal / Less Than Or Equal

以上・以下の比較です。

### And / Or / Not

Bool型のAND・OR・NOT演算です。

!!! info "Boolカテゴリとの統合"
And / Or / Not ノードは [Bool カテゴリ](bool.md) にも含まれています。同一ノードです。

!!! note
この章は作成中です。詳細は追って追記されます。
