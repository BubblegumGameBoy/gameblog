# はてな貼り付け用スニペット（人気記事 ＋ 広告CLS対策）2026-07-06

貼る場所は3か所。上から順に。

---

## ① デザインCSS に貼る（末尾に追記）

場所：デザイン → カスタマイズ → デザインCSS の一番下。

- 前半の `.recommended-*` は、いま入っている「おすすめ」用CSSの置き換え（3列固定・スマホ4枚目表示ルールを撤去）。
- 後半の広告CLS対策は新規。2026-07-01で全撤去した高さ予約を、今度は「対象を絞って＋来なかった枠だけ畳む」形で入れ直したもの。`.adsbygoogle` 全体には付けないのでアンカー広告は崩れない。

```css
/* ============================================================
   ★人気記事（旧おすすめ）＋ 広告CLS対策 ― 2026-07-06 更新
   既存の .recommended-* はこの内容で置き換え。広告CLS対策は新規追記。
   （2026-07-01で min-height を全撤去したが、CLSが悪化したため
    対象を絞って予約し直す。埋まらない枠だけJSで畳む。）
   ============================================================ */

/* ===== 人気記事カード（PC3列／スマホも3列詰め） ===== */
.recommended-articles { margin: 40px 0; padding: 24px 20px; background: linear-gradient(135deg, #f8fafc, #eef2f7); border-radius: 16px; }
.recommended-title { font-size: 1.1rem; font-weight: 700; color: #2c4d7a; margin: 0 0 20px; text-align: center; }
.recommended-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
.recommended-card { background: #fff; border-radius: 12px; overflow: hidden; text-decoration: none; color: #333; box-shadow: 0 2px 6px rgba(0,0,0,0.06); transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; min-width: 0; }
.recommended-card:hover { transform: translateY(-3px); box-shadow: 0 6px 14px rgba(0,0,0,0.1); color: #2c4d7a; }
.recommended-thumb { display: block; width: 100%; height: 100px; background-size: cover; background-position: center; background-color: #dfe6ee; }
.recommended-text { padding: 10px 12px; font-size: 0.82rem; line-height: 1.5; flex: 1; font-weight: 500; word-break: break-word; }
.rec-badge { display: inline-block; background: #e60012; color: #fff; font-size: 0.62rem; font-weight: 700; padding: 1px 6px; border-radius: 4px; margin-right: 5px; vertical-align: middle; }
@media (max-width: 600px) {
  .recommended-grid { gap: 8px; }
  .recommended-thumb { height: 66px; }
  .recommended-text { font-size: 0.72rem; padding: 7px 8px; line-height: 1.4; }
}

/* ===== 広告CLS対策：枠の高さを予約し、来なかった枠だけ畳む ===== */
/* min-height は下の3クラスだけに付ける。.adsbygoogle 全体には付けない（アンカー広告が崩れるため） */
.ad-wrapper-top { min-height: 100px; overflow: hidden; max-width: 100%; text-align: center; margin: 10px 0; }
.adsense-in-article { min-height: 250px; overflow: hidden; max-width: 100%; margin: 30px 0; text-align: center; }
.ad-wrapper-bottom { min-height: 300px; overflow: hidden; max-width: 100%; }
@media (max-width: 600px) { .adsense-in-article { min-height: 280px; } }
/* 来なかった枠は予約を解除して空白を残さない（!important でインライン高さに勝たせる） */
.ad-wrapper-top.is-empty,
.adsense-in-article.is-empty,
.ad-wrapper-bottom.is-empty { min-height: 0 !important; height: 0 !important; margin: 0 !important; padding: 0 !important; overflow: hidden !important; }
```

---

## ② 記事下 に貼る（人気記事の本体HTML）

場所：デザイン → カスタマイズ → 記事 → 記事下（HTML編集モードで貼る）。

```html
<div class="recommended-articles">
  <p class="recommended-title">🔥 人気記事</p>
  <div class="recommended-grid">
    <a href="https://babblegum.hatenablog.com/entry/2026/06/12/144156" class="recommended-card">
      <span class="recommended-thumb" style="background-image:url('https://cdn-ak.f.st-hatena.com/images/fotolife/B/Babblegum/20260629/20260629164335.png');"></span>
      <span class="recommended-text"><span class="rec-badge">自作</span>スペースキー連打ゲーム｜ボス撃破で自動化</span>
    </a>
    <a href="https://babblegum.hatenablog.com/entry/2025/12/04/111657" class="recommended-card">
      <span class="recommended-thumb" style="background-image:url('https://cdn-ak.f.st-hatena.com/images/fotolife/B/Babblegum/20251203/20251203180053.png');"></span>
      <span class="recommended-text">【2026年版】個人的神ゲーランキングTOP27</span>
    </a>
    <a href="https://babblegum.hatenablog.com/entry/2026/03/16/153001" class="recommended-card">
      <span class="recommended-thumb" style="background-image:url('https://cdn-ak.f.st-hatena.com/images/fotolife/B/Babblegum/20260314/20260314193445.jpg');"></span>
      <span class="recommended-text">【Switch2】2026年おすすめゲームランキング22選</span>
    </a>
  </div>
</div>
```

---

## ③ フッター を差し替える（広告CLS対策版）

場所：設定 → 詳細設定 → フッタ（または デザイン → フッター）。
いま入っている広告3ブロック（記事内挿入 / 下部Multiplex / 空枠非表示）を、まるごと下記に差し替える。

変更点：
- 記事内広告の挿入時に `min-height:250px` をインラインで持たせ、広告が「後から膨らんで本文を押し下げる」ズレを止める。
- 空枠の非表示を `display:none` から `.is-empty` クラス付与に変更（CSS側で高さ予約を解除）。判定は `unfilled` か「filled だけど極端に低い」ときのみ。読み込み中の枠を誤爆で畳まないようにした。
- 畳むタイミングを 1.2s / 3s / 8s に前倒し（空枠の残り時間を短縮）。

```html
<!-- ▼ 記事内広告の自動挿入（高さ予約つき・CLS対策版） -->
<script>
document.addEventListener('DOMContentLoaded', function() {
  if (!document.querySelector('.entry-content')) return;
  var headings = document.querySelectorAll('.entry-content h2, .entry-content h3, .entry-content h4, .entry-content .h4-block, .entry-content .h5-block');
  if (headings.length < 2) return;
  var positions = (headings.length >= 5) ? [1, 4] : [1];
  var adHTML =
    '<div class="adsense-in-article" style="min-height:250px;margin:30px 0;text-align:center;overflow:hidden;max-width:100%;">' +
      '<ins class="adsbygoogle"' +
        ' style="display:block;text-align:center;"' +
        ' data-ad-layout="in-article"' +
        ' data-ad-format="fluid"' +
        ' data-ad-client="ca-pub-2203567155161909"' +
        ' data-ad-slot="1845067348"></ins>' +
    '</div>';
  positions.forEach(function(pos) {
    if (headings[pos]) {
      headings[pos].insertAdjacentHTML('beforebegin', adHTML);
      (adsbygoogle = window.adsbygoogle || []).push({});
    }
  });
});
</script>

<!-- ▼ 下部広告（Multiplex）※高さ予約は .ad-wrapper-bottom のCSSで担保 -->
<div class="ad-wrapper-bottom" style="margin: 0 0 90px 0; padding: 0;">
  <ins class="adsbygoogle" style="display:block" data-ad-format="autorelaxed" data-ad-client="ca-pub-2203567155161909" data-ad-slot="5529974521"></ins>
</div>
<script> (adsbygoogle = window.adsbygoogle || []).push({}); </script>

<!-- ▼ 来なかった広告枠だけ畳む（埋まった枠はそのまま＝CLSを出さない） -->
<script>
(function() {
  function collapseEmptyAds() {
    document.querySelectorAll('.adsbygoogle').forEach(function(ad) {
      var wrapper = ad.closest('.ad-wrapper-top, .ad-wrapper-bottom, .adsense-in-article');
      if (!wrapper || wrapper.classList.contains('is-empty')) return;
      var status = ad.getAttribute('data-ad-status');
      if (status === 'unfilled' || (status === 'filled' && ad.offsetHeight < 50)) {
        wrapper.classList.add('is-empty');
      }
    });
  }
  window.addEventListener('load', function() {
    setTimeout(collapseEmptyAds, 1200);
    setTimeout(collapseEmptyAds, 3000);
    setTimeout(collapseEmptyAds, 8000);
  });
})();
</script>
```

---

## ④ タイトル下 の上部広告に高さ予約を付ける（任意・CLSに効く）

場所：デザイン → カスタマイズ → タイトル下（ヘッダーのカテゴリナビが入っている欄）。
その中の「上部広告」の `<ins>` を `<div class="ad-wrapper-top">` で挟むだけ。ナビや Font Awesome はそのまま。

```html
<!-- 上部広告 -->
<div class="ad-wrapper-top">
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

注意：この上部広告は `data-ad-format="auto"`（自動サイズ）なので、完璧な高さ予約はできない。控えめに 100px 予約して、来なければ畳む形。ズレは減るがゼロにはならない。ページ最上部なので予約を大きくすると空白が目立つため、あえて控えめにしている（`.ad-wrapper-top` の min-height を増やせば予約は増えるが、空きが出やすくなるトレードオフ）。

## 注意：AdSense 自動広告（別枠）について

上の④は「手貼りの上部広告」の話。これとは別に、AdSense の自動広告がページ上部やアンカー位置に勝手に差し込むことがあり、それは CSS/フッターでは制御できない。もし数値が改善しきらない場合は、AdSense管理画面 → 広告 → 自動広告 で「ページ上部の大きな広告」やアンカー系をオフにするのが効く。まずは①〜④を入れて、2〜4週間サーチコンソールの推移を見てから判断で。

## 反映後の運用メモ

- 貼ったら、サーチコンソール → ページエクスペリエンス／Core Web Vitals で「検証を開始」を押す（再評価をリクエスト）。
- CLSの数値が実測に反映されるまで2〜4週間かかる。すぐには動かない。
- 人気記事の並べ替え・差し替えは、②のHTMLの `<a>` 3ブロックを入れ替えるだけ。
