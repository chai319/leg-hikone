# LEG彦根 公式サイト

滋賀・彦根の教育者グループ **LEG彦根**（Learning Ecosystem Group Hikone）の公式サイトです。
Googleサイト版（`sites.google.com/view/lgehikone`）から移行しました。

**公開URL**: https://chai319.github.io/leg-hikone/

---

## 構成

```
leg-hikone/
├── index.html            ← サイト本体（HTML + CSS + JS を1ファイルに内包）
├── 404.html              ← 存在しないURLへのアクセス時
├── favicon.svg           ← ブラウザタブのアイコン
├── apple-touch-icon.png  ← iOSホーム画面アイコン (180×180)
├── og-image.jpg          ← SNSシェア時のサムネイル (1200×630)
├── README.md
└── assets/img/
    ├── hero-banner.webp        ← キービジュアル（彦根城）
    ├── logo-leg-hikone.webp    ← LEG彦根公式ロゴ
    ├── member-kubokawa.webp
    ├── member-nishimoto.webp
    ├── member-tokuchiyo.webp
    └── flyer-2024-10-03.webp   ← ICTカフェのフライヤー
```

- **ビルド不要**。`index.html` をブラウザで開けばそのまま動きます
- 外部への依存は **Google Fonts のみ**（アイコンはSVGを内蔵）
- パスはすべて相対パス。フォルダごと別の場所へ移しても動きます

---

## 更新のしかた

編集後に `git add` → `git commit` → `git push` すると、1〜2分で公開サイトに反映されます。

### 1. お知らせを追加する

`index.html` 内の `<!-- お知らせを追加するときは… -->` コメントを探し、
`<ul class="news-list">` の**先頭**に以下を貼り付けて書き換えます。

```html
<li class="news-item rv">
  <p class="news-date">
    <svg class="icon" aria-hidden="true"><use href="#i-cal"/></svg>
    2026.04.01
  </p>
  <p>ここにお知らせ本文を書きます。</p>
</li>
```

### 2. コアメンバーを追加する

`<ul class="mgrid">` の中の `<li class="mcard rv">` をまるごとコピーして、氏名・所属・タグを差し替えます。
役職バッジのクラスは 3 種類（`role-1` リーダー / `role-2` 副リーダー / `role-3` スーパーバイザー）です。

### 3. 連携LEGを追加する

`<ul class="ngrid">` の中の `<li>` をコピーして、リンク先・名前・ドメイン表示を差し替えます。
枚数が増えても自動で折り返します。

### 4. 活動実績を追加する

`<ol class="tl">` の**先頭**に `<li class="tl-item rv">` を追加します（新しい順に並べます）。

### 5. 写真を差し替える

1. 新しい画像を `assets/img/` に置きます（**WebP形式・長辺720px以内**を推奨）
2. `index.html` の該当 `<img src="...">` を書き換えます
3. 顔の位置がずれる場合は、同じ `<img>` の `style="object-position: 65% 52%"` の数値を調整します
   （1つ目=左右、2つ目=上下。数字を小さくすると左/上へ寄ります）

---

## 気をつけること

- **画像の合計サイズは 450KB 以内**に保ってください（スマホでの表示速度のため）
- **メールアドレス・電話番号・QRコードを画像内に含めないでください**
  （フライヤー画像は、申込欄をトリミングして掲載しています）
- 掲載する氏名・所属・受賞歴は、必ず**本人に確認した事実**だけを書いてください
- 文字色に明るい緑（`--teal-500` / `--emerald-400`）を使わないでください
  （白背景でコントラスト不足になります。文字は `--teal-700` を使います）

---

## GitHub Pages の設定

Settings → Pages → Source: `Deploy from a branch` / Branch: `main` / Folder: `/ (root)`

---

## 出典

- 元サイト: https://sites.google.com/view/lgehikone/ホーム
- アイコン形状は [Lucide](https://lucide.dev/)（ISC License）を参考にした自作SVG
- フォント: Google Fonts（Plus Jakarta Sans / Noto Sans JP）
