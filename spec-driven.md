# 仕様駆動開発 (Specification-Driven Development, SDD)

## 権力構造の逆転

何十年もの間、コードが主役でした。仕様書はコードに従属するものであり、開発の「本番作業」が始まると捨てられる足場のようなものでした。私たちはPRD（プロダクト要件文書）を作成して開発を導き、設計文書を作成して実装を支援し、アーキテクチャを視覚化するために図を描きました。しかし、これらは常にコード自体に従属していました。コードが真実であり、それ以外はせいぜい善意の産物でした。コードが唯一の真実の源であり、コードが進化するにつれて仕様書はほとんど追随しませんでした。コードと実装が一体であるため、コードから離れて並行して実装を行うのは容易ではありません。

仕様駆動開発（SDD）は、この権力構造を逆転させます。仕様書はコードに従属するのではなく、コードが仕様書に従属します。PRD（プロダクト要件文書-仕様書）は実装のガイドではなく、実装を生成する源泉です。技術計画はコーディングを支援する文書ではなく、コードを生成するための正確な定義です。これはソフトウェア開発の方法を改善するだけでなく、開発を駆動するものを根本的に再考するものです。

仕様と実装の間のギャップは、ソフトウェア開発の黎明期から悩みの種でした。私たちはこれを埋めるために、より良い文書化、より詳細な要件、より厳格なプロセスを試みてきました。しかし、これらのアプローチはギャップを避けられないものとして受け入れており、ギャップを狭めることはできても完全に排除することはできませんでした。SDDは、仕様書や仕様から生まれる具体的な実装計画を実行可能にすることで、このギャップを排除します。仕様から実装計画がコードを生成する場合、ギャップは存在せず、変換のみが存在します。

この変革は、AIが複雑な仕様を理解し、実装計画を作成できるようになったことで可能になりました。しかし、構造のないAI生成は混乱を引き起こします。SDDは、仕様書とその後の実装計画を通じて、正確で完全かつ曖昧さのない構造を提供します。仕様書は主要な成果物となり、コードは特定の言語やフレームワークでの表現（実装計画からの実装）となります。

この新しい世界では、ソフトウェアの保守は仕様書の進化を意味します。開発チームの意図は、自然言語（「意図駆動開発」）、設計資産、コア原則、その他のガイドラインで表現されます。開発の共通言語はより高いレベルに移行し、コードは最後の一里を担うものとなります。

デバッグは、誤ったコードを生成する仕様書とその実装計画を修正することを意味します。リファクタリングは、明確さのための再構築を意味します。開発ワークフロー全体が、仕様書を真実の中心的な源泉とし、実装計画とコードを継続的に再生成される成果物として再編成されます。新機能を追加したり、新しい並行実装を作成したりすることは、仕様書を再訪し、新しい実装計画を作成することを意味します。このプロセスは、0 -> 1, (1', ..), 2, 3, N という形で進行します。

開発チームは、創造性、実験、批判的思考に集中します。

## 実践におけるSDDワークフロー

ワークフローは、しばしば曖昧で不完全なアイデアから始まります。AIとの反復的な対話を通じて、このアイデアは包括的なPRDに進化します。AIは明確化の質問を行い、エッジケースを特定し、正確な受け入れ基準を定義するのを支援します。従来の開発では数日かかる会議や文書作成が、集中した仕様作業で数時間で完了します。これにより、従来のSDLC（ソフトウェア開発ライフサイクル）が変革され、要件と設計が離散的なフェーズではなく、継続的な活動となります。これは、チームプロセスをサポートするものであり、チームレビューされた仕様が表現され、ブランチで作成され、マージされます。

プロダクトマネージャーが受け入れ基準を更新すると、実装計画は影響を受けた技術的決定を自動的にフラグ付けします。アーキテクトがより良いパターンを発見すると、PRDは新しい可能性を反映するように更新されます。

仕様プロセス全体を通じて、リサーチエージェントが重要なコンテキストを収集します。ライブラリの互換性、パフォーマンスベンチマーク、セキュリティの影響を調査します。組織の制約が自動的に発見され、適用されます。たとえば、会社のデータベース標準、認証要件、デプロイメントポリシーがすべての仕様にシームレスに統合されます。

PRDから、AIは要件を技術的な決定にマッピングする実装計画を生成します。すべての技術選択には文書化された根拠があります。すべてのアーキテクチャ決定は特定の要件に遡ります。このプロセス全体を通じて、一貫性の検証が品質を継続的に向上させます。AIは、曖昧さ、矛盾、ギャップについて仕様を分析します。これは一度限りのゲートではなく、継続的な改善プロセスです。

仕様とその実装計画が十分に安定すると、コード生成が開始されますが、「完成」している必要はありません。初期の生成は探索的である場合があります。仕様が実際に意味をなすかどうかをテストします。ドメインの概念はデータモデルになります。ユーザーストーリーはAPIエンドポイントになります。受け入れシナリオはテストになります。これにより、仕様を通じて開発とテストが統合されます。テストシナリオはコードの後に書かれるのではなく、実装とテストの両方を生成する仕様の一部です。

フィードバックループは初期開発を超えて拡張されます。運用メトリクスやインシデントは、ホットフィックスをトリガーするだけでなく、次回の再生成のために仕様を更新します。パフォーマンスのボトルネックは新しい非機能要件になります。セキュリティの脆弱性は、すべての将来の生成に影響を与える制約になります。この仕様、実装、運用現実の間の反復的なダンスが、真の理解が生まれる場所であり、従来のSDLCが継続的な進化に変わる場所です。

## なぜ今SDDが重要なのか

3つのトレンドがSDDを可能にし、必要不可欠なものにしています：

1つ目、AIの能力が自然言語仕様から信頼性の高い動作コードを生成できる閾値に達しました。これは開発者を置き換えるものではなく、仕様から実装への機械的な変換を自動化することで彼らの効果を増幅するものです。探索と創造性を増幅し、「やり直し」を容易にし、追加や削除、批判的思考をサポートします。

2つ目、ソフトウェアの複雑さが指数関数的に増加し続けています。現代のシステムは、数十のサービス、フレームワーク、依存関係を統合しています。手動プロセスを通じてこれらすべての部分を元の意図と一致させ続けることはますます困難になっています。SDDは、仕様駆動の生成を通じて体系的な整合性を提供します。フレームワークは、人間中心ではなくAI中心のサポートを提供するよう進化するか、再利用可能なコンポーネントを中心に設計される可能性があります。

3つ目、変化のペースが加速しています。要件はこれまで以上に急速に変化します。ピボットはもはや例外ではなく、期待されるものです。現代のプロダクト開発は、ユーザーフィードバック、市場状況、競争圧力に基づいて迅速な反復を要求します。従来の開発では、これらの変更を混乱として扱います。各ピボットは、文書化、設計、コードを手動で伝播する必要があります。その結果、速度を制限する慎重な更新か、技術的負債を蓄積する迅速で無謀な変更のいずれかになります。

SDDは、「もしアプリケーションを再実装または変更してビジネスニーズを促進し、Tシャツをより多く販売する必要がある場合、どのように実装し、実験するか？」といったシミュレーション実験をサポートできます。

SDDは、要件の変更を障害ではなく通常のワークフローに変えます。仕様が実装を駆動する場合、ピボットは手動の書き換えではなく体系的な再生成になります。PRDのコア要件を変更すると、影響を受けた実装計画が自動的に更新されます。ユーザーストーリーを変更すると、対応するAPIエンドポイントが再生成されます。これは初期開発だけでなく、避けられない変更を通じてエンジニアリングの速度を維持することに関するものです。

## コア原則

**共通言語としての仕様書**: 仕様書が主要な成果物となります。コードは特定の言語やフレームワークでの表現となります。ソフトウェアの保守は仕様書の進化を意味します。

**実行可能な仕様書**: 仕様書は、動作するシステムを生成するのに十分な正確さ、完全性、曖昧さのなさを持つ必要があります。これにより、意図と実装のギャップが排除されます。

**継続的な改善**: 一貫性の検証は一度限りのゲートではなく、継続的に行われます。AIは、曖昧さ、矛盾、ギャップについて仕様を分析します。

**リサーチ駆動のコンテキスト**: リサーチエージェントが仕様プロセス全体を通じて重要なコンテキストを収集し、技術的な選択肢、パフォーマンスの影響、組織の制約を調査します。

**双方向フィードバック**: 運用現実が仕様の進化を通知します。メトリクス、インシデント、運用から得られた学びが仕様の改善の入力となります。

**探索のためのブランチング**: 同じ仕様から複数の実装アプローチを生成し、パフォーマンス、保守性、ユーザーエクスペリエンス、コストなどの異なる最適化目標を探索します。

## 実装アプローチ

今日、SDDを実践するには、既存のツールを組み合わせ、このプロセス全体を通じて規律を維持する必要があります。この方法論は以下を使用して実践できます：

- 反復的な仕様開発のためのAIアシスタント
- 技術的なコンテキストを収集するためのリサーチエージェント
- 仕様を実装に変換するコード生成ツール
- 仕様優先のワークフローに適応したバージョン管理システム
- 仕様文書のAI分析による一貫性チェック

重要なのは、仕様書を真実の源泉とし、コードを仕様に従属する生成された成果物として扱うことです。

## ClaudeコマンドによるSDDの効率化

SDDの方法論は、仕様と計画のワークフローを自動化する2つの強力なClaudeコマンドによって大幅に強化されます。

### `new_feature` コマンド

このコマンドは、シンプルな機能の説明（ユーザープロンプト）を完全で構造化された仕様に変換し、自動的にリポジトリを管理します：

1. **自動機能番号付け**: 既存の仕様をスキャンして次の機能番号を決定（例: 001, 002, 003）
2. **ブランチ作成**: 説明からセマンティックなブランチ名を生成し、自動的に作成
3. **テンプレートベースの生成**: 機能仕様テンプレートをコピーして要件に合わせてカスタマイズ
4. **ディレクトリ構造**: 関連するすべてのドキュメントのために`specs/[branch-name]/`構造を作成

### `generate_plan` コマンド

機能仕様が存在すると、このコマンドは包括的な実装計画を作成します：

1. **仕様分析**: 機能要件、ユーザーストーリー、受け入れ基準を読み取り理解
2. **憲法準拠**: プロジェクト憲法とアーキテクチャ原則との整合性を確保
3. **技術的翻訳**: ビジネス要件を技術アーキテクチャと実装の詳細に変換
4. **詳細な文書化**: データモデル、API契約、テストシナリオのサポート文書を生成
5. **手動テスト計画**: 各ユーザーストーリーのステップバイステップの検証手順を作成

### 例: チャット機能の構築

これらのコマンドが従来の開発ワークフローをどのように変革するかを示します：

**従来のアプローチ:**
```
1. ドキュメントでPRDを書く（2〜3時間）
2. 設計文書を作成（2〜3時間）
3. プロジェクト構造を手動で設定（30分）
4. 技術仕様を書く（3〜4時間）
5. テスト計画を作成（2時間）
合計: ~12時間の文書作業
```

**SDDとコマンドのアプローチ:**
```bash
# ステップ1: 機能仕様を作成（5分）
/new_feature リアルタイムチャットシステム（メッセージ履歴とユーザーの存在感を含む）

# これにより自動的に以下が行われます：
# - ブランチ"003-chat-system"を作成
# - specs/003-chat-system/feature-spec.mdを生成
# - 構造化された要件で内容を埋める

# ステップ2: 実装計画を生成（10分）
/generate_plan WebSocketを使用したリアルタイムメッセージング、PostgreSQLを使用した履歴、Redisを使用した存在感

# これにより以下が自動的に作成されます：
# - specs/003-chat-system/implementation-plan.md
# - specs/003-chat-system/implementation-details/
#   - 00-research.md（WebSocketライブラリの比較）
#   - 02-data-model.md（メッセージとユーザースキーマ）
#   - 03-api-contracts.md（WebSocketイベント、RESTエンドポイント）
#   - 06-contract-tests.md（メッセージフローシナリオ）
#   - 08-inter-library-tests.md（データベース-WebSocket統合）
# - specs/003-chat-system/manual-testing.md
```

15分で以下が得られます：
- ユーザーストーリーと受け入れ基準を含む完全な機能仕様
- 技術選択とその根拠を含む詳細な実装計画
- コード生成の準備が整ったAPI契約とデータモデル
- 自動テストと手動テストの両方の包括的なテストシナリオ
- すべてのドキュメントが機能ブランチに適切にバージョン管理

### 構造化された自動化の力

これらのコマンドは時間を節約するだけでなく、一貫性と完全性を強制します：

1. **詳細の見落としなし**: テンプレートにより、非機能要件からエラーハンドリングまで、すべての側面が考慮されます
2. **追跡可能な決定**: すべての技術的選択が特定の要件にリンクされます
3. **生きた文書**: 仕様がコードと同期し続けるため、コードを生成します
4. **迅速な反復**: 要件を変更し、計画を数分で再生成

これらのコマンドは、仕様を静的な文書ではなく、実行可能な成果物として扱うことで、SDDの原則を体現しています。仕様プロセスを必要悪から開発の推進力に変えます。

### Template-Driven Quality: How Structure Constrains LLMs for Better Outcomes

The true power of these commands lies not just in automation, but in how the templates guide LLM behavior toward higher-quality specifications. The templates act as sophisticated prompts that constrain the LLM's output in productive ways:

#### 1. **Preventing Premature Implementation Details**

The feature specification template explicitly instructs:
```
- ✅ Focus on WHAT users need and WHY
- ❌ Avoid HOW to implement (no tech stack, APIs, code structure)
```

This constraint forces the LLM to maintain proper abstraction levels. When an LLM might naturally jump to "implement using React with Redux," the template keeps it focused on "users need real-time updates of their data." This separation ensures specifications remain stable even as implementation technologies change.

#### 2. **Forcing Explicit Uncertainty Markers**

Both templates mandate the use of `[NEEDS CLARIFICATION]` markers:
```
When creating this spec from a user prompt:
1. **Mark all ambiguities**: Use [NEEDS CLARIFICATION: specific question] 
2. **Don't guess**: If the prompt doesn't specify something, mark it
```

This prevents the common LLM behavior of making plausible but potentially incorrect assumptions. Instead of guessing that a "login system" uses email/password authentication, the LLM must mark it as `[NEEDS CLARIFICATION: auth method not specified - email/password, SSO, OAuth?]`.

#### 3. **Structured Thinking Through Checklists**

The templates include comprehensive checklists that act as "unit tests" for the specification:
```
### Requirement Completeness
- [ ] No [NEEDS CLARIFICATION] markers remain
- [ ] Requirements are testable and unambiguous  
- [ ] Success criteria are measurable
```

These checklists force the LLM to self-review its output systematically, catching gaps that might otherwise slip through. It's like giving the LLM a quality assurance framework.

#### 4. **Constitutional Compliance Through Gates**

The implementation plan template enforces architectural principles through phase gates:
```
### Phase -1: Pre-Implementation Gates
#### Simplicity Gate (Article VII)
- [ ] Using ≤3 projects?
- [ ] No future-proofing?
#### Anti-Abstraction Gate (Article VIII)
- [ ] Using framework directly?
- [ ] Single model representation?
```

These gates prevent over-engineering by making the LLM explicitly justify any complexity. If a gate fails, the LLM must document why in the "Complexity Tracking" section, creating accountability for architectural decisions.

#### 5. **Hierarchical Detail Management**

The templates enforce proper information architecture:
```
**IMPORTANT**: This implementation plan should remain high-level and readable. 
Any code samples, detailed algorithms, or extensive technical specifications 
must be placed in the appropriate `implementation-details/` file
```

This prevents the common problem of specifications becoming unreadable code dumps. The LLM learns to maintain appropriate detail levels, extracting complexity to separate files while keeping the main document navigable.

#### 6. **Test-First Thinking**

The implementation template enforces test-first development:
```
### File Creation Order
1. Create `contracts/` with API specifications
2. Create test files in order: contract → integration → e2e → unit
3. Create source files to make tests pass
```

This ordering constraint ensures the LLM thinks about testability and contracts before implementation, leading to more robust and verifiable specifications.

#### 7. **Preventing Speculative Features**

Templates explicitly discourage speculation:
```
- [ ] No speculative or "might need" features
- [ ] All phases have clear prerequisites and deliverables
```

This stops the LLM from adding "nice to have" features that complicate implementation. Every feature must trace back to a concrete user story with clear acceptance criteria.

### The Compound Effect

These constraints work together to produce specifications that are:
- **Complete**: Checklists ensure nothing is forgotten
- **Unambiguous**: Forced clarification markers highlight uncertainties
- **Testable**: Test-first thinking baked into the process
- **Maintainable**: Proper abstraction levels and information hierarchy
- **Implementable**: Clear phases with concrete deliverables

The templates transform the LLM from a creative writer into a disciplined specification engineer, channeling its capabilities toward producing consistently high-quality, executable specifications that truly drive development.

## The Constitutional Foundation: Enforcing Architectural Discipline

At the heart of SDD lies a constitution—a set of immutable principles that govern how specifications become code. The constitution (`base/memory/constitution.md`) acts as the architectural DNA of the system, ensuring that every generated implementation maintains consistency, simplicity, and quality.

### The Nine Articles of Development

The constitution defines nine articles that shape every aspect of the development process:

#### Article I: Library-First Principle
Every feature must begin as a standalone library—no exceptions. This forces modular design from the start:
```
Every feature in Specify MUST begin its existence as a standalone library. 
No feature shall be implemented directly within application code without 
first being abstracted into a reusable library component.
```

This principle ensures that specifications generate modular, reusable code rather than monolithic applications. When the LLM generates an implementation plan, it must structure features as libraries with clear boundaries and minimal dependencies.

#### Article II: CLI Interface Mandate
Every library must expose its functionality through a command-line interface:
```
All CLI interfaces MUST:
- Accept text as input (via stdin, arguments, or files)
- Produce text as output (via stdout)
- Support JSON format for structured data exchange
```

This enforces observability and testability. The LLM cannot hide functionality inside opaque classes—everything must be accessible and verifiable through text-based interfaces.

#### Article III: Test-First Imperative
The most transformative article—no code before tests:
```
This is NON-NEGOTIABLE: All implementation MUST follow strict Test-Driven Development.
No implementation code shall be written before:
1. Unit tests are written
2. Tests are validated and approved by the user
3. Tests are confirmed to FAIL (Red phase)
```

This completely inverts traditional AI code generation. Instead of generating code and hoping it works, the LLM must first generate comprehensive tests that define behavior, get them approved, and only then generate implementation.

#### Articles VII & VIII: Simplicity and Anti-Abstraction
These paired articles combat over-engineering:
```
Section 7.3: Minimal Project Structure
- Maximum 3 projects for initial implementation
- Additional projects require documented justification

Section 8.1: Framework Trust
- Use framework features directly rather than wrapping them
```

When an LLM might naturally create elaborate abstractions, these articles force it to justify every layer of complexity. The implementation plan template's "Phase -1 Gates" directly enforce these principles.

#### Article IX: Integration-First Testing
Prioritizes real-world testing over isolated unit tests:
```
Tests MUST use realistic environments:
- Prefer real databases over mocks
- Use actual service instances over stubs
- Contract tests mandatory before implementation
```

This ensures generated code works in practice, not just in theory.

### Constitutional Enforcement Through Templates

The implementation plan template operationalizes these articles through concrete checkpoints:

```markdown
### Phase -1: Pre-Implementation Gates
#### Simplicity Gate (Article VII)
- [ ] Using ≤3 projects?
- [ ] No future-proofing?

#### Anti-Abstraction Gate (Article VIII)
- [ ] Using framework directly?
- [ ] Single model representation?

#### Integration-First Gate (Article IX)
- [ ] Contracts defined?
- [ ] Contract tests written?
```

These gates act as compile-time checks for architectural principles. The LLM cannot proceed without either passing the gates or documenting justified exceptions in the "Complexity Tracking" section.

### The Power of Immutable Principles

The constitution's power lies in its immutability. While implementation details can evolve, the core principles remain constant. This provides:

1. **Consistency Across Time**: Code generated today follows the same principles as code generated next year
2. **Consistency Across LLMs**: Different AI models produce architecturally compatible code
3. **Architectural Integrity**: Every feature reinforces rather than undermines the system design
4. **Quality Guarantees**: Test-first, library-first, and simplicity principles ensure maintainable code

### Constitutional Evolution

While principles are immutable, their application can evolve:
```
Section 4.2: Amendment Process
Modifications to this constitution require:
- Explicit documentation of the rationale for change
- Review and approval by project maintainers
- Backwards compatibility assessment
```

This allows the methodology to learn and improve while maintaining stability. The constitution shows its own evolution with dated amendments, demonstrating how principles can be refined based on real-world experience.

### Beyond Rules: A Development Philosophy

The constitution isn't just a rulebook—it's a philosophy that shapes how LLMs think about code generation:

- **Observability Over Opacity**: Everything must be inspectable through CLI interfaces
- **Simplicity Over Cleverness**: Start simple, add complexity only when proven necessary
- **Integration Over Isolation**: Test in real environments, not artificial ones
- **Modularity Over Monoliths**: Every feature is a library with clear boundaries

By embedding these principles into the specification and planning process, SDD ensures that generated code isn't just functional—it's maintainable, testable, and architecturally sound. The constitution transforms AI from a code generator into an architectural partner that respects and reinforces system design principles.

## The Transformation

This isn't about replacing developers or automating creativity. It's about amplifying human capability by automating mechanical translation. It's about creating a tight feedback loop where specifications, research, and code evolve together, each iteration bringing deeper understanding and better alignment between intent and implementation.

Software development needs better tools for maintaining alignment between intent and implementation. SDD provides the methodology for achieving this alignment through executable specifications that generate code rather than merely guiding it.