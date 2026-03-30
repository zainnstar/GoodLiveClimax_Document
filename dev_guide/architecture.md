# GoodLiveClimax システムアーキテクチャ

## システム全体構成

```
┌──────────────────────────────────────────────────────────┐
│                   GoodLiveClimax (Unity)                 │
│                                                          │
│  ┌────────────┐   ┌─────────────┐   ┌────────────────┐  │
│  │  Avatar    │   │  Rendering  │   │  Asset Manager │  │
│  │  System    │   │  Pipeline   │   │  (SceneData)   │  │
│  └────────────┘   └─────────────┘   └────────────────┘  │
│         ↑               ↑                   ↑            │
│  ┌──────────────────────────────────────────────────┐    │
│  │            Controller Layer (OSC/WebSocket)      │    │
│  └──────────────────────────────────────────────────┘    │
│                          ↑                               │
└──────────────────────────┼───────────────────────────────┘
                           │ OSC (UDP)
              ┌────────────┴───────────┐
              │       Chataigne        │
              │  (Show Control / TL)   │
              └────────────────────────┘

映像出力: Spout2 → OBS (配信)
トラッキング入力: Webcam → MediaPipe
```

---

## プロセス構成

GoodLiveClimaxは**シングルプロセス・シングルウィンドウ**で動作する。  
設定UIとアバター表示は同一プロセス内でシーン分離して実装している。

旧設計（2プロセス案）は廃案。現在はすべてUnity内で完結。

---

## 通信プロトコル

| 通信 | プロトコル | 用途 |
|------|-----------|------|
| Chataigne → Unity | OSC (UDP) | タイムライン連動・プリセット発火 |
| Unity → Chataigne | OSC (UDP) | フィードバック・状態通知 |
| 外部コントローラ | OSC (UDP) | リアルタイム制御 |

OSCポートデフォルト値:
- 受信: `9000`
- 送信: `9001`

ライブラリ: **uOSC**

---

## アセットシステム

すべての演出要素（カメラ・ライト・アバター・アイテム等）はIDで管理する**アセットシステム**として実装されている。

### アセットの特徴

- 各アセットは一意の **AssetID (GUID)** で識別される
- 表示名（ユーザーが変更可）とは独立しているため、リネームしても参照が切れない
- シーンデータは JSON で `Datas/` 以下に永続化される

### 共通コンポーネント

各アセットが継承する共通システム:

| コンポーネント | 役割 |
|--------------|------|
| Transform | 位置・回転・スケール管理 |
| MaterialController | マテリアルパラメータ制御 |
| ShadowSettings | Cast/Receive Shadow 設定 |

---

## レンダリングパイプライン

- **URP (Universal Render Pipeline)** ベース
- アウトライン等の追加シェーダーは **AddShaderTarget** コンポーネントで後付け
- Post Process は **AddPPCameraShader** でカメラ単位に管理
- 映像出力は **KlakSpout2 (Spout2)** でOBSに送信

---

## トラッキングパイプライン

```
Webcam → MediaPipe Unity Plugin
                ↓
        Hand / Face / Pose Landmarks
                ↓
        VMM (Virtual Model Manipulator)
                ↓
        VRM BlendShape / Humanoid Bone
```

対応フォーマット: **VRM 0.x**（VRM 1.xは非対応）  
顔: パーフェクトシンク対応（BlendShape 52種）
