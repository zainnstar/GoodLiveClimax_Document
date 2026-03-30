# 開発環境セットアップ

## 必要ツール

| ツール | バージョン | 用途 |
|--------|-----------|------|
| Unity | 推奨バージョンはプロジェクト `.unityversionproject` を参照 | メイン開発環境 |
| Visual Studio / Rider | - | C#スクリプト編集 |
| Python | 3.x | MkDocsドキュメントビルド |
| Git | - | バージョン管理 |

---

## Unityプロジェクトの起動

```
AvatarSystem/  ← Unityプロジェクトルート
```

Unity Hub からこのフォルダを開く。

### 初回起動時の注意

- パッケージ解決に時間がかかる場合がある
- `Assets/Plugins/` 以下の DLL は `netstandard` ビルドのものだけを配置すること  
  （multi-target NuGet の `net6.0` / `net7.0` を丸ごと置かない）

---

## ドキュメントのローカルプレビュー

```bash
cd GoodLiveClimax_Document/
pip install mkdocs-material
mkdocs serve
```

→ `http://127.0.0.1:8000` でリアルタイムプレビュー

---

## ビルド手順

### Unityビルド

1. Unity Editor メニュー: **File → Build Settings**
2. Platform: **PC, Mac & Linux Standalone / Windows x64**
3. **Build**

出力先はプロジェクトルート外の任意フォルダを推奨。

### ドキュメントビルド（手動）

```bash
mkdocs build
```

→ `site/` フォルダにHTMLが生成される。  
`.gitignore` で `site/` は除外済みのため、GitHubにはpushしない。

---

## スクリプト変更後の確認手順

C#スクリプトを変更した場合は必ず以下を実施:

1. Unity Editor で保存 → 自動コンパイル待ち
2. **Unity MCP: Refresh Unity** または Unity の `Assets → Refresh`
3. **Console ウィンドウ** にエラーがないことを確認

> IDE (Visual Studio / Rider) にエラーが出ていなくても、Unity Editor 側でエラーが出る場合がある。必ずConsoleを確認すること。

---

## OSCデバッグ

OSCの送受信確認には **Protokol** (無料) が便利。

```
受信ポート: 9000
送信ポート: 9001
```
