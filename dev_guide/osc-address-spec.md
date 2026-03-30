# OSC通信仕様（開発者向け）

GoodLiveClimaxで使用するOSCアドレス一覧。

ライブラリ: **uOSC**

---

## ポート設定

| 方向 | ポート |
|------|--------|
| 受信 (Chataigne → Unity) | 9000 |
| 送信 (Unity → Chataigne) | 9001 |

---

## アドレス体系

```
/glc/{カテゴリ}/{アセットID}/{パラメータ}
```

---

## カメラ

| アドレス | 型 | 説明 |
|---------|-----|------|
| `/glc/camera/{id}/active` | int (0/1) | カメラのON/OFF |
| `/glc/camera/{id}/spout/enable` | int (0/1) | Spout2送信のON/OFF |

---

## ライト

| アドレス | 型 | 説明 |
|---------|-----|------|
| `/glc/light/{id}/color` | float,float,float | RGB (0.0〜1.0) |
| `/glc/light/{id}/intensity` | float | 光量 (0.0〜最大値) |
| `/glc/light/{id}/enable` | int (0/1) | ON/OFF |

### ライトグループ

| アドレス | 型 | 説明 |
|---------|-----|------|
| `/glc/lightgroup/{groupId}/color` | float,float,float | グループ全体の色 |
| `/glc/lightgroup/{groupId}/intensity` | float | グループ全体の光量 |
| `/glc/lightgroup/{groupId}/enable` | int (0/1) | グループ全体のON/OFF |

---

## トラッキング

| アドレス | 型 | 説明 |
|---------|-----|------|
| `/glc/tracking/face/enable` | int (0/1) | 顔トラッキングON/OFF |
| `/glc/tracking/hand/enable` | int (0/1) | 手トラッキングON/OFF |
| `/glc/tracking/body/enable` | int (0/1) | 体トラッキングON/OFF |

---

## プリセット

| アドレス | 型 | 説明 |
|---------|-----|------|
| `/glc/preset/{presetId}/trigger` | int (1) | プリセット発火 |

---

!!! note
    このドキュメントは実装に追従して更新すること。  
    追加アドレスはここに記載してから実装する。
