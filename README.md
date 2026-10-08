# apm-team-skills

[APM（Agent Package Manager）](https://github.com/microsoft/apm) で、チームのプロジェクトに Agent Skills を同じ版で配る方法を試すための検証用リポジトリです。

- `bundle/` … チームで使うスキルの一式（APM パッケージ）。中身は [anthropics/skills](https://github.com/anthropics/skills) の `skill-creator` と `webapp-testing` を題材として参照しています。
- `consumer/` … 一式を使う側のプロジェクト。`apm install` で Claude Code 用（`.claude/skills/`）と GitHub Copilot 用（`.agents/skills/`）に展開したファイルと、`apm.lock.yaml` をコミットしています。
- `.github/workflows/skills-check.yml` … PR ごとに `apm audit --ci` を実行し、展開済みのスキルが手で書き換えられていないか、`apm.yml` と lock が食い違っていないかを検査します。

## ライセンス

`consumer/.claude/skills/` と `consumer/.agents/skills/` の各スキルは Anthropic のもので、Apache License 2.0 です（各ディレクトリの `LICENSE.txt` を参照）。それ以外のファイルは検証用のサンプルです。
