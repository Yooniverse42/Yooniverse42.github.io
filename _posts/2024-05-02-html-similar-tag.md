---
title: "HTML 다른 태그지만, 사용자에게 동일하게 보이는 태그들"
excerpt: "똑같이 보이는데 마음대로 사용하면 안되나요? 네 안돼요."

categories:
  - HTML
tags:
  - [HTML, CSS, s, del, b, strong, i, em]

permalink: /html/similar-tag/

toc: true
toc_sticky: true

date: 2024-05-02
last_modified_at: 2024-05-02
---

# `<s>` & `<del>`, `<b>` & `<strong>`, `<i>` & `<em>`의 차이에 대해 알아보자.

> 태그 생김새 뿐만 아니라 의미도 다르지만, 사용자에게 비슷하게 보이는 태그들이 있다. 이러한 태그들을 다 외울 필요도 없고, 굳이 나눠서 쓰지 않아도 된다고 많이들 애기하지만, 똑같이 보인다고 해서 아무렇게나 쓰는 것 보단 의미를 알고 쓰는 것이 좋을 듯 하다.

<br/>

## `<s>` & `<del>` 의 차이🧐

두 태그 모두 문자 중간에 줄이 그어지게 나온다.

```html
<body>
  <p>안녕하세요! <s>감사</s>합니다!</p>
  <p>안녕하세요! <del>감사</del>합니다!</p>
</body>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/similar-tag-01.png)

`<s>` : 문서의 내용이 틀렸을 때

`<del>` : 예전 버전에는 있었으나, 최신 버전에는 삭제된 내용

## `<b>` & `<strong>` 의 차이🧐

```html
<body>
  <p>안녕하세요! <b>감사</b>합니다!</p>
  <p>안녕하세요! <strong>감사</strong>합니다!</p>
</body>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/similar-tag-02.png)

`<b>` : 단순히 특정 단어, 문장을 굵게하고 싶을 때

`<strong>` : 문서에서 중요도가 높은 단어 (앞, 뒤 문장에 비해 제일 중요한 단어 또는 문장을 강요하고 싶을 때)

**스크린리더를 읽을 때 차이가 난다.**
`<b>` 사용 시 : 감사합니다.(다른 단어, 문장들과 똑같이 읽어짐)
`<strong>` 사용 시 : 감!사! 합니다.(”감사”라는 단어를 강요하면서 읽어짐)

## `<i>` & `<em>` 의 차이🧐

```html
<body>
  <p>안녕하세요! <i>감사</i>합니다!</p>
  <p>안녕하세요! <em>감사</em>합니다!</p>
</body>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/similar-tag-03.png)

`<i>` : 어떤 이유로 구분해야 할 때

`<em>` : 단어, 문장을 강조하고 싶을 때 (스크린 리더 - 강조하며 읽어짐)

> 이 외에도 비슷하게 보이는 태그들이 많다. 하지만 프론트엔드 개발자로서 보이는 것뿐만 아니라 누구든 이용 가능한 웹페이지를 만드는 것 즉, 웹접근성을 중요시해야 한다고 생각한다. 그러므로 웹표준과 웹접근성을 준수하며 프로그래밍하도록 노력해 보자.🫡
