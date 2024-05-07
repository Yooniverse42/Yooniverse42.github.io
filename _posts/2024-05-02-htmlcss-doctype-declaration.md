---
title: "!DOCTYPE 선언하는 이유"
excerpt: "HTML 작성시 &lt;!DOCTYPE html&gt;을 선언하는 이유에 대해 알아보자"

categories:
  -HTML/CSS
tags:
  - [HTML, CSS, DOCTYPE]

permalink: /htmlcss/doctype-declaration/

toc: true
toc_sticky: true

date: 2024-05-02
last_modified_at: 2024-05-02
---

# 📌 HTML 작성시 &lt;!DOCTYPE html&gt;을 선언하는 이유

> html 최신 문서라는 것을 알려주기 위함이다.
`<!DOCTYPE html>`을 선언하지 않는다면 브라우저가 현재 읽고 있는 html의 버전을 알 수 없어 html의 디자인 같은 것들을 마음대로 렌더링하게 된다.

### `<!DOCTYPE html>` 선언했을 때 👇🏻
```
<!DOCTYPE html>
<html>
<head>
    <title>Document</title>
    <style>
        body{
            border: 4px solid blue;
        }
    </style>
</head>
<body>
    <h1>안녕하세요!</h1>
</body>
</html>
```

![doctype01](https://Yooniverse42.github.io/assets/images/posts_img/categories01-htmlcss/001-01-doctype.png)

<br>

### `<!DOCTYPE html>` 선언하지 않았을 때 👇🏻
```
<html>
<head>
    <title>Document</title>
    <style>
        body{
            border: 4px solid blue;
        }
    </style>
</head>
<body>
    <h1>안녕하세요!</h1>
</body>
</html>
```

![doctype02](https://Yooniverse42.github.io/assets/images/posts_img/categories01-htmlcss/001-02-doctype.png)