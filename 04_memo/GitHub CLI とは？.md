#tool/git #type/memo 

以下が GitHub CLI の要点です。

---

## GitHub CLI（gh）とは

**GitHub CLI** は、GitHub をターミナルから操作するオープンソースのコマンドラインツールです。ブラウザを開かずに GitHub と連携でき、作業の切り替えを減らして効率を上げられます。

- **git** … ローカル／リモートの Git 全般を操作
- **gh** … GitHub 専用（Issue、PR、リポジトリ、Actions など）

---

## 主な機能

- **リポジトリ**: 表示・作成・クローン・フォーク
- **Issue**: 作成・一覧・クローズ・編集
- **Pull Request**: 作成・一覧・レビュー・マージ・diff 確認
- **ワークフロー**: GitHub Actions の実行・一覧・表示
- **リリース**: 作成・一覧・表示・削除
- **その他**: Gist、Codespaces、GitHub API の利用

---

## インストール

- **macOS**: `brew install gh`
- **Windows**: winget / Scoop / Chocolatey
- **Linux**: apt / yum / dnf / snap など

---

## 認証

```bash
gh auth login
```

対話形式で次のような選択をします。

- ホスト（GitHub.com または Enterprise）
- プロトコル（HTTPS 推奨）
- 認証方式（HTTPS/SSH、SSO、2FA 対応）

HTTPS で「Git の認証情報も保存する」を Yes にすると、`git push` などもその認証で使えます。

---

## よく使うコマンド例

| 操作 | コマンド例 |
|------|-------------|
| 認証状態確認 | `gh status` |
| リポジトリ表示 | `gh repo view OWNER/REPO` |
| ブラウザで開く | `gh repo view OWNER/REPO --web` |
| クローン | `gh repo clone OWNER/REPO` |
| リポジトリ作成 | `gh repo create` |
| Issue 一覧 | `gh issue list` または `gh issue list --assignee "@me"` |
| PR 一覧 | `gh pr list` または `gh pr list --author "@me"` |
| PR 作成 | `gh pr create` |
| レビュー依頼された PR | `gh search prs --review-requested=@me --state=open` |

各コマンドの詳細は `gh コマンド --help` で確認できます。`fzf` などと組み合わせると、インタラクティブに操作しやすくなります。

---

まとめると、**GitHub の操作をターミナルで完結させたい人**や**スクリプトで GitHub を自動化したい人**に向いたツールです。