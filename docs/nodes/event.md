# イベント (Event)

BP の実行トリガーとなるイベントノード群です。外部入力・ BPM ・キー入力などに対応します。

---

## ノード一覧

| 英語名              | 日本語名                | 説明                                   |
| ------------------- | ----------------------- | -------------------------------------- |
| On BP Enabled       | BP有効化時              | BPが有効になったとき実行               |
| On BP Disabled      | BP無効化時              | BPが無効になったとき実行               |
| On Fixed Update     | FixedUpdate時           | 物理演算フレームごとに実行             |
| On Late Update      | LateUpdate時            | 毎フレームの LateUpdate で実行         |
| On Update           | Update時                | 毎フレームの Update で実行             |
| On WebSocket Event  | WebSocketイベント受信時 | WebSocket メッセージを受信したとき実行 |
| On Key Press        | キー押下時              | 指定キーが押されたとき実行             |
| On Timer            | タイマー時              | 設定時間ごとに定期実行                 |
| On Tempo            | テンポ時                | BPM に同期したテンポで実行             |
| On Button Press     | ボタン押下時            | コントローラのボタンが押されたとき実行 |
| On Mouse Press      | マウス押下時            | マウスボタンが押されたとき実行         |
| On Variable Changed | 変数変更時              | 指定変数の値が変化したとき実行         |
