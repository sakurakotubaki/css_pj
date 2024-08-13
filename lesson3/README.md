## 赤いボタンの作り方
botクラスのbuttonタグを作成する。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <button class="btn">button</button>
    <script>
        const btn = document.querySelector('.btn');
        btn.addEventListener('click', () => {
            alert('Hello');
        });
    </script>
</body>
</html>
```

.btnクラスを指定したCSSを作成する。
```css
* {
    margin: 0;
}

.btn {
    padding: 10px 20px;
    background-color: #f00;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
```