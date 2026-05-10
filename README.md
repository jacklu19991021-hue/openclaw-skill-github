# OpenClaw Skill: GitHub CLI

[English](#english) | [中文](#中文) | [日本語](#日本語)

---

## English

An OpenClaw skill for interacting with GitHub via the `gh` CLI.

### Features

- **Pull Requests**: Check CI status, list workflow runs, view failed step logs
- **Issues**: List, create, view, and label issues
- **API Queries**: Access GitHub API data with `gh api`
- **JSON Output**: Structured output with `--json` and `--jq` filtering

### Installation

```bash
clawhub install github
```

### Usage

```bash
# Check PR CI status
gh pr checks 55 --repo owner/repo

# List open issues
gh issue list --repo owner/repo --state open

# Create an issue
gh issue create --repo owner/repo --title "Bug: ..." --body "Details..."

# API query
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'
```

### Requirements

- [`gh` CLI](https://cli.github.com/) installed and authenticated
- OpenClaw agent with `exec` tool access

---

## 中文

OpenClaw 的 GitHub CLI 集成技能，通过 `gh` 命令与 GitHub 交互。

### 功能

- **PR 管理**：查看 CI 状态、workflow 运行记录、失败日志
- **Issue 管理**：列出、创建、查看、添加标签
- **API 查询**：通过 `gh api` 访问 GitHub API 数据
- **JSON 输出**：结构化输出，支持 `--jq` 过滤

### 安装

```bash
clawhub install github
```

### 使用

```bash
# 查看 PR CI 状态
gh pr checks 55 --repo owner/repo

# 列出 open issues
gh issue list --repo owner/repo --state open

# 创建 issue
gh issue create --repo owner/repo --title "Bug: ..." --body "详情..."

# API 查询
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'
```

### 依赖

- 安装并认证 [`gh` CLI](https://cli.github.com/)
- OpenClaw agent 需要 `exec` 工具权限

---

## 日本語

`gh` CLI を使って GitHub と連携する OpenClaw スキル。

### 機能

- **PR 管理**：CI ステータス確認、ワークフロー実行一覧、失敗ログ表示
- **Issue 管理**：一覧、作成、表示、ラベル追加
- **API クエリ**：`gh api` で GitHub API データにアクセス
- **JSON 出力**：構造化出力、`--jq` フィルタ対応

### インストール

```bash
clawhub install github
```

### 使い方

```bash
# PR の CI ステータス確認
gh pr checks 55 --repo owner/repo

# オープン issue 一覧
gh issue list --repo owner/repo --state open

# issue 作成
gh issue create --repo owner/repo --title "バグ: ..." --body "詳細..."

# API クエリ
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'
```

### 必要条件

- [`gh` CLI](https://cli.github.com/) のインストールと認証
- OpenClaw agent の `exec` ツール権限

---

## License

MIT
