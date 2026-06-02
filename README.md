# decision-log — Claude Code skill

**あなたの意思決定を、AI が学べるデータに変える Claude Code スキル。**

値付け・交渉・人の配置・優先順位・Go/No-Go ―
日々の判断を、会話の流れを壊さず**バックグラウンドで構造化記録**する。

---

## なぜ作ったか

人を AI に置き換える/任せる第一歩は「判断基準のデータ化」だと考えている。

頭の中だけにある「なぜその値段にしたか」「なぜその人に任せたか」は、放っておくと消える。
これを毎日 3 個記録すれば、3 ヶ月で 270 個の学習データになる。
後からパターンを言語化すれば、AI や仲間が**同じ基準で動ける**ようになる。

現役の建設会社経営者が、建設・eBay・SaaS の 3 事業を Claude Code で回す中で実際に使っているスキルを、汎用化して公開した。

## 何をするか

- **自動検知**：会話中に判断（pricing / negotiation / staffing / material / priority / go-nogo）を検知したら、黙って `logs/decisions.md` に追記。
- **手動記録**：`/decision` または「判断ログ」で明示的に記録。
- **構造化**：領域・場面・判断・理由・カテゴリ・確信度 を 1 行で。
- **月次集計**（任意）：分布とパターンを集計し、「判断基準の言語化」まで落とす。
- **連携**（任意）：日記・週次/月次レビュー・朝の起動に統合できる。

## 記録フォーマット

```markdown
| # | 時刻 | 領域 | 場面 | 判断 | 理由 | カテゴリ | 確信度 |
|---|---|---|---|---|---|---|---|
| 1 | 09:30 | product | 価格設定 | 1,480/月で仮設定 | まず出して後から変更 | pricing | 迷いなく |
```

## インストール

このリポジトリの `skills/decision-log/` を、あなたのプロジェクトの `.claude/skills/` に置くだけ。

```bash
cp -r skills/decision-log /path/to/your-project/.claude/skills/
```

Claude Code が自動でスキルを認識する。`logs/decisions.md` は初回記録時に自動生成される。

## 使い方

- 普段どおり Claude Code と会話する。判断が出たら自動で記録される。
- 明示的に残したい時は `/decision`。
- 月末に「判断ログを集計して」と言えば月次レポートを生成。

## カスタマイズ

- **領域 (area)**：`sales / hiring / product / ops` など、自分の事業/分野に合わせて自由に定義。
- **カテゴリ**：`pricing / negotiation / staffing / material / priority / go-nogo / other`。増やしてよい。
- 詳細は `skills/decision-log/SKILL.md` を参照。

---

## English

**A Claude Code skill that turns your decisions into data an AI can learn from.**

It silently logs your real decisions (pricing, negotiation, staffing, priorities, go/no-go) into `logs/decisions.md` without breaking your conversation flow. 1 log/day = 270 data points in 3 months — the raw material for encoding *how you decide* so an AI (or teammate) can act on the same judgment.

Install: copy `skills/decision-log/` into your project's `.claude/skills/`. Trigger automatically, or manually with `/decision`.

---

## Author

現役建設会社経営者 / 大山 隆弥志（Takayoshi Oyama）
建設20年 × AI × コード。3事業を Claude Code で運用中。
X: [@takayoshioyama](https://x.com/takayoshioyama)

## License

MIT — see [LICENSE](./LICENSE).
