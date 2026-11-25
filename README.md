# ushidakyotaro.github.io

# ファイル構成
```
/ (リポジトリルート)
├── _config.yml             # サイト全体の設定（タイトル、URL、プラグイン等）
├── index.html              # ホーム画面（Hero、経歴概要、最新記事一覧）
├── 404.md                  # ページが見つからない時のエラー画面
├── cv.md                   # 詳細な経歴・受賞歴を表示するページ
├── categories.html         # 全カテゴリーの記事をハッシュ(#)で切り替えて出すページ
├── contact.md              # お問い合わせページ（Googleフォーム埋め込み等）
├── news.md                 # newsを表示
│
├── _data/                  # サイトのコンテンツデータを管理
│   ├── navigation.yml      # ヘッダーメニューのリンク集
│   ├── social.yml          # SNSのリンクとアイコン設定
│   └── cv.yml              # 経歴や受賞歴の具体的なデータ（ここを直せば各所が更新される）
│
├── _includes/              # 各ページで使い回す部品
│   ├── header.html         # サイト上部のロゴとナビメニュー
│   ├── sidebar.html        # プロフィール、カテゴリー一覧（右側）
│   ├── footer.html         # サイト下部のコピーライト等
│   └── breadcrumbs.html    # 記事ページに表示するパンくずリスト
│
├── _layouts/               # ページの「型」を定義
│   ├── default.html        # 基本レイアウト（全ページのベース）
│   └── post.html           # ブログ記事専用のレイアウト
│
├── _posts/                 # 公開済みのブログ記事（YYYY-MM-DD-title.md）
├── _news/                 # 公開済みのnews記事（YYYY-MM-DD-title.md）
├── _drafts/                # 下書き中の記事（本番には表示されない）
├── Gemfile                 # ローカルでjekyllを使うようの設定
│
└── assets/                 # 画像やスタイルシートなどの素材
    ├── css/
    │   └── style.scss      # Qiita風デザインやレイアウトを定義したメインCSS
    └── images/
        ├── profile.jpg     # サイドバーに表示する顔写真
        └── favicon.ico     # ブラウザのタブに表示されるアイコン

```

# ローカルで確認する方法
```
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev

gem install jekyll bundler
bundle install
bundle exec jekyll serve
```

```
cd ~/docker/jekell_site
docker compose up
```

# github pagesに公開する方法
```
# 1. 変更したファイルをステージングに追加
git add .

# 2. コミットメッセージを付けて確定
git commit -m "Add new post: 記事のタイトル"

# 3. GitHubへ送信
git push origin main
```


# 公開方法
ファイル名を変更する: YYYY-MM-DD-タイトル.md の形式に日付を付けます。

移動する: ファイルを _drafts フォルダから _posts フォルダへ移動します。

プッシュする: GitHub にプッシュすると、正式な記事として公開されます。

# 英語版ページ（多言語）
- 英語ページは `en/` 以下（`en/index.html`, `en/cv.md`, `en/contact.md`）。`_config.yml` の defaults で `lang: en` が自動で付く。
- 日本語版と英語版は front matter の `ref:` を同じ値にすると対応づけられ、ヘッダーの言語切替リンクと hreflang が自動で出る。
- CV のデータは `_data/cv.yml` に `{ja: ..., en: ...}` の形で日英を併記する（`_includes/t.html` が言語に応じて選ぶ）。
- 英語メニューは `_data/navigation.yml` の `en:`。
- メールアドレスは `_config.yml` の `email_user` / `email_domain` を変更する。

# 記事を書く時の注意
カテゴリー：
        順番を守る: 必ず [親, 子, 孫] の順で書く（パンくずリストは書かれた順にループするため）。

# comment
<script src="https://utteranc.es/client.js"
        repo="ushidakyotaro/ushidakyotaro.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>