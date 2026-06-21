# Migration.fm

[Migration.fm](https://migration.fm) — Salesforce Developer 向け Podcast サイトのリポジトリです。Jekyll + GitHub Pages で構築しています。

## ローカル環境の構築

### 前提条件

- Git
- Ruby（最新安定版を推奨）
- Bundler

### 1. Ruby のインストール（rbenv を使う場合）

```sh
# rbenv と ruby-build をインストール
brew install rbenv ruby-build

# シェル設定に rbenv を追加（bash の場合は ~/.bash_profile）
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
source ~/.zshrc

# 最新安定版の Ruby をインストール
rbenv install $(rbenv install -l | grep -v - | tail -1)
rbenv global <インストールしたバージョン>

# 確認
ruby -v
```

### 2. Bundler のインストール

```sh
gem install bundler
```

### 3. 依存 gem のインストール

```sh
bundle install
```

### 4. ローカルサーバーの起動

```sh
bundle exec jekyll serve
```

ブラウザで http://localhost:4000 にアクセスします。

ファイルを変更するたびに自動で再ビルドしたい場合:

```sh
bundle exec jekyll serve --livereload
```

### 5. ビルドのみ実行

```sh
bundle exec jekyll build
```

ビルド結果は `_site/` ディレクトリに出力されます（`.gitignore` で除外済み）。

## 注意事項

- `CNAME` に `migration.fm` が設定されているため、`master` ブランチへのプッシュで本番環境に反映されます
- `README.md` は `_config.yml` の `exclude` に指定されており、GitHub Pages には公開されません
