---
name: github
description: "Interact with GitHub using the `gh` CLI. Use `gh issue`, `gh pr`, `gh run`, and `gh api` for issues, PRs, CI runs, and advanced queries. GitHub CLI 集成，支持 issue、PR、CI、API 查询。GitHub CLI連携：issue、PR、CI、APIクエリ対応。"
---

# GitHub Skill

Use the `gh` CLI to interact with GitHub. Always specify `--repo owner/repo` when not in a git directory, or use URLs directly.

## Pull Requests

Check CI status on a PR:
```bash
gh pr checks 55 --repo owner/repo
```

List recent workflow runs:
```bash
gh run list --repo owner/repo --limit 10
```

View a run and see which steps failed:
```bash
gh run view <run-id> --repo owner/repo
```

View logs for failed steps only:
```bash
gh run view <run-id> --repo owner/repo --log-failed
```

## Issues

List open issues:
```bash
gh issue list --repo owner/repo --state open
```

Create a new issue:
```bash
gh issue create --repo owner/repo --title "Bug: ..." --body "Details..."
```

View an issue:
```bash
gh issue view 123 --repo owner/repo
```

Add labels:
```bash
gh issue edit 123 --repo owner/repo --add-label "bug,priority:high"
```

## API for Advanced Queries

The `gh api` command is useful for accessing data not available through other subcommands.

Get PR with specific fields:
```bash
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'
```

List releases:
```bash
gh api repos/owner/repo/releases --jq '.[] | "\(.tag_name): \(.name)"'
```

## JSON Output

Most commands support `--json` for structured output. You can use `--jq` to filter:

```bash
gh issue list --repo owner/repo --json number,title --jq '.[] | "\(.number): \(.title)"'
```

---

# GitHub Skill（中文）

使用 `gh` CLI 与 GitHub 交互。不在 git 目录时，始终用 `--repo owner/repo` 指定仓库。

## PR 管理

查看 PR 的 CI 状态：
```bash
gh pr checks 55 --repo owner/repo
```

查看最近的 workflow 运行：
```bash
gh run list --repo owner/repo --limit 10
```

查看失败的步骤日志：
```bash
gh run view <run-id> --repo owner/repo --log-failed
```

## Issue 管理

列出 open issues：
```bash
gh issue list --repo owner/repo --state open
```

创建 issue：
```bash
gh issue create --repo owner/repo --title "Bug: ..." --body "详情..."
```

添加标签：
```bash
gh issue edit 123 --repo owner/repo --add-label "bug,priority:high"
```

## API 高级查询

```bash
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'
```

## JSON 输出

```bash
gh issue list --repo owner/repo --json number,title --jq '.[] | "\(.number): \(.title)"'
```

---

# GitHubスキル（日本語）

`gh` CLI を使って GitHub と連携します。git ディレクトリ以外では `--repo owner/repo` でリポジトリを指定してください。

## PR 管理

PR の CI ステータスを確認：
```bash
gh pr checks 55 --repo owner/repo
```

最近のワークフロー実行を表示：
```bash
gh run list --repo owner/repo --limit 10
```

失敗したステップのログを表示：
```bash
gh run view <run-id> --repo owner/repo --log-failed
```

## Issue 管理

オープン issue 一覧：
```bash
gh issue list --repo owner/repo --state open
```

issue 作成：
```bash
gh issue create --repo owner/repo --title "バグ: ..." --body "詳細..."
```

ラベル追加：
```bash
gh issue edit 123 --repo owner/repo --add-label "bug,priority:high"
```

## API 高度なクエリ

```bash
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'
```

## JSON 出力

```bash
gh issue list --repo owner/repo --json number,title --jq '.[] | "\(.number): \(.title)"'
```
