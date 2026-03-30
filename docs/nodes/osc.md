# OSC

OSCメッセージの送受信を行うノード群です。専用 Controller（GoodLiveClimaxController）とのデータ連携のほか、外部ソフトウェアとの OSC 通信にも対応します。

---

## ノード一覧

| 英語名              | 日本語名         | 説明                                      |
| ------------------- | ---------------- | ----------------------------------------- |
| Receive OSC Float   | OSC Float受信    | 指定アドレスで float 値を受信したとき実行 |
| Receive OSC Trigger | OSC トリガー受信 | 指定アドレスでトリガーを受信したとき実行  |
| Receive OSC String  | OSC 文字列受信   | 指定アドレスで文字列を受信したとき実行    |
| Send OSC            | OSC送信          | 指定アドレスへ OSC メッセージを送信       |
