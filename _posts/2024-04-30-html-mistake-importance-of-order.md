---
title: "head : 순서의 중요성(feat. link)"
excerpt: "&lt;link&gt;에서 실수한 썰.."

categories:
  - HTML
tags:
  - [HTML, CSS, head, link]

permalink: /html/mistake-importance-of-order/

toc: true
toc_sticky: true

date: 2024-04-30
last_modified_at: 2024-04-30
---

# 📌 순서의 중요성

![](https://velog.velcdn.com/images/yoonieverse/post/f5ea06fc-eacc-4ae1-9a73-e5fc65d9ef0e/image.jpg)

## Problem
코딩을 해본 사람이라면 **"컴퓨터는 위에서 아래로 읽어요~"** 라는 말을 많이 들어 보았을 것이다.
나 또한 아주 많이 들어보았다.ㅎㅎ
하지만.. 나는 <span style="color:red;">[HTML]</span>파일에 있는 `<body>` 와 <span style="color:blue;">[CSS]</span>파일을 통해 웹을 꾸몄고 <span style="color:red;">[HTML]</span>파일에 있는 `<head>` 는 크게 손을 대지 않았기에 신경을 크게 쓰지 않았다.
그래서 멍청멍청쓰인 나는 여기서 아주 기본적인 개념을 틀려 버리는데..^-^

나는 이제 코딩을 시작한 삐약이 였기에 `<head>` 에 들어가는 `<link>`  는 아래처럼 <span style="color:blue;">[CSS]</span>파일 하나만 적었었다.
```html
<link rel="stylesheet" href="./main.css">
```
<br />
But,, 이번에는 `reset.css` 파일 만드는 것을 배웠고 그것을 사용하기로 해본 것이다.
먼저 혼자 만들어보고 두 번째는 강의를 보며 내가 만든 방식과 어떻게 다른지 확인해보려 따라하고 있었다.
빠짐없이 따라했다고 생각했는데 처음부터 &lt;div&gt; 의 padding값이 먹히지 않던 것이다...🤷🏻‍♀️
하지만 <span style="color:blue;">[CSS]</span>파일에서는 안먹혔던 padding값이 <span style="color:red;">[HTML]</span>파일 안에 있는 &lt;div&gt;에 스타일을 주면 잘 된다는 것이다. 여기서 더 멘붕..🥲
몇 시간동안 처음부터 끝까지 다시 해보기도 하고 구글링하기도 했지만 이유를 알 수 없었다.
<br /><br />

그런데 갑자기 생각나버린 `<link>`..
알고보니
```html
<link rel="stylesheet" href="./main.css"> [main을 먼저 적어서 문제가 됨]
<link rel="stylesheet" href="./reset.css">
```

ㅎㅎ^-^ 바보마냥 스타일을 만들어주는 <span style="color:blue;">[CSS]</span>파일보다 `reset.css`를 뒤에 적어버린 삐약쓰ㅎㅎ🤦🏻‍♀️
그냥 강의를 제대로 본게 아니었고.. 개념을 완전히 무시해버렸고.. 

![](https://velog.velcdn.com/images/yoonieverse/post/4a221b97-eb01-47c7-b19d-96a06b5e5246/image.png)

## Solution
📌 `reset.css`를 만드는 이유가 브라우저마다 기본 속성과 요소들의 값이 다르기 때문에 기본값을 0으로 맞추어 어떤 브라우저에서든 같은 화면을 보기 위함인데 아무 생각 없이 `main.css`보다 `reset.css`를 뒤쪽에 배치하여 제대로 된 프로그래밍을 하지 못 했던 것 이다.
<br /><br />

_**<span style="color:red;">"컴퓨터는 위에서 아래로 읽어요~"</span>
<span style="color:orange;">"컴퓨터는 위에서 아래로 읽어요~"</span>
<span style="color:blue;">"컴퓨터는 위에서 아래로 읽어요~"</span>**_

그래서 아래처럼 &lt;link&gt; 태그에 reset.css를 먼저 적어준 후 main.css를 적어야 한다.

```html
<link rel="stylesheet" href="./reset.css">
<link rel="stylesheet" href="./main.css">
```
바보바보 멍청멍청쓰인 나는 같은 `<link>` 2개가 `<head>` 안에 모두 들어가 있고 순서가 어떻게 되든 브라우저에 영향을 끼치지 않는 것처럼 보여 css링크의 순서를 신경 쓰지 않았던 것..거의 뭐 자격박탈 수준ㅠ
다음부터는 이런 실수하지 않기를..🙏🏻

