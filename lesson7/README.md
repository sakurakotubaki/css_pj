# メディアを使ってみる
左側に画像、右側にテキストを配置するモジュールを一般的に「メディア」と呼びます。
テキストはタイトルと説明文で構成され、メディアクエリ適用時は、画像とテキストを縦並びにします。

こんな感じで、画像素材を用意してください。index.html, style.css, imageフォルダを作成。

[figure](https://developer.mozilla.org/ja/docs/Web/HTML/Element/figure)　タグについて知りたい人は、
こちらをみてください。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="media">
    <figure class="media__img-wrapper">
      <img src="./image/android.jpg" alt="android image" class="media__img">
    </figure>
    <div class="media__body">
      <h3 class="media__title">Androidユーザーが増えた背景</h3>
      <p>
        Androidユーザーが増えた背景には、価格の安さと性能の向上があります。Androidは、
        スマートフォンのOSの中でも比較的安価で購入できるため、多くの人が利用しています。
        また、AndroidはGoogleが提供しているため、Googleのサービスとの親和性が高いことも理由の一つです。
        日本国内でもiPhoneのシェアが高いですが、半分の価格で買えて、性能も十分なAndroidスマートフォンが
        近年多く売れています。Pixelシリーズなど、Googleが提供しているスマートフォンが人気です。
      </p>
    </div>
    <!-- /.media_body --> 
  </div>
  <!-- /.media -->
</body>
</html>
```

CSSは、画面サイズが、max-width: 768pxに設定して、それ以下だと、画像と
テキストを縦向きに並べます。

```css
.media {
    display: flex;
    align-items: center;
}
.media__img-wrapper {
    flex: 0 1 27.58333%;
    margin-right: 3.33333%;
}
.media__img {
    width: 100%;
}
.media__body {
    flex: 1;
}
/* 最後の要素の余白をリセットする */
.media__body > *:last-child {
    margin-bottom: 0;
}
.media__title {
    margin-bottom: 10px;
    font-size: 1.125rem;
    font-weight: bold;
}
/* メディアクエリ適用時 */
@media (max-width: 768px) {
    .media {
        display: block;
    }
    .media__img-wrapper {
        margin-right: 0;
        margin-bottom: 20px;
    }
}
```