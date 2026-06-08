# task-board

タスク管理ボードアプリケーション用のプロジェクトです。

## デプロイ先

[https://ysawada0022.github.io/task-board/](https://ysawada0022.github.io/task-board/)

`main` ブランチへのpushをトリガーに、GitHub Actions（[.github/workflows/deploy.yml](.github/workflows/deploy.yml)）が自動でビルド・デプロイを行う。

## 技術スタック

- React 19
- Vite（ビルド・開発サーバー）
- ESLint
- プレーンCSS（[src/App.css](src/App.css)）
- 状態の永続化は `localStorage` を使用（外部の状態管理ライブラリは未使用）

## コンポーネントの命名規約

- コンポーネントファイルは `PascalCase.jsx`（例: [App.jsx](src/App.jsx)）
- 各コンポーネントには対応する同名のCSSファイルを置く（例: `App.jsx` ⇔ `App.css`）
- CSSのクラス名は `kebab-case`（例: `task-form`, `task-list`, `delete-button`）
- 状態変更を行う関数は `動詞 + 対象` の形式で命名する（例: `addTask`, `toggleTask`, `deleteTask`）

## Git運用ルール

- **コードを変更したら、その都度コミットしてGitHubにプッシュすること。**
  - 変更をローカルに溜め込まず、小さい単位でコミット・プッシュを行う。
  - コミットメッセージは変更内容と「なぜ」変更したのかが分かるように簡潔に書く。
  - プッシュ前に `git status` / `git diff` で変更内容を確認する。
  - force push やコミットの amend など、履歴を書き換える操作は行わない。

## 開発の進め方

- 既存のコードスタイル・構成に合わせる。
- 不要な抽象化やリファクタリングは行わず、依頼された変更に集中する。
- コメントは「なぜ」が自明でない場合のみ最小限で記述する。
