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
├── article.html            # ブログ記事一覧（Research & Tech / Life に分けて表示）
├── notes.md                # Notes（研究の基礎知識）一覧をテーマ別に表示
├── en/                     # 英語版ページ（Home / CV / Contact）
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
│   ├── post.html           # ブログ記事専用のレイアウト
│   └── note.html           # Notes 専用のレイアウト（_notes/ に自動適用）
│
├── _posts/                 # 公開済みのブログ記事（YYYY-MM-DD-title.md）
├── _notes/                 # 研究の基礎知識ノート（_notes/<テーマ>/<スラッグ>.md）
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

# Notes（研究の基礎知識）の書き方
`_notes/<テーマのフォルダ>/<スラッグ>.md` に置くと `/notes/<テーマのフォルダ>/<スラッグ>/` で公開される。
日付順のブログではなく、テーマごとにまとめて随時更新する前提。レイアウトと数式(KaTeX)は自動で有効になる。
```yaml
---
title: "知の創成 1"
topic: "身体性認知科学"   # 一覧での見出し。同じ値のノートがまとまる
order: 1                  # テーマ内の並び順（前後リンクもこの順）
updated: 2026-02-06       # 最終更新日。内容を直したら更新する
references:               # 任意。ページ末尾に参考文献として出る
  - title: "著者『書名』出版社"
    url: "https://..."
---
```
- 書籍のまとめは自分の言葉で書き、引用は最小限・図表の転載はしない。未発表の研究内容は書かない。
- 記事を別の場所に移したときは `redirect_from: [/旧URL/]` を付けると旧URLから転送される。

# 趣味の記事（Life）
通常の `_posts` に書き、`categories: [Life, 旅行]` のように **先頭に `Life`** を付ける。
記事一覧（/article/）の「Life」セクションに表示され、Home の「Recent Blog Posts」には出ない。

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