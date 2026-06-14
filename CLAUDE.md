# バブルガムのゲームブログ／読書ブログ 執筆ルール

このリポジトリは、はてなブログ記事（HTML直書き）の作成・リライト用の作業場です。
記事を作成・リライトする際は、必ず以下のルールに従ってください。

## ブログ基本情報

| 項目 | 内容 |
|---|---|
| ゲームブログ | babblegum.hatenablog.com（バブルガムのゲームブログ） |
| 読書ブログ | bubble-books.com（バブルガムの読書録） |
| Amazonタグ | bubblegumkk0d-22 |
| 楽天アフィリエイトID | 4ef94133.1f1592cd.4ef94134.ad13b72f |
| メルカリアンバサダーafid | 6396715167 |
| メルカリ招待コード | YRCNMN（新規ユーザー向け500P付与） |
| ブログエンジン | はてなブログ（HTML直書き） |
| AdSense | 未通過（再申請準備中） |

ブログのトーン：一人称・体験談ベース、ジャンル横断、ですます調

---

## ★最重要：記事の設計思想（他のすべてに優先する）

「SEOテンプレを埋めた量産記事」ではなく「人間が最後まで読みたくなる体験談」を目指す。
この思想を、フォーマットルールよりも上位の判断基準とする。

優先順位：
1. 第一に、人間が読み続けたくなる文章（フック・体験・人間味）
2. 第二に、検索意図を満たす実用情報（読者の問題解決）
3. 第三に、SEOの技術的整備（見出しキーワード・構造化データなど）

SEO対策は「やりすぎない」ことが、結果的に最もSEOに効く。

### 伸びる記事の構造

冒頭で結論を機械的に出すのではなく、読者を引き込むフックを置く。次のいずれか/複数：
- 具体的な情景・体験の一場面（その人にしか書けない入り）
- 読者のあるあるへの共感
- 意外性のある一言・問いの提示

結論は冒頭で全部言わず、フックで惹きつけたあと自然な流れで早めに示す。

### 人間味の出し方

- 一次情報を入れる（実際に詰まった点・試した手順・失敗・感想）。これがAIっぽさを消す最大の武器。
- 完璧に整えすぎない。脱線・こだわり・率直な本音を残す。
- 断定とためらいを混ぜる（「正直、最初はナメていました」など、書き手の温度）。
- 体言止め・短文を効果的に挟みリズムを作る。

### やってはいけないこと（AIっぽさ・SEO過剰）

- 機械的な結論ボックスを毎回冒頭に置く（k-conclusion-boxはデフォルト廃止）
- 「いかがでしたか」「まとめると以下の通りです」式の中身のない締め
- キーワードの不自然な繰り返し
- 全見出しに同じ型のキーワードを機械的に入れる（見出しの説明文化）
- 網羅しようとして書き手の視点が消えカタログ化する
- FAQ・各種ボックスを「埋めるべき枠」として惰性で全部入れる
- 冒頭に「この記事では〜を解説します」式のメタ説明（記事の予告・道案内）を置く。いきなり本題の体験・話に入る。読めば自然に伝わる流れを、わざわざ先回りして説明しない
- 過剰な前置き・全部説明。文脈で察せられることは書かない。何から何まで説明すると逆に読みにくくなる

判断に迷ったら「これは読者の体験を良くするか、枠を埋めているだけか」を自問する。

---

## リライト・新規作成の標準フロー

1. 競合記事をWebSearchで確認（大手・個人ブログ両方）。上位の構成と薄い箇所を見る。
2. 競合の強み・弱みを分析し、バブルガムだけが書ける一次情報・体験・視点を特定（記事の背骨）。
3. 冒頭のフックを設計する（結論の前に、情景・共感・問い）。
4. 検索意図を満たす実用情報を、体験談の流れに自然に織り込む。
5. SEOの技術整備は最後に、邪魔にならない範囲で（見出しにメインKW、構造化データ、内部リンク）。
6. タイトル案を3〜5個提示（SEO重視・SNS重視・データ訴求・情緒型などバリエーション）。

### 各要素は「必須」ではなく「適切なら使う」

惰性で全部入れない。読者体験を高める場合のみ使う。

- 結論ボックス（k-conclusion-box）：原則デフォルトでは置かない。価格比較や「結局どれを買えばいいか」が主目的の実用記事など、読者が結論を急いでいることが明確な場合のみ。
- FAQ：検索で実際に問われ、本文で拾いきれない疑問がある場合のみ。2〜3問でもよい。数を優先しない。
- good-box / bad-box：適性が分かれるレビューで有効。日記的記事では不要なことも多い。
- 星評価（verdict-box）：明確に評価をくだすレビュー記事のみ。
- Schema.org：型が明確に当てはまる場合のみ。FAQPageは実際にFAQを置いたときだけ。

---

## 記事フォーマットルール

### 禁止事項（絶対厳守）

- `<strong>` タグ禁止 → `style="font-weight: bold"` を使う
- アスタリスク強調（`** **`）禁止
- かぎかっこ「『』」禁止（書名も「」か《》）
- 「——」「──」ダッシュ禁止（読点や句点で置換）
- `<h4>` `<h5>` タグ禁止（h2.section-head / h3.sub-head、読書ブログはh4-block/h5-blockクラス付きdiv）
- 断るときに箇条書きリスト禁止（文章で書く）
- 他のレビューサイト・他人の意見への直接言及禁止（「ネットの声では」等も禁止）
- 「いかがでしたか」式の中身のない締め禁止
- キーワードの不自然な詰め込み禁止

### 文体

- 基本はです・ます調。ただし自然な日本語優先。体言止め・短文も使う。
- 一人称・体験談ベース。書き手の温度・本音・こだわりを残す。
- 冒頭はフックを優先し、機械的な要約リストを置かない。
- 冒頭で記事の内容を予告・道案内しない（「この記事では〜を解説します」式は禁止）。本題からそのまま書き出す。
- 文脈で理解できることは説明しない。全部を丁寧に補足すると逆に読みにくくなる。引き算を意識する。

### はてなブログ固有の記法

- 目次：`[:contents]`
- 内部リンク埋め込み：iframeのembedカード形式
  ```html
  <iframe src="https://hatenablog-parts.com/embed?url=[URL]" class="embed-card embed-blogcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 190px; max-width: 500px; margin: 10px 0px;" loading="lazy"></iframe>
  ```
- 画像：hatena-fotolife形式
  ```html
  <figure class="figure-image figure-image-fotolife mceNonEditable">
  <img src="https://cdn-ak.f.st-hatena.com/..." width="1200" height="675" loading="lazy" class="hatena-fotolife" itemprop="image" />
  <figcaption>キャプション</figcaption>
  </figure>
  ```

---

## アフィリエイトリンク形式

### Amazon（商品カード）
単体商品レビュー記事、またはサムネ兼用時に使う。
```html
<div class="freezed">
<div class="hatena-asin-detail">
  <a href="https://www.amazon.co.jp/dp/ASIN?tag=bubblegumkk0d-22&linkCode=osi&th=1&psc=1" class="hatena-asin-detail-image-link" target="_blank" rel="sponsored noopener">
    <img src="AMAZON_IMAGE_URL" class="hatena-asin-detail-image" alt="商品名" />
  </a>
  <div class="hatena-asin-detail-info">
    <p class="hatena-asin-detail-title">
      <a href="https://www.amazon.co.jp/dp/ASIN?tag=bubblegumkk0d-22&linkCode=osi&th=1&psc=1" target="_blank" rel="sponsored noopener">商品名</a>
    </p>
    <ul class="hatena-asin-detail-meta"><li>メーカー名</li></ul>
    <a href="https://www.amazon.co.jp/dp/ASIN?tag=bubblegumkk0d-22&linkCode=osi&th=1&psc=1" class="asin-detail-buy" target="_blank" rel="sponsored noopener">Amazon</a>
  </div>
</div>
</div>
```
注意：このカードを `.shop-buttons`（flexコンテナ）の中に入れない。独立して配置する。

### Amazon検索リンク（ASIN不明時）
```
https://www.amazon.co.jp/s?k=検索キーワード&tag=bubblegumkk0d-22
```

### 楽天検索リンク（在庫切れに強い）
```
https://hb.afl.rakuten.co.jp/hgc/4ef94133.1f1592cd.4ef94134.ad13b72f/?pc=https%3A%2F%2Fsearch.rakuten.co.jp%2Fsearch%2Fmall%2F[URLエンコードした検索キーワード]%2F&link_type=text&ut=eyJwYWdlIjoic2VhcmNoIiwidHlwZSI6InRleHQiLCJjb2wiOjF9
```

### ★メルカリ検索リンク
**afid `6396715167` を必ず付与。afidがないリンクは報酬対象外。**
```
https://jp.mercari.com/search?afid=6396715167&keyword=[URLエンコードした検索キーワード]
```
ルール：
- ベース形式 `https://jp.mercari.com/search?afid=6396715167&keyword=[URLエンコード済みKW]` で固定。AIが組み立て可。
- 複数単語の場合、スペースは `+` でエンコードする（例：「ゲーム ps5」→ `keyword=%E3%82%B2%E3%83%BC%E3%83%A0+ps5`）。
- HTML埋め込み時の `&` → `&amp;` エスケープのみ可。他パラメータの追加・改変はしない。
- **category_id は付けない**。
- 記事内にメルカリリンク発行依頼などのリマインド文を入れない。
- 使用したメルカリ検索キーワードは納品時にチャットで一覧報告する。

招待コード併用：
- 招待コード「YRCNMN」：新規ユーザー向け（双方500P付与）。中古推し記事ではmercari-boxで表示。
- afid付きリンク：既存ユーザー向け（購入経由報酬）。
- 中古推し記事は両方併用が標準。

メルカリ使用時の開示文（記事冒頭）：
```html
<p style="font-size: 12px; color: #888888; margin: 0 0 16px 0; padding: 8px 12px; background: #f5f5f5; border-radius: 3px;">
※本記事には広告（Amazon・楽天アフィリエイト、メルカリアンバサダープログラム、メルカリ招待プログラム）が含まれます。
</p>
```

### Audible / Kindle Unlimited（成果報酬）
**汎用URLはトラッキングが落ちる。Associates Central / SiteStripe経由の正規URLを使う。**
確認済み正規Audibleリンク：
```
https://www.amazon.co.jp/hz/audible/arya/mlp?_encoding=UTF8&purchaseType=DISC_MTRIAL&SHOPPING_PORTAL_MODE=AUGMENTED&linkCode=ll2&tag=bubblegumkk0d-22&linkId=3737ac73bb482d05395fe7ed30018213&ref_=as_li_ss_tl
```
正規リンクには `linkCode=ll2` / `linkId=xxx` / `ref_=as_li_ss_tl` が含まれることを確認。

---

## アフィリエイト統一ボタンスタイル（推奨）

Amazon・楽天・メルカリの3並列ボタンを標準。CSSは記事の `<style>` 内に毎回含める。
ボタンは記事内で唯一のカラフル要素（グレー統一原則の例外。各ストアのコーポレートカラーを背景に使う）。

```css
.shop-buttons { display: flex; flex-wrap: wrap; gap: 8px; margin: 14px 0 22px 0; }
.shop-btn {
  flex: 1 1 0; min-width: 100px; display: inline-flex; align-items: center; justify-content: center;
  padding: 11px 12px; border: none; border-radius: 5px; background: #555555; color: #ffffff !important;
  font-size: 13.5px; font-weight: bold; text-decoration: none !important; text-align: center;
  transition: all 0.18s; box-shadow: 0 1px 2px rgba(0,0,0,0.12);
}
.shop-btn:hover { opacity: 0.88; transform: translateY(-1px); box-shadow: 0 3px 6px rgba(0,0,0,0.18); }
.shop-btn-amazon { background: #FF9900; }
.shop-btn-rakuten { background: #BF0000; }
.shop-btn-mercari { background: #FF0211; }
.shop-btn-label { font-size: 12px; font-weight: normal; color: #888; margin-right: 8px; flex-shrink: 0; display: flex; align-items: center; }
@media (max-width: 520px) {
  .shop-buttons { gap: 6px; }
  .shop-btn { padding: 10px 6px; font-size: 12px; min-width: 0; }
  .shop-btn-label { display: none; }
}
```

テンプレート：
```html
<div class="shop-buttons">
  <span class="shop-btn-label">PS5版</span>
  <a href="https://www.amazon.co.jp/s?k=【KW】&tag=bubblegumkk0d-22" class="shop-btn shop-btn-amazon" target="_blank" rel="sponsored noopener">Amazon</a>
  <a href="https://hb.afl.rakuten.co.jp/hgc/4ef94133.1f1592cd.4ef94134.ad13b72f/?pc=https%3A%2F%2Fsearch.rakuten.co.jp%2Fsearch%2Fmall%2F【URLエンコード】%2F&link_type=text&ut=eyJwYWdlIjoic2VhcmNoIiwidHlwZSI6InRleHQiLCJjb2wiOjF9" class="shop-btn shop-btn-rakuten" target="_blank" rel="sponsored noopener">楽天</a>
  <a href="https://jp.mercari.com/search?afid=6396715167&keyword=【URLエンコード】" class="shop-btn shop-btn-mercari" target="_blank" rel="sponsored noopener">メルカリ中古を探す</a>
</div>
```

### カード+ボタン構成の判断ルール（AIが文脈から自動判断）

| 状況 | 構成 | 判断基準 |
|---|---|---|
| 単体商品レビューで記事内に他の商品画像がない | asinカード + shop-buttons 3並列 | カードがサムネ兼商品ビジュアル |
| 単体商品レビューで記事内にfotolife画像が既に複数 | shop-buttons 3並列のみ | カードは冗長 |
| ランキング・複数商品紹介 | 各商品ごとに shop-buttons 3並列のみ | カードは縦に伸びすぎる |
| 中古推し記事 | shop-buttons を冒頭・中盤・末尾の3箇所 | メルカリ誘導を最大化 |
| 読書ブログ（書籍レビュー） | asinカード + shop-buttons（メルカリ） | 表紙画像が重要 |

迷う場合は「画像があるか」を最優先基準にする。

### 設置ルール
- 記事冒頭・中盤・末尾の3箇所が基本（長文記事）。ただし冒頭は文章で引き込んでから設置（いきなり広告を出さない）。
- 楽天は検索URL推奨（在庫切れに強い）。
- 同記事内で複数商品リンクOK。
- Audible/KU誘導は冒頭と末尾の2箇所（特に読書ブログ）。

---

## ゲームブログ CSS（毎回全文を出力に含める）

```css
h2.section-head {
  font-size: 118% !important; font-weight: bold !important;
  background-color: #555555 !important; color: #ffffff !important;
  padding: 10px 14px !important;
  border-top: 4px solid #aaaaaa !important; border-bottom: 4px solid #aaaaaa !important;
  box-shadow: inset 0px 1px 0px #ffffff, inset 0px -1px 0px #ffffff;
  margin-top: 48px !important; margin-bottom: 20px !important; border-left: none !important;
}
h3.sub-head {
  font-size: 108% !important; font-weight: bold !important;
  border-left: 5px solid #555555 !important; padding: 10px 0 10px 15px !important;
  margin-top: 36px !important; margin-bottom: 16px !important; background-color: #f9f9f9 !important;
}
.point-box { border: 1px solid #dddddd; padding: 15px 18px; margin: 20px 0; border-radius: 5px; background-color: #ffffff; box-shadow: 0 2px 5px rgba(0,0,0,0.05); }
.point-box .point-title { color: #333333; font-weight: bold; font-size: 15px; margin-bottom: 10px; }
.note-box { background: #fffde6; border: 1px solid #e8d44d; border-radius: 5px; padding: 13px 16px; margin: 16px 0; font-size: 13.5px; color: #444; line-height: 1.8; }
.note-box .note-label { font-weight: bold; color: #555; margin-right: 4px; }
.warn-box { background: #fff5f5; border: 1px solid #e0a0a0; border-radius: 5px; padding: 13px 16px; margin: 16px 0; font-size: 13.5px; color: #333; line-height: 1.8; }
.warn-box .warn-label { font-weight: bold; color: #c0392b; margin-right: 6px; }
figure { margin: 16px 0; }
figure img { max-width: 100%; height: auto; }
figcaption { font-size: 12px; color: #888; margin-top: 5px; }
ul { padding-left: 1.5em; }
li { margin-bottom: 6px; line-height: 1.8; }
p { margin-bottom: 1.4em; }
```

### ★テーブル CSS（汎用・スマホ対応）

```css
.data-table { width: 100%; border-collapse: collapse; font-size: 14px; margin: 16px 0; }
.data-table th { background: #555555; color: #333333; padding: 9px 12px; text-align: left; font-weight: bold; }
.data-table td { padding: 9px 12px; border-bottom: 1px solid #e0e0e0; line-height: 1.7; background: #fff; vertical-align: top; }
.data-table tr:nth-child(even) td { background: #f9f9f9; }
.data-table th[scope="row"] { background: #f5f5f5; color: #333333; font-weight: bold; white-space: nowrap; vertical-align: top; }
@media (max-width: 520px) {
  .data-table thead { display: none; }
  .data-table, .data-table tbody, .data-table tr, .data-table td { display: block; width: 100%; box-sizing: border-box; }
  .data-table tr { border: 1px solid #e0e0e0; border-radius: 6px; margin-bottom: 10px; overflow: hidden; }
  .data-table td { display: flex; align-items: flex-start; padding: 7px 10px; border-bottom: 1px solid #f0f0f0; font-size: 13px; }
  .data-table td:last-child { border-bottom: none; }
  .data-table td::before { content: attr(data-label); font-weight: bold; font-size: 11px; color: #666; background: #f5f5f5; min-width: 70px; max-width: 70px; flex-shrink: 0; padding: 2px 8px 2px 0; margin-right: 10px; border-right: 2px solid #dddddd; line-height: 1.6; }
  .data-table th[scope="row"] { display: block; width: 100%; box-sizing: border-box; padding: 6px 10px; font-size: 11px; color: #666; background: #f5f5f5; border-bottom: 1px solid #f0f0f0; }
  .data-table tr:nth-child(even) td { background: #ffffff; }
}
```

### ★テーブル構造の絶対ルール（崩れ防止・最重要）

過去にテーブル崩れ事故が複数回。原因は常に「ヘッダー列数とデータ行のセル数が不一致」。

ルール1：`<thead>` の `<th>` 数と各 `<tr>` のセル数を必ず一致させる。

ルール2：型は2種類。混ぜない。
- **型A（横ヘッダー・3列以上の比較表向き）**：theadに列見出し。各データ行はヘッダーと同数の `<td>`。全 `<td>` に `data-label="列見出し"`。1列目も実セルを持たせる（data-labelに逃がさない）。
  ```html
  <table class="data-table">
  <thead><tr><th>順番</th><th>色</th><th>点数</th></tr></thead>
  <tbody>
  <tr><td data-label="順番">1番目</td><td data-label="色">イエロー</td><td data-label="点数">2点</td></tr>
  </tbody>
  </table>
  ```
- **型B（2列縦型・項目名＋値の仕様表向き）**：theadを置かない。各行は `<th scope="row">`（項目名）＋ `<td>`（値）の2セル。data-labelは使わない。
  ```html
  <table class="data-table">
  <tbody>
  <tr><th scope="row" style="width: 30%;">価格</th><td>基本無料（課金あり）</td></tr>
  </tbody>
  </table>
  ```

ルール3：出力前にセルフチェック。
- 型A：thead の th 数 ＝ 各 tr の td 数か？ 全 td に data-label があるか？
- 型B：各 tr が「th[scope=row] 1個＋td 1個」の2セルか？ theadを置いていないか？

「項目名をdata-labelに入れて値だけtd」の1列構成はPCで空列を生むので絶対NG。

### テーブルth文字色（はてなブログ固有）
`color: #ffffff`（白）ははてなのデザインCSSに上書きされ消える。**全テーブルでthは `color: #333333`（黒）**。ゲーム・読書共通。

---

## 読書ブログ CSS（bubble-books.com / Dragon's Eggスタイル）

```css
.h4-block { font-size: 118%; font-weight: bold; background-color: #555555; color: #ffffff; padding: 10px 14px; border-top: 4px solid #aaaaaa; border-bottom: 4px solid #aaaaaa; box-shadow: inset 0px 1px 0px #ffffff, inset 0px -1px 0px #ffffff; margin-top: 56px; margin-bottom: 24px; }
.h5-block { font-size: 108%; font-weight: bold; border-left: 5px solid #555555; padding: 10px 0 10px 15px; margin-top: 48px; margin-bottom: 24px; background-color: #f9f9f9; }
.compare-table { width: 100%; border-collapse: collapse; margin: 20px 0; font-size: 14px; }
.compare-table th { background: #555555; color: #333333; padding: 9px 13px; text-align: left; font-weight: bold; }
.compare-table td { padding: 9px 13px; border-bottom: 1px solid #e0e0e0; vertical-align: top; line-height: 1.7; background: #ffffff; color: #222; }
.compare-table tr:nth-child(even) td { background: #f9f9f9; }
.supplement-box { border: 1px solid #dddddd; border-radius: 5px; padding: 15px 18px; margin: 20px 0; background: #f9f9f9; }
.supplement-box .sup-title { font-weight: bold; font-size: 14px; color: #555; margin-bottom: 8px; }
.recommend-box { border: 1px solid #dddddd; border-radius: 5px; padding: 15px 18px; margin: 24px 0; background: #ffffff; }
.recommend-box .rec-title { font-weight: bold; font-size: 14px; color: #333; margin-bottom: 10px; }
.cite-block { border-left: 4px solid #aaaaaa; padding: 12px 18px; margin: 16px 0; background: #fafafa; font-size: 14px; font-style: italic; line-height: 1.9; color: #333; }
.cite-block .cite-source { display: block; font-style: normal; font-size: 11px; color: #999; margin-top: 6px; }
@media (max-width: 600px) {
  .compare-table, .compare-table tbody, .compare-table thead, .compare-table tr, .compare-table th, .compare-table td { display: block; width: 100%; box-sizing: border-box; }
  .compare-table thead, .compare-table th { display: none; }
  .compare-table tr { border: 1px solid #dddddd; border-radius: 5px; margin-bottom: 12px; overflow: hidden; }
  .compare-table td[data-label] { display: flex; align-items: flex-start; padding: 8px 10px; border-bottom: 1px solid #f0f0f0; font-size: 13px; line-height: 1.7; }
  .compare-table td[data-label]:last-child { border-bottom: none; }
  .compare-table td[data-label]::before { content: attr(data-label); font-weight: bold; font-size: 11px; color: #666; background: #f5f5f5; min-width: 62px; max-width: 62px; flex-shrink: 0; padding: 2px 8px 2px 0; margin-right: 10px; border-right: 2px solid #dddddd; }
}
```
読書ブログのcompare-tableも上記「テーブル構造の絶対ルール」を同様に適用。読書ブログのブレークポイントは600pxがデフォルト。

---

## ボックス使い分け（読者体験を高める場合のみ。惰性で全部入れない）

| クラス | 用途 | 背景色 |
|---|---|---|
| k-conclusion-box | 先に結論（※デフォルト廃止。結論を急ぐ実用記事のみ） | #f0f7ff |
| note-box | 補足・情報 | #fffde6 |
| warn-box | 注意・警告 | #fff5f5 |
| good-box | 良い点・おすすめ | #f0f7f4 |
| bad-box | 気になる点・向かない | #fdf3f0 |
| verdict-box | 総合評価・星評価 | #fafafa |
| story-box | ゲームあらすじ・体験談 | #f7f9fc |
| supplement-box | 補足（読書ブログ） | #f9f9f9 |
| recommend-box | 推薦（読書ブログ） | #ffffff |
| cite-block | 引用 | #fafafa |
| mercari-box | メルカリ招待コード | #fff8f3 |

各ボックスCSS：
```css
.k-conclusion-box { background: #f0f7ff; border: 2px solid #4a90b8; border-radius: 6px; padding: 18px 20px; margin: 20px 0 28px 0; }
.k-conclusion-box .k-conclusion-title { font-weight: bold; font-size: 16px; color: #2277aa; margin-bottom: 12px; border-bottom: 1px solid #c0d8e8; padding-bottom: 8px; }
.good-box { background: #f0f7f4; border-left: 4px solid #27ae60; padding: 14px 18px; margin: 16px 0; border-radius: 0 5px 5px 0; }
.good-box .good-title { font-weight: bold; color: #27ae60; font-size: 14px; margin-bottom: 8px; }
.bad-box { background: #fdf3f0; border-left: 4px solid #c0392b; padding: 14px 18px; margin: 16px 0; border-radius: 0 5px 5px 0; }
.bad-box .bad-title { font-weight: bold; color: #c0392b; font-size: 14px; margin-bottom: 8px; }
.verdict-box { border: 2px solid #555555; background: #fafafa; padding: 16px 20px; margin: 24px 0; border-radius: 5px; }
.verdict-box .verdict-title { font-weight: bold; font-size: 16px; color: #333; margin-bottom: 10px; }
.star-rating { color: #e8a800; font-size: 18px; letter-spacing: 2px; }
.story-box { background: #f7f9fc; border-left: 4px solid #555555; padding: 14px 18px; margin: 20px 0; border-radius: 0 5px 5px 0; }
.story-box .story-title { font-weight: bold; font-size: 14px; color: #444; margin-bottom: 8px; }
.mercari-box { background: #fff8f3; border: 1px solid #f0c8a0; border-radius: 6px; padding: 16px 18px; margin: 20px 0; }
.mercari-box .mercari-title { font-weight: bold; font-size: 15px; color: #b8501a; margin-bottom: 10px; }
.mercari-code { display: inline-block; background: #ffffff; border: 2px dashed #b8501a; border-radius: 4px; padding: 6px 14px; margin: 4px 0; font-family: 'Courier New', monospace; font-size: 16px; font-weight: bold; color: #b8501a; letter-spacing: 2px; }
.faq-list dt { font-weight: bold; background: #f5f5f5; padding: 10px 14px; margin-top: 12px; border-left: 4px solid #555555; font-size: 14.5px; }
.faq-list dd { padding: 10px 14px 14px 18px; margin: 0; font-size: 14px; line-height: 1.85; border-bottom: 1px solid #eee; }
```

---

## カラーパレット（基本グレー統一 + アクセント）

| 用途 | カラー |
|---|---|
| 見出し背景 | #555555 |
| 見出しボーダー | #aaaaaa |
| テーブルヘッダー | #555555（文字色 #333333 必須） |
| テーブルボーダー | #e0e0e0 |
| 背景（偶数行） | #f9f9f9 |
| 背景（カード） | #fafafa |
| テキスト本文 | #222222 / #333333 |
| テキスト薄め | #666666 / #888888 |
| 赤（値上げ・警告） | #c0392b |
| 緑（OK・安値） | #27ae60 |
| 青（参考リンク・結論） | #2277aa / #4a90b8 |
| Amazon | #FF9900（ボタン背景のみ） |
| 楽天 | #BF0000（ボタン背景のみ） |
| メルカリ | #FF0211（ボタン背景のみ） |

ストア識別カラーはshop-btnの背景色のみで使う例外。他は全てグレー統一を維持。

---

## Schema.org構造化データ（型が明確に当てはまる場合のみ）

- 商品レビュー → Review + Product
- ゲームレビュー → Review + VideoGame
- 手順解説 → HowTo
- Q&Aあり → FAQPage（実際にFAQを置いたときのみ）
- 価格・在庫 → Product の offers

中身のないスキーマ（実体のないFAQ等）は入れない。
スクリプト位置：記事冒頭の `<p>` タグ内で `<script type="application/ld+json">`。

---

## スマホ最適化

- 型Aテーブルは全セルに `data-label`。型Bは th[scope=row] で対応。
- ブレークポイント：ゲームブログ520px、読書ブログ600pxがデフォルト。
- グリッド使用時は子要素に `min-width: 0`。
- 英文を含むブロックに `overflow-wrap: break-word; word-break: break-word;`。
- 画像は常に `max-width: 100%; height: auto;`。

---

## SEO・アフィリエイト知識

- 技術的SEOは「やりすぎない」。最優先は読者の滞在・読了・満足。
- Amazon：クリック後24時間以内にカート投入した全商品が報酬対象（品切れページでも有効）。同記事内で複数リンクOK。Audible/KU無料体験登録は1件500〜1,500円。
- 楽天：クリック後24時間・注文確定が必要。検索ページ誘導が在庫切れに強い。
- メルカリ：招待コードYRCNMNは何回でも使用可。中古ゲーム・古本が活発で過去作の在庫豊富。
- 重複コンテンツ：同じ検索クエリを狙う本文重複はNG。季節性の告知セクションの複数記事末尾追加はOK。横展開は2〜3文ティーザー＋内部リンク。
- 引用（著作権法32条）：明瞭区別（blockquote/cite-block）・出典明示・主従関係（地の文が主）・正当な範囲。

### Search Console運用
- 新規公開時：URL検査→インデックス登録をリクエスト。
- 大幅修正・タイトル変更時：必ず再申請。
- 順位確認は2〜4週間待つ。
- 「Page Title」「og:title」「post description」の3欄は必ず埋める（空欄だとブログタイトルで上書きされる）。

---

## 出力形式

- 必ずHTMLファイルとして出力（styleブロック付き完全版）。CSSは記事冒頭の `<style>` 内にまとめる。
- はてなに貼り付けられる形（DOCTYPE・html・bodyタグ不要）。
- ファイル名は内容を反映したスネークケース（例：pragmata_review.html）。
- Schema.org構造化データは適切な型がある場合のみ記事冒頭に配置。

## 完成時のレスポンス構成（必須）

1. ファイル作成完了の確認（SendUserFileで提示）
2. 主な変更点・改善点の説明（特にどんなフックで引き込む設計にしたか）
3. タイトル案を3〜5個提示（情緒型・SEO型・SNS型などバリエーション）
4. Page Title / og:title / post description の提案
5. 使用したメルカリ検索キーワードの一覧報告（メルカリリンクを入れた場合）
6. Search Console再申請のリマインド（修正記事の場合）

---

## 作業メモ

- 公開済み記事のURLを直接取得するには、環境のネットワークポリシー（Network access）で `babblegum.hatenablog.com` 等を許可ホストに追加する必要がある。設定変更は新規セッションから反映。
- リライト前に元記事のHTMLを `<記事名>_original_restore.html` としてバックアップしておくと、貼り付けミス時に復元できる。
- 競合調査・事実確認・リンクチェック等のトークン消費が大きい作業はSonnet/Haikuのサブエージェントに委任し、構成設計・執筆・最終品質チェックはメインモデルが担当すると効率的。
