---
title: "&lt;input&gt; 속성 추가 - required, disabled, checked"
excerpt: "input 요소에 들어갈 속성 중 required, disabled, checked에 대해 알아보자."

categories:
  - HTML
tags:
  - [HTML, CSS, input, required, disabled, checked]

permalink: /html/input-required-disabled-checked/

toc: true
toc_sticky: true

date: 2024-05-09
last_modified_at: 2024-05-09
---

# 📋 &lt;input&gt; 속성 추가

```html
HTML
<form action="join.html">
  <input type="email" placeholder="email" required />
  <input type="password" placeholder="password" required />
  <input type="text" placeholder="text" disabled />
  <input type="submit" />
</form>
```

✅ body의 배경색만 따로 지정함.
![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/003-01-input.png)

<br>

## 1) required

> 필수 입력으로 설정하고 싶을 때

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/003-02-input.png)

입력하지 않고 `제출`버튼을 누르면 페이지가 넘어가지 않고 "**이 입력란을 작성하세요.**" 라는 멘트가 나온다.

<br>

## 2) disabled

> 마우스로 클릭하거나 텍스트 입력 등 비활성으로 변경된다.

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/003-03-input.png)

활성화 되어있는 요소들과 달리 비활성화된 `<input type="text">`는 foucs, active가 되지 않고 입력도 되지 않는다. 비활성된 요소들은 **상위 요소의 배경색**을 따라가고 배경색과 **비슷한** 색으로 적용된다.

<br>

## 3) checked

> 사용자가 체크하기 전에 처음부터 기본으로 체크되어져 있게 만든다.

### `checked` 적용하지 않았을 때

```html
HTML
<div>
  <input type="radio" name="check" id="check01" />
  <label for="check01">check01</label>
  <input type="radio" name="check" id="check02" />
  <label for="check02">check02</label>
</div>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/003-04-input.png)

### `checked` 적용했을 때

```html
HTML
<div>
  <input type="radio" name="check" id="check01" checked />
  <label for="check01">check01</label>
  <input type="radio" name="check" id="check02" />
  <label for="check02">check02</label>
</div>
```

![](https://Yooniverse42.github.io/assets/images/posts_img/categories01-html/003-05-input.png)

처음 사이트를 들어갈 때부터 "check01"에 선택되어져 있다.
