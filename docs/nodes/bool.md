# Bool

Bool型（true / false）の論理演算・比較ノード群です。Int / Float / 文字列の比較系ノードもこのカテゴリに含まれます。

---

## ノード一覧

| 英語名                 | 日本語名           | 説明                                     |
| ---------------------- | ------------------ | ---------------------------------------- |
| AND                    | AND                | 両方 true のとき true を出力             |
| Get BP Bool            | BP Boolを取得      | BP変数（Bool型）の値を読み取る           |
| Set BP Bool            | BP Boolを設定      | BP変数（Bool型）に値を書き込む           |
| Bool                   | Bool               | 固定の bool 値を出力するリテラル         |
| Int Greater Or Equal   | Int が以上         | A ≥ B なら true                          |
| Int Less Or Equal      | Int が以下         | A ≤ B なら true                          |
| Int Greater            | Int が大きい       | A > B なら true                          |
| Int Less               | Int が小さい       | A < B なら true                          |
| Int Equal              | Int が等しい       | A == B なら true                         |
| Int Not Equal          | Int が等しくない   | A != B なら true                         |
| OR                     | OR                 | どちらか一方が true なら true を出力     |
| XOR                    | XOR                | 片方だけ true（排他的論理和）のとき true |
| NOT                    | 反転               | Bool 値を反転する                        |
| String Equal           | 文字列が等しい     | 2 つの文字列が等しければ true            |
| Float Greater Or Equal | float が以上       | A ≥ B なら true                          |
| Float Less Or Equal    | float が以下       | A ≤ B なら true                          |
| Float Greater          | float が大きい     | A > B なら true                          |
| Float Less             | float が小さい     | A < B なら true                          |
| Float Equal            | float が等しい     | A == B なら true                         |
| Float Not Equal        | float が等しくない | A != B なら true                         |
