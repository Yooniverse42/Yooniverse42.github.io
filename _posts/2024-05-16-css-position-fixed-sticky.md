---
title: "position에서 fixed와 sticky 차이"
excerpt: "position 속성에서 fixed와 sticky의 차이에 대해 알아보자."

categories:
  - CSS
tags:
  - [HTML, CSS, position, fixed, sticky]

permalink: /css/position-fixed-sticky/

toc: true
toc_sticky: true

date: 2024-05-16
last_modified_at: 2024-05-16
---

# 🏷️ fixed VS sticky

## fixed 🔩

- 눈에 보이는 뷰포트를 기준으로 top, right, bottom, left 값에 따라 최종 위치를 지정한다.
- 스크롤을 하더라도 계속 따라온다.
- 아래에 어떤 내용이 있더라도 가리면서 따라온다.
- 예) 팝업창, 문의하기 버튼, 네비게이션 바, 광고창 등

![fixed.png](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories02-css/001-02-fixed.gif?raw=true)

<br>

## sticky 🔖

- Normal Flow를 따르고, 가장 가까운 스크롤이 되는 부모를 기준으로 top, right, bottom, left 값에 따라 최종 위치를 지정한다. (기본적으로 스크롤이 되는 상황에서만 효과가 나타남)
- Normal Flow를 따르기 때문에 처음에는 자신의 영역을 차지하고 있다.
- sticky라는 이름을 기억하면 이해하기가 쉽다. 스크롤을 내리다가 특정 시점부터 마치 fixed처럼 동작한다.

![sticky.png](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories02-css/001-03-sticky.gif?raw=true)

참고로 `fixed`는 top 50px, right 50px를 주었고 `sticky`는 top 50px만 주었다.
![fixed+sticky](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories02-css/001-01-fixed-sticky.png?raw=true)
