# bisii.co.jp

株式会社ビシィッ コーポレートサイト。Astro + GitHub Pages。

## 開発

```sh
npm install
npm run dev
```

`http://localhost:4321` で確認できます。

## デプロイ（GitHub Pages）

1. GitHubリポジトリの **Settings → Pages** で、Source を **GitHub Actions** に設定
2. `main` ブランチにpushすると `.github/workflows/deploy.yml` が自動でビルド・デプロイ
3. `public/CNAME` に `www.bisii.co.jp` を設定済み。DNS側のCNAMEレコードが
   GitHub Pages（`<username>.github.io`）を向くよう設定してください
   （参考: https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site）

## お問い合わせフォーム（要設定）

`src/pages/contact.astro` 内の `FORMSPREE_ENDPOINT` を、
[Formspree](https://formspree.io) で無料登録後に発行されるフォームIDに差し替えてください。

```ts
const FORMSPREE_ENDPOINT = "https://formspree.io/f/YOUR_FORM_ID";
```

## ブログ記事の追加

`src/content/blog/` にMarkdownファイルを追加するだけで `/blog` に反映されます。

```md
---
title: "記事タイトル"
description: "概要"
pubDate: 2026-08-01
tags: ["お知らせ"]
---

本文をここに書く。
```

## SEO / AIO

- `astro.config.mjs` の `site` に本番URLを設定済み（sitemap.xml自動生成）
- `public/robots.txt`、`public/llms.txt` を設置済み
- 各ページに canonical / OGP / Organization・Articleの構造化データ（JSON-LD）を出力
