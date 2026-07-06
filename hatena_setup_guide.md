# はてな貼り付け手順（人気記事＋広告CLS対策）2026-07-06

方針：**CSSは広告に一切触らない**（広告が縮んだ原因だったため）。広告の高さ予約は広告HTML側にインラインで書き、埋まらない枠はJSが畳む。CSSは人気記事の見た目だけ担当。

いま各欄に入っているもの（確認済み・送り直し不要）：
- 設定 → 詳細設定 → **HTML in entry header（記事上）**：広告の開示文 → 触らない
- 設定 → 詳細設定 → **HTML in entry footer（記事下）**：記事内広告スクリプト一式 → ここを差し替え
- デザイン → **デザインCSS**：貼り直す
- デザイン → **タイトル下**：カテゴリナビ＋上部広告

---

## 必須ステップ（この2つで完成）

### STEP 1｜デザインCSS を貼り替え

場所：デザイン → カスタマイズ（スパナ🔧）→ **デザインCSS**。
中身を全選択して消し、`hatena_design_css_safe.css` の中身を全部貼る。
（変更点は「人気記事を3列にした」だけ。広告のルールは足していないので、広告は前と同じ挙動のまま。）

### STEP 2｜HTML in entry footer を差し替え

場所：設定 → 詳細設定 → **HTML in entry footer**。
今入っている広告スクリプト一式を全部消して、`hatena_entry_footer.html` の中身を全部貼る。
これで「人気記事（3枚）」＋「記事内広告（高さ予約つき）」＋「下部広告」＋「空枠を畳むJS」が一括で入る。

→ この2つで、人気記事の表示と、記事内・下部広告のCLS対策が完了。

---

## 任意ステップ（上部広告のCLSも減らしたいとき）

### STEP 3｜タイトル下の上部広告を div で挟む

場所：デザイン → カスタマイズ → **タイトル下**。
カテゴリナビはそのまま。その下の「上部広告」の `<ins>` を、下記のように `<div class="ad-wrapper-top" ...>` で挟むだけ。

```html
<!-- 上部広告 -->
<div class="ad-wrapper-top" style="min-height:100px;text-align:center;overflow:hidden;max-width:100%;margin:10px 0;">
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-2203567155161909"
     data-ad-slot="8957021599"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
</div>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
```

上部広告は自動サイズなので予約は控えめの100px。ズレは減るがゼロにはならない。空白が気になるなら `min-height:100px` を下げる、CLSをもっと減らしたいなら上げる（トレードオフ）。

---

## 高さ予約の数字（あとで自分で調整できる）

`hatena_entry_footer.html` の中の `min-height` がその枠の予約高さ。広告が小さく出て空白が気になったら数字を下げる、逆にズレが気になったら上げる。

- 記事内広告：`min-height:250px`
- 下部広告：`min-height:280px`
- 上部広告（STEP3）：`min-height:100px`

畳みJSがあるので「広告が来なかった枠」は自動で0に潰れる。空白が残るのは「広告は来たけど予約より小さいとき」だけ。

---

## 貼ったあと

- 記事を1本開いて、下に **🔥人気記事**（3枚・左端に赤い「自作」バッジ）が出るか確認。
- スマホでも3枚が横に並んでるか、広告の位置で本文がガクッと落ちないか。
- サーチコンソール → Core Web Vitals → 「検証を開始」。数値反映は2〜4週間。
- AdSenseの自動広告（勝手に入るやつ）は別。数値が下がりきらなければ、AdSense管理画面 → 広告 → 自動広告 で上部大型・アンカーをオフにするのが効く。

## 人気記事の差し替え方

`hatena_entry_footer.html` の `<a class="recommended-card">` 3ブロックを入れ替えるだけ（URL・画像URL・テキストの3か所）。
