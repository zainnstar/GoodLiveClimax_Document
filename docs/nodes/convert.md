# 変換 (Convert)

型変換（キャスト）を行うノード群です。異なる型の値を相互に変換します。

---

## ノード一覧

| 英語名           | 日本語名        | 説明                                  |
| ---------------- | --------------- | ------------------------------------- |
| Int to Float     | Int → Float     | int 値を float に変換する             |
| Float to Int     | Float → Int     | float 値を int に変換する（切り捨て） |
| Bool to Int      | Bool → Int      | true → 1、false → 0 に変換する        |
| Int to Bool      | Int → Bool      | 0 → false、それ以外 → true に変換する |
| Float to String  | Float → String  | float 値を文字列に変換する            |
| Int to String    | Int → String    | int 値を文字列に変換する              |
| String to Float  | String → Float  | 数値文字列を float に変換する         |
| String to Int    | String → Int    | 数値文字列を int に変換する           |
| Color to Vector3 | Color → Vector3 | RGB 成分を Vector3 として取り出す     |
| Vector3 to Color | Vector3 → Color | Vector3 の XYZ を RGB に変換する      |
