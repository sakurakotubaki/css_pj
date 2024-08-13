# ボタンをデザインする
今時ボタンは、MUIとかChakra UIを使えば最初からデザインされているものを使うだけなので、デザインを意識する必要がなかったりします。しかし、自作するとなると自分で設定が必要です。

HTML:
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
  <a class="btn" href="#">ボタンだよ</a>
  <a class="btn" href="#">ボタンだよボタンだよボタンだよボタンだよボタンだよボタンだよ</a>
</body>
</html>
```

CSS:
```css
.btn {
    display: inline-block;
    width: 300px;
    max-width: 100%;
    padding: 20px 10px;
    background-color: #e25c00;
    border: 2px solid transparent;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 16);
    color: #fff;
    font-size: 1.125rem,;
    text-align: center;
    text-decoration: none;
    transform: 25s;
}

.btn:focus,
.btn:hover {
    background-color: #fff;
    border-color: currentColor;
    color: #e25c00;
}
```

割と綺麗なボタンを作れたと思ったが、テキストが多いと改行されてしまう。この場合は、サイズを指定しない方が良かったりする。ボタン内で改行したくないときは、`mix-width`を使うと良い

```css
.btn {
    display: inline-block;
    min-width: 300px; /** min-widthに修正*/
    max-width: 100%;
    padding: 20px 10px;
    background-color: #e25c00;
    border: 2px solid transparent;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 16);
    color: #fff;
    font-size: 1.125rem,;
    text-align: center;
    text-decoration: none;
    transform: 25s;
}
```

もし横幅に最大値を設けたい場合は、`max-width`を併用する。
```css
max-width: 100%;
```