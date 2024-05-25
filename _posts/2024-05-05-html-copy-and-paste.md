---
title: "동일한 태그를 복붙 대신에 쉽게 만드는 방법"
excerpt: "우리의 손가락은 소중하니까요"

categories:
  - HTML
tags:
  - [HTML, CSS, tag, copy, paste]

permalink: /html/copy-and-paste/

toc: true
toc_sticky: true

date: 2024-05-05
last_modified_at: 2024-05-05
---

# 아직 드래그 + 복사 + 붙여넣기 하고 있나요?

동일한 태그를 쭉 이어서 만들 때 하나하나 힘들게 드래그해서 복붙하고 있나요?  
우리의 손가락은 소중하니까.. 키보드로 간편하게 할 수 있는 명령어와 단축키에 대해 알아봅시다.

<br/>

## 1️⃣ 태그만 여러개 만들고 싶을 때❗️

☝🏻첫 번째 방법 : **원하는 태그\*원하는 개수**

- 예를 들어 div 태그를 5개 만들고 싶다면 `div*5`를 작성 후 “_enter_” or “_tab_”을 누름

```html
<body>
  div*5
</body>
```

⬇️ “_enter_” or “_tab_”을 누르면 아래와 같이 만들어짐.

```html
<body>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</body>
```

만약 class가 들어가고 텍스트도 숫자1부터 숫자5 까지 나오게 하고 싶다면!  
`div.num{숫자$}*5`를 작성

```html
<body>
  <div class="num">숫자1</div>
  <div class="num">숫자2</div>
  <div class="num">숫자3</div>
  <div class="num">숫자4</div>
  <div class="num">숫자5</div>
</body>
```

속성 추가도 가능하다!  
`button.btn$[type=button]{버튼$}*5`

```html
<body>
  <button class="btn1" type="button">버튼1</button>
  <button class="btn2" type="button">버튼2</button>
  <button class="btn3" type="button">버튼3</button>
  <button class="btn4" type="button">버튼4</button>
  <button class="btn5" type="button">버튼5</button>
</body>
```

<br/>

✌🏻두 번째 방법 : **option + shift + 방향키** (mac이 아닌 윈도우 사용 시 alt+shift+방향키)

- 복사를 하고 싶은 태그에서 “option + shift + (위 또는 아래) 방향키” 를 누르면 누를 때마다 하나씩 복사됨
- 텍스트 커서의 위치는 상관없음 복붙을 원하는 줄에만 텍스트 커서가 있으면 됨

```html
<body>
  <div></div>
</body>
```

⬇️ `<div></div>` 중 아무곳이나 텍스트 커서를 놔둔 후 “option" 과 "shift"를 누른 후 아래 방향키를 2번 누르게 되면 아래와 같이 만들어짐.

```html
<body>
  <div></div>
  <div></div>
  <div></div>
</body>
```

<br/>

## 2️⃣ 태그 안 요소까지 복붙하고 싶을 때

위 **두 번째 방법** 처럼 똑같이 하면 됨.  
`option + shift + 방향키` (mac이 아닌 윈도우 사용 시 alt+shift+방향키)
