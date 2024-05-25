---
title: "HTML Character Entities에 대해 알아보자"
excerpt: "HTML 특수문자를 표현하는 코드표 정리 "

categories:
  - HTML
tags:
  - [HTML, CSS, entities]

permalink: /html/character-entities/

toc: true
toc_sticky: true

date: 2024-05-03
last_modified_at: 2024-05-03
---

# 🖨️ HTML Character Entities

콘텐츠에 `<...>` 와 같은 꺽쇠를 나타내고 싶은데 자꾸 태그로 인식하거나 공백이 여러번 나오게 하고 싶은데 하나의 공백으로 인식할 때!  
google에 "html character entities"라고 검색을 하면 특수문자들이 어떻게 치환되는지 정리된 표가 나온다.  
([W3Schools](https://www.w3schools.com/html/html_entities.asp)에도 잘 정리되어 있으니 참고하면 될 듯!)  
개발자들도 모두 기억하고 있는 것은 아니라고 하니, 자주 쓰는 것만 기억하고 궁금할 땐 구글링 💻 그리고 euro sign 같은 경우 복사하여 사용해도 되지만 웬만하면 entities name, number 사용을 권장한다.
![doctype02](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/character-entities-01.png)

출처 : W3Schools

<br>

자주 사용하는 특수문자들에 대해 알아보자.

## 1) 꺽쇠 나타내는 법

`<` 대신에 `&lt;` 쓰기 (Less Than)  
`>` 대신에 `&gt;` 쓰기 (Greater Than)

```html
<body>
  <h1>안녕하세요!</h1>
  <p>&lt;꺽쇠는 이렇게 만들면 됩니당&gt;</p>
</body>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/character-entities-02.png)

## 2) 공백 나타내는 법

**공백**을 나타내기 위해 스페이스바를 여러번 눌리는 대신에 `&nbsp;` 쓰기 (Not Breaking SPace)

- 아무리 스페이스바를 눌려도 하나의 공백으로 인식하므로 `&nbsp;`를 사용하면 원하는 만큼의 공백을 얻을 수 있다.

```html
<body>
  <h1>안녕하세요!</h1>
  <p>공 백</p>
  <p>공 백</p>
  <p>공&nbsp;백</p>
  <p>공&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;백</p>
</body>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/character-entities-03.png)
