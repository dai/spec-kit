<div align="center">
    <img src="./media/logo_small.webp"/>
    <h1>🌱 Spec Kit</h1>
    <h3><em>高品質なソフトウェアをより速く構築しましょう。</em></h3>
</div>

<p align="center">
    <strong>Spec-Driven Development（仕様駆動開発）の力を借りて、組織が非差別化コードの記述ではなくプロダクトシナリオに集中できるようにする取り組みです。</strong>
</p>

[![Release](https://github.com/github/spec-kit/actions/workflows/release.yml/badge.svg)](https://github.com/github/spec-kit/actions/workflows/release.yml)

---

## 目次

- [🤔 Spec-Driven Developmentとは？](#-spec-driven-developmentとは)
- [⚡ はじめ方](#-はじめ方)
- [📚 コア哲学](#-コア哲学)
- [🌟 開発フェーズ](#-開発フェーズ)
- [🎯 実験的な目標](#-実験的な目標)
- [🔧 前提条件](#-前提条件)
- [📖 詳しく知る](#-詳しく知る)
- [詳細プロセス](#詳細プロセス)
- [トラブルシューティング](#トラブルシューティング)

## 🤔 Spec-Driven Developmentとは？

Spec-Driven Development（仕様駆動開発）は、従来のソフトウェア開発とは逆の発想です。長年にわたり、コードが主役でしたが、仕様書は「本番」の作業の足場として作られ、すぐに捨てられる存在でした。Spec-Driven Developmentは「何を作るか」「なぜ作るか」を重視し、仕様がプロダクトの中心となります。

## ⚡ はじめ方

### 1. Specifyのインストール

使用するコーディングエージェントに応じてプロジェクトを初期化します。

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <PROJECT_NAME>
```

### 2. 仕様書の作成

`/specify` コマンドで作りたいものを記述します。技術スタックではなく、**何を、なぜ作るか**に集中しましょう。

```bash
/specify 写真をアルバムごとに整理するアプリケーションを作りたい。アルバムは日付ごとにグループ化され、メインページでドラッグ＆ドロップで再編成できる。アルバムは決して消えない。[...]
```

### 3. 技術実装計画の作成

`/plan` コマンドで技術スタックやアーキテクチャの方針を記述します。

```bash
/plan アプリケーションはViteを使い、ライブラリは最小限に抑える。できるだけバニラHTML、CSS、JavaScriptを使用する。画像はアップロードせず、メタデータはローカルSQLiteデータベースに保存する。[...]
```

### 4. 分割と実装

`/tasks` で実行可能なタスクリストを作成し、エージェントに実装を依頼しましょう。

詳細な手順は[総合ガイド](./spec-driven.md)をご覧ください。

## 📚 コア哲学

Spec-Driven Developmentは以下の原則を重視します：

- **意図駆動開発**：仕様が「何を」定義し、「どうやって」は後から決定
- **豊かな仕様作成**：ガードレールや組織的原則に基づく仕様化
- **多段階の洗練**：プロンプト一発ではなく段階的な洗練
- **AIモデルの高度な活用**：仕様解釈にAIの力を活用

## 🌟 開発フェーズ

| フェーズ | フォーカス | 主な活動 |
|-------|-------|----------------|
| **0→1開発**（グリーンフィールド） | ゼロから構築 | <ul><li>高レベル要件からスタート</li><li>仕様書の作成</li><li>実装計画の立案</li><li>本番コードの構築</li></ul> |
| **創造的探求** | 並列実装 | <ul><li>多様なソリューションの探求</li><li>複数技術スタック・アーキテクチャのサポート</li><li>UXパターンの実験</li></ul> |
| **反復的改善**（ブラウンフィールド） | レガシーの近代化 | <ul><li>機能追加の反復</li><li>レガシーシステムの近代化</li><li>プロセスの適応</li></ul> |

## 🎯 実験的な目標

研究・実験のフォーカス：

### 技術独立性

- 多様な技術スタックでアプリケーションを作成
- Spec-Driven Developmentが技術・言語・フレームワークに依存しないプロセスであることを検証

### 企業制約

- ミッションクリティカルなアプリケーションの開発
- 組織的制約（クラウド、技術、エンジニアリング習慣）の取り込み
- 企業向けデザインシステムやコンプライアンス要件への対応

### ユーザー中心開発

- 多様なユーザー層・嗜好に合わせたアプリケーション作成
- コーディングアプローチの多様性（バイブコーディング～AIネイティブ開発）

### 創造的＆反復的プロセス

- 並列実装探求の概念検証
- 強力な反復的機能開発ワークフローの提供
- アップグレードや近代化タスクへのプロセス拡張

## 🔧 前提条件

- **Linux/macOS**（またはWindows上のWSL2）
- AIコーディングエージェント：[Claude Code](https://www.anthropic.com/claude-code)、[GitHub Copilot](https://code.visualstudio.com/)、[Gemini CLI](https://github.com/google-gemini/gemini-cli)
- パッケージ管理用 [uv](https://docs.astral.sh/uv/)
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

## 📖 詳しく知る

- **[Spec-Driven Development完全ガイド](./spec-driven.md)** - プロセスの詳細
- **[詳細な実装手順](#詳細プロセス)** - ステップバイステップのガイド

---

## 詳細プロセス

<details>
<summary>詳細なステップバイステップ手順を表示</summary>

Specify CLIを使ってプロジェクトをブートストラップできます。必要なアーティファクトが環境に導入されます。コマンド：

```bash
specify init <project_name>
```

カレントディレクトリで初期化：

```bash
specify init --here
```

![Specify CLIが新規プロジェクトをターミナルでブートストラップ](./media/specify_cli.gif)

使用するAIエージェントを選択するように促されます。直接指定も可能です：

```bash
specify init <project_name> --ai claude
specify init <project_name> --ai gemini
specify init <project_name> --ai copilot
# カレントディレクトリの場合：
specify init --here --ai claude
```

CLIはClaude CodeやGemini CLIのインストールを確認します。未インストール、あるいはテンプレートだけ欲しい場合は `--ignore-agent-tools` オプションを追加してください。

```bash
specify init <project_name> --ai claude --ignore-agent-tools
```

### **STEP 1:** プロジェクトのブートストラップ

プロジェクトフォルダへ移動し、AIエージェントを起動します。ここでは `claude` を例にします。

![Claude Code環境のブートストラップ](./media/bootstrap-claude-code.gif)

`/specify`, `/plan`, `/tasks` コマンドが使える状態になっていれば設定成功です。

まずはプロジェクトの足場を作成します。`/specify` コマンドで具体的な要件を入力しましょう。

>[!IMPORTANT]
>「何を」「なぜ」作りたいのかを明確に記述しましょう。**技術スタックにはこの段階で触れないでください。**

入力例：

```text
Taskifyというチーム生産性プラットフォームを開発したい。ユーザーはプロジェクト作成・メンバー追加・タスク割り当て・コメント・タスクをカンバンで移動可能。初期ではユーザーは事前定義、5人（1人プロダクトマネージャ・4人エンジニア）、3つのサンプルプロジェクト。カンバンは「To Do」「In Progress」「In Review」「Done」。ログイン不要。UI上でタスクカードの状態変更、コメント追加・編集・削除（自分のみ）、タスクの担当割り当て。色分けで自分のタスク判別。プロジェクト選択後、カンバン表示。ドラッグ＆ドロップでカード移動可能。他人のコメントは編集・削除不可。
```

このプロンプト入力後、Claude Codeがプランニングや仕様作成を開始します。ビルトインスクリプトでリポジトリ設定も行われます。

完了すると新しいブランチ（例：`001-create-taskify`）と、`specs/001-create-taskify` ディレクトリに仕様書が作成されます。

この時点でのプロジェクトフォルダ例：

```text
├── memory
│	 ├── constitution.md
│	 └── constitution_update_checklist.md
├── scripts
│	 ├── check-task-prerequisites.sh
│	 ├── common.sh
│	 ├── create-new-feature.sh
│	 ├── get-feature-paths.sh
│	 ├── setup-plan.sh
│	 └── update-claude-md.sh
├── specs
│	 └── 001-create-taskify
│	     └── spec.md
└── templates
    ├── CLAUDE-template.md
    ├── plan-template.md
    ├── spec-template.md
    └── tasks-template.md
```

### **STEP 2:** 機能仕様の明確化

ベース仕様作成後、抜け漏れ要件を明確化できます。例：

```text
各サンプルプロジェクトには5～15個のタスクをランダムに割り振り、すべての進行状態に最低1つずつタスクが存在するようにしてください。
```

Claude Codeに**レビュー＆受入チェックリスト**の検証も依頼できます。

```text
レビュー＆受入チェックリストを読み、仕様が満たしていればチェックを入れてください。満たしていない場合は空欄のままにしてください。
```

初回仕様は確定ではありません。Claude Codeとのやり取りで積極的に質問・明確化しましょう。

### **STEP 3:** プランの生成

ここで技術スタックや詳細要件を明示します。`/plan` コマンド例：

```text
.NET Aspireを使用し、データベースはPostgres。フロントエンドはBlazorサーバー、ドラッグ＆ドロップ対応、リアルタイム更新。REST APIでプロジェクト・タスク・通知を管理。
```

この段階でディレクトリは下記のようになります：

```text
.
├── CLAUDE.md
├── memory
│	 ├── constitution.md
│	 └── constitution_update_checklist.md
├── scripts
│	 ├── check-task-prerequisites.sh
│	 ├── common.sh
│	 ├── create-new-feature.sh
│	 ├── get-feature-paths.sh
│	 ├── setup-plan.sh
│	 └── update-claude-md.sh
├── specs
│	 └── 001-create-taskify
│	     ├── contracts
│	     │	 ├── api-spec.json
│	     │	 └── signalr-spec.md
│	     ├── data-model.md
│	     ├── plan.md
│	     ├── quickstart.md
│	     ├── research.md
│	     └── spec.md
└── templates
    ├── CLAUDE-template.md
    ├── plan-template.md
    ├── spec-template.md
    └── tasks-template.md
```

`research.md` に技術スタックの調査内容が反映されているか確認しましょう。必要ならClaude Codeに修正依頼できます。

技術スタックが急速に変化する場合は追加調査の依頼も推奨です：

```text
.NET Aspireのような急速に進化するライブラリについては、実装計画や詳細ファイル内で追加調査が必要な部分を特定し、対応するリサーチタスクを並列で展開してください。Taskifyに使用するバージョンなど、具体的な情報をresearch.mdに追記してください。
```

Claude Codeが的外れな調査をした場合は、下記のように修正を促しましょう：

```text
まず実装時に不明点・追加調査が必要なタスクをリストアップし、それぞれ並列にリサーチタスクを展開してください。一般的な.NET Aspire情報の調査ではなく、課題解決に直結する具体的な調査が必要です。
```

>[!NOTE]
>Claude Codeが余計なコンポーネントを追加することもあるので、理由や変更の根拠を確認しましょう。

### **STEP 4:** プランの検証

プラン完成後、Claude Codeに内容監査を依頼しましょう：

```text
実装計画と詳細ファイルを監査し、明らかに実施すべきタスクの抜け漏れがないか確認してください。各ステップに関連する詳細情報への参照も付けてください。
```

これで計画の精度が高まり、見落としを防げます。初回の洗練後は、Claude Codeに「過剰設計」箇所の確認も依頼しましょう。

>[!NOTE]
>実装前に過剰設計部分の有無も要確認です。

### STEP 5: 実装

準備ができたらClaude Codeに実装を指示します（例）：

```text
implement specs/002-create-taskify/plan.md
```

Claude Codeが自動で実装を進めます。

>[!IMPORTANT]
>Claude CodeはローカルCLIコマンド（dotnet等）を実行するため、事前にインストールしておいてください。

実装完了後はアプリ実行＆ビルドエラー対応を依頼しましょう。実行可能でもランタイムエラーが発生する場合は、追加で修正を依頼してください。

</details>

---

## トラブルシューティング

### LinuxでのGit Credential Manager

LinuxでGit認証に問題がある場合は以下でインストール可能です：

```bash
#!/bin/bash
set -e
echo "Git Credential Manager v2.6.1のダウンロード中..."
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.1/gcm-linux_amd64.2.6.1.deb
echo "Git Credential Managerのインストール中..."
sudo dpkg -i gcm-linux_amd64.2.6.1.deb
echo "Gitの認証ヘルパーをmanagerに設定中..."
git config --global credential.helper manager
echo "後処理中..."
rm gcm-linux_amd64.2.6.1.deb
```

## メンテナー

- Den Delimarsky ([@localden](https://github.com/localden))
- John Lam ([@jflam](https://github.com/jflam))

## サポート

サポートが必要な場合は[GitHub Issue](https://github.com/github/spec-kit/issues/new)を作成してください。バグ報告・機能要望・Spec-Driven Developmentの利用質問を歓迎します。

## 謝辞

本プロジェクトは[John Lam](https://github.com/jflam)の研究成果に大きく基づいています。

## ライセンス

本プロジェクトはMITライセンスで公開されています。詳細は[LICENSE](./LICENSE)ファイルをご参照ください。
