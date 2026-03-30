# コーディング規約

GoodLiveClimax / AvatarSystem プロジェクトのC#コーディング規約。

---

## 基本方針

1. **可読性** > 差し替えやすさ > 再利用性 の優先順位で設計する
2. 密結合な設計を避ける
3. 修正は必要最小限に留める

---

## ファイル構成

- **1ファイルの目安: 300行以内**
- 機能単位でファイルを分割し、役割を明確にする
- エントリーポイント (`Main` 相当のクラス) を肥大化させない
- ロジックはサブクラス・モジュールへ分割する

---

## 命名規則

| 対象 | 規則 | 例 |
|------|------|-----|
| クラス | PascalCase | `CameraAssetController` |
| メソッド | PascalCase | `ApplyLightColor()` |
| フィールド (private) | _camelCase | `_assetId` |
| プロパティ | PascalCase | `AssetId` |
| 定数 | UPPER_SNAKE_CASE | `DEFAULT_OSC_PORT` |
| ファイル名 | 内容が一目でわかるPascalCase | `LightOperationManager.cs` |

ファイル名は可読性のために長くなっても構わない。

---

## コメント規約

`<summary>` のような XMLドキュメントコメントは使用しない。  
代わりに、**「なぜその処理が必要なのか」** を1行コメントで説明する。

```csharp
// Bad: 何をしているかしか書いていない
// リストをクリアする
_assetList.Clear();

// Good: なぜやるのかを説明する
// アセットIDのキャッシュが古くなるため、シーンロード前に必ずクリアする
_assetList.Clear();
```

---

## リソース管理

リソースのライフサイクルを明確にする:

- **生成タイミング**: `Awake()` または明示的な `Initialize()` で
- **解放タイミング**: `OnDestroy()` で確実に解放
- **所有関係**: 誰がリソースを持つか明記する

---

## アセットシステム設計

新しいアセット種別を追加する際のルール:

1. 共通コンポーネント（Transform / MaterialController / ShadowSettings）を継承する
2. 固有プロパティはそのアセットのスクリプトに閉じ込める
3. シーンデータ保存に対応するため、プロパティはシリアライズ可能にする

---

## Unityエラー確認

スクリプト変更後は必ず Unity Console を確認すること。  
詳細は [build-and-setup.md](build-and-setup.md) を参照。

---

## OSC / WebSocket DTO 設計

- nullable bool (`bool?`) は使用しない → `bool` + 明示的なデフォルト値を使用すること
- フラグのON/OFFはDTO内で完結させ、Controller側が外部状態に依存しないようにする

> 参考: Unity JsonUtility + nullable bool は silently フラグ未伝播のバグを起こしやすい（過去インシデント済み）
