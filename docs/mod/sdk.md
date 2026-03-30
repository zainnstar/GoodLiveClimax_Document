# SDK ダウンロード

GoodLiveClimax MOD作成用のSDKは、GitHubのReleasesページから入手できます。

---

## ダウンロード

<div class="grid cards" markdown>

- **MOD SDK**

  最新版のMOD SDKはGitHubのReleasesページからダウンロードしてください。

  [GitHubのReleasesページへ :octicons-arrow-right-24:](https://github.com/zainnstar/GoodLiveClimax_Document/releases/latest){ .md-button .md-button--primary }

</div>

---

## SDKに含まれるファイル

| ファイル                        | 役割                          |
| ------------------------------- | ----------------------------- |
| `ModMetaData.cs`                | MODのメタデータ定義           |
| `ModExportBuilder.cs`           | アセットバンドルビルド処理    |
| `ModExportEditor.cs`            | Unityエディタ上のUIウィンドウ |
| `ModExportAssetDropField.cs`    | アセットドロップフィールドUI  |
| `ModExportLocalization.cs`      | ローカライズテキスト          |
| `ModMetadataCache.cs`           | メタデータキャッシュ          |
| `ModExportPublicKeyProvider.cs` | 公開鍵プロバイダ（暗号化用）  |
| `ModCmxmodCrypto.cs`            | 暗号化処理                    |

---

## SDKに含まれないもの（意図的な除外）

以下はSDKには含まれておらず、開発者側のみが保有します。

- `AvatarModCrypto.dll` — 復元用DLL
- 開発者専用の復元パスワード
- 内部秘密鍵を含むファイル

これはMODの改ざんを防ぐための設計です。SDKで作れるのは「暗号化されたMODパッケージ」だけです。

---

## バージョン履歴

| バージョン | 内容               |
| ---------- | ------------------ |
| 準備中     | 初回リリース準備中 |

---

!!! note "Boothでも配布予定"
GoodLiveClimax本体はBoothでの販売を予定しています。  
 SDKはGitHubから無償で配布する予定です。
