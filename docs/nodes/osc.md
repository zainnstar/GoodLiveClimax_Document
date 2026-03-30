# OSC ノード

OSCメッセージの送受信を行うノード群です。外部ツール（VRCOSCやDJソフトなど）との連携に使用します。

---

## OSCとは

OSC（Open Sound Control）は音楽・映像演出でよく使われるネットワーク通信プロトコルです。  
GoodLiveClimax は OSC を経由してトラッキングデータや操作コマンドを受信・送信できます。

---

## ノード一覧

### Send OSC

OSCメッセージを送信します。

| ピン    | 方向 | 型     | 説明                                  |
| ------- | ---- | ------ | ------------------------------------- |
| →       | 入力 | フロー | 実行                                  |
| Address | 入力 | string | OSCアドレス（例: `/glc/light/color`） |
| Values  | 入力 | list   | 送信する値のリスト                    |
| →       | 出力 | フロー | 送信後                                |

### Receive OSC (Event)

特定アドレスへのOSC受信イベント。詳細は [Event ノード](event.md) の `On OSC Receive` を参照。

### OSC Float / OSC Int / OSC String

OSC メッセージのペイロードから指定インデックスの値を取り出します。

| ピン   | 方向 | 型               | 説明                     |
| ------ | ---- | ---------------- | ------------------------ |
| Values | 入力 | list             | 受信したOSCペイロード    |
| Index  | 入力 | int              | 取り出す値のインデックス |
| Result | 出力 | float/int/string | 取り出した値             |

---

## 対応アドレス仕様

OSCアドレス仕様の詳細については、dev_guide の `osc-address-spec.md` を参照してください（開発者向け）。

!!! note
この章は作成中です。詳細は追って追記されます。
