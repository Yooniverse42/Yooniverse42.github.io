---
title: "요소를 숨겨보자(feat. display & visibility)"
excerpt: "display와 visibility에 대해 알아보자."

categories:
  - CSS
tags:
  - [HTML, CSS, display, none, visibility, hidden]

permalink: /css/display-visibility/

toc: true
toc_sticky: true

date: 2024-05-18
last_modified_at: 2024-05-18
---

# 😶‍🌫️ 요소를 숨겨보자

브라우저에서 어떠한 요소를 숨기고 싶거나 JavaScript를 이용하여 숨겼다 나타났다 하는 이벤트를 주고 싶을 때 CSS로 작성하여 어떠한 요소를 숨길 수 있는데 이때 사용 가능한 것들이 두 가지가 있다.

- `display : none;`
- `visibility: hidden;`

```html
<body>
  <h2>Display</h2>

  <div>
    <div>one</div>
    <div class="hidden1">two</div>
    <div>three</div>
  </div>

  <h2>Visibility</h2>

  <div>
    <div>one</div>
    <div class="hidden2">two</div>
    <div>three</div>
  </div>
</body>
```

![](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories02-css/0618-display-visibility.png?raw=true)

`display : none;`을 주면 완전히 사라지지만,  
`visibility: hidden;`는 브라우저 상에서는 보이지 않지만 자리를 차지하고 있다는 것을 알 수 있다.
