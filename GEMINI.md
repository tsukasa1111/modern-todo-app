このプロジェクトでは、すべての実装ログを _docs/templates/ に Markdown 形式（yyyy-mm-dd_機能名.md）で記録しています。

各実装タスクが完了してコミットされたら、自動で以下の構成のMarkdownファイルを生成してください：

ファイル名：yyyy-mm-dd_機能名.md
保存先：`_docs/templates/`
内容構成（日本語）：
  1. 機能名
  2. 実装日
  3. 概要
  4. 変更点（箇条書き）
  5. 副作用／考慮事項
  6. 関連ファイル
  7. 設計意図
末尾に以下のインストラクション文も含めてください：

このプロジェクトでは、すべての実装ログが docs/templates/ に yyyy-mm-dd機能名.md の形式で保存されています。起動時にこのディレクトリを全読み込みし、過去の設計意図・変更履歴・副作用を踏まえてタスク提案を行ってください。
今後、すべての実装ごとにこのログ出力を自動で行ってください。

## 通知ルール
**必須**: あらゆるタスク完了時は必ず通知を送信してください。例外はありません。通知内容は実行したタスクに応じて適切に記述すること。

### 通知テンプレート（タスク別サウンド）

#### 1. ファイル編集完了
```bash
osascript -e 'display notification " ファイル編集完了: [ファイル名]" with title "Claude Code" sound name "Tink"'
```

#### 2. ビルド・コンパイル完了
```bash
osascript -e 'display notification " ビルド完了" with title "Claude Code" sound name "Hero"'
```

#### 3. テスト実行完了
```bash
osascript -e 'display notification "✅ テスト実行完了 ([結果])" with title "Claude Code" sound name "Glass"'
```

#### 4. 検索・分析完了
```bash
osascript -e 'display notification " 検索・分析完了" with title "Claude Code" sound name "Ping"'
```

#### 5. インストール・設定完了
```bash
osascript -e 'display notification " インストール・設定完了" with title "Claude Code" sound name "Funk"'
```

## 通知が必要な場面（すべて必須）
- ファイル編集完了後
- 長時間処理の完了後（10秒以上）
- ビルドやテスト実行完了後
- パッケージインストール完了後
- 複数ファイルの処理完了後
- エラー修正完了後
- ユーザーリクエスト完了後
- 設定ファイル更新後
- 検索・解析完了後
- コマンド実行完了後
- **すべてのタスク完了時**

**重要**: 通知内容は必ず具体的で分かりやすく記述すること

## 絶対禁止事項
- テストエラーや型エラー解消のための条件緩和
- テストのスキップや不適切なモック化による回避
- 出力やレスポンスのハードコード
- エラーメッセージの無視や隠蔽
- 一時的な修正による問題の先送り
