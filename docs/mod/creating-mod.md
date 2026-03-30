# MOD作成手順

GoodLiveClimax用のMODを作成するには、**Unity**と**MOD SDK**が必要です。

---

## 必要なもの

| 必要物             | 備考                                     |
| ------------------ | ---------------------------------------- |
| Unity              | 推奨バージョンはUnity6.3 Lts             |
| MOD SDK            | [SDKダウンロードページ](sdk.md) から入手 |
| 作成したいアセット | 3Dモデル・テクスチャなど                 |

---

## セットアップ

### 1. 新規Unityプロジェクトを作成する

SDKを組み込むための専用Unityプロジェクトを用意します。

### 2. SDKをインポートする

ReleaseページよりダウンロードしたUnityプロジェクトを、Unityで開いてください。

```

---

## MODのビルド手順

### 1. MOD素材を用意する

シーンまたはPrefabとして、MODにしたいアセットをUnityに取り込みます。

### 2. MOD Exporterを開く

Unity Editor メニュー: **Tools → MOD Exporter**

### 3. 設定を入力する

| 設定項目     | 内容                                         |
| ------------ | -------------------------------------------- |
| 対象アセット | MODにするシーンまたはPrefab                  |
| カテゴリ     | `Worlds`（ステージ）または `Items`（小道具） |
| MOD名        | 表示される名前                               |
| 出力先       | `.cmxmod` の保存先                           |

### 4. Buildボタンを押す

`Build` を押すと `.cmxmod` ファイルが生成されます。

---

## 動作確認

生成した `.cmxmod` を以下のフォルダに配置して、GoodLiveClimaxで読み込めるか確認します。

| 種類     | 配置先                    |
| -------- | ------------------------- |
| ワールド | `StreamingAssets/Worlds/` |
| アイテム | `StreamingAssets/Items/`  |
| アバター | `StreamingAssets/Avatars/` |
| パーティクル | `StreamingAssets/Particles/` |
---

## 注意事項

!!! warning "権利について"
配布するMODに使用する素材（モデル・テクスチャ等）の権利を必ず確認してください。
 無断使用は著作権侵害になります。
```
