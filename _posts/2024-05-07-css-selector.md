---
title: "CSS 선택자 파헤치기"
excerpt: "CSS 선택자 종류와 우선순위에 대해 알아보자."

categories:
  - CSS
tags:
  - [HTML, CSS, selector, specificity, inherit]

permalink: /css/selector/

toc: true
toc_sticky: true

date: 2024-05-07
last_modified_at: 2024-05-07
---

# 👨🏻 👩🏻 선택자란? 👦🏻 👧🏻

**Ex.**

```css
p {
  color: red;
  font-size: 10px;
}
```

`p` : 선택자  
`{ ... }` : 선언  
`color:red;`, `font-size:10px;` : 선언문  
`color`, `font-size` : 속성  
`red`, `10px` : 속성값

<br>

## 1) Type Selector

> 위 예시처럼 태그를 선택하는 selector

```html
HTML
<p>Type Selector</p>
<div>Type Selector</div>
```

```css
CSS p {
  color: red;
}
```

![](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories02-css/002-01-selector.png?raw=true)

<br/>

## 2) Class Selector

> html 문서에서 여러번 중복 가능하고 한 태그에 여러 개의 class를 사용할 수 있다.
> css에서 선택자 앞에 `.`(마침표) 붙여서 사용한다.

```html
HTML
<p>Class Selector</p>
<div class="red">Class Selector</div>
<p class="red">Class Selector</p>
```

```css
CSS .red {
  color: red;
}
```

![](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories02-css/002-02-selector.png?raw=true)

> 🚨 `.red` 보단 `div.red` 처럼 사용할 때 더 우선순위가 높다.  
> 만약 아래와 같은 예시에서의 css는

```html
<div class="class1">
  <p class="class2"></p>
</div>
```

`.class1 .class2` 와 중첩 패턴에서의 `&.class2` 는 같은 결과값을 가져온다.

<br/>

## 3) ID Selector

> html 문서에서 한 번만 사용 가능하다. 어떤 태그와도 중복이 되서는 안된다.
> css에서 선택자 앞에 `#` 붙여서 사용한다.

```
HTML
  <p>ID Selector</p>
  <div id="red">Id Selector</div>
  <p id="blue">Id Selector</p>
```

```
CSS
#red {
  color: red;
}
#blue {
  color: blue;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/21f40a09-d60c-437d-a984-56958b6791db/image.png)

> 🚨 만약 class 와 id 모두 가지고 있는 태그 요소만 선택하고 싶을 땐 `.class#id` 처럼 적용해주면 된다.

<br/>

## 4) Selector Combinators (선택자 결합)

### 4-1) 하위 선택자 결합

> 공백(spacing)을 이용하는 선택자로 자식요소를 모두 선택한다. 자식의 자식의 자식..까지 **모두** 선택된다.

```
HTML
  <p>Selector Combinators</p>
  <div class="red">
    <p>p 하위 선택자</p>
    <span> span 하위 선택자</span>
    <p>p 하위 선택자</p>
    <div>div 하위 선택자
    	<p>div p 하위 선택자</p>
    </div>
  </div>
```

```
CSS
.red p {
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/1c18ff34-2e5d-453e-bed5-aab5cb324674/image.png)

> `<div class="red">` 안에 있는 모든 `<p>` 가 선택됨.

<br/>

### 4-2) 자식 선택자 결합

> `>`(꺾쇠)를 이용하는 선택자이고 **바로 밑**의 하위 자식만 고른다.

```
HTML
  <p>Selector Combinators</p>
  <div class="red">
    <p>p 자식 선택자</p>
    <span> span 자식 선택자</span>
    <p>p 자식 선택자</p>
    <div>div 자식 선택자
      <p>div p 자식 선택자</p>
    </div>
  </div>
```

```
CSS
.red > p {
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/ee6fb424-70b3-4eb5-89a7-4b28f09bd45f/image.png)

<br/>

### 4-3) 형제 선택자 결합

#### 4-3-1) 일반 형제 선택자 결합

> `~`(물결)을 이용하는 선택자로 뒤쪽의 원하는 형제 태그들을 선택한다.

```
HTML
  <p>Selector Combinators</p>
  <div>div 일반 형제 선택자</div>
  <p>p 일반 형제 선택자</p>
  <span>span 일반 형제 선택자</span>
  <p>p 일반 형제 선택자</p>
  <div>div 일반 형제 선택자</div>
```

```
CSS
div ~ p {
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/8417c4ad-2b2f-4444-bc9b-eac1bbe0d709/image.png)

> `div ~ p` : `<div>` 와 **형제** 태그이면서 `<div>` **다음**으로 오는 `<p>`들이 선택됨.
> 그래서 `<div>` 앞에 있는 `<p>`는 선택안됨.

<br/>

#### 4-3-2) 인접 형제 선택자 결합

> `+`를 이용하는 선택자로 바로 뒤에 오는 형제를 선택한다.

```
HTML
  <p>Selector Combinators</p>
  <div>div 인접 형제 선택자</div>
  <p>p 인접 형제 선택자</p>
  <span>span 인접 형제 선택자</span>
  <p>p 인접 형제 선택자</p>
  <div>div 인접 형제 선택자</div>
```

```
CSS
div + p {
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/339d20dd-9ee1-4530-86f0-917471c9a413/image.png)

> `div + p` : `<div>` 와 **형제** 태그이면서 `<div>` **바로 다음**으로 오는 `<p>`만 선택됨.
> 그래서 `<div>` 앞에 있는 `<p>`와 `<div>` 뒤에 있지만 `<span>`을 거쳐서 나오는 다섯 번째 `<p>`는 선택안됨.

<br/>

### 4-4) 그룹화

> 선택자는 다르지만 선언문이 같을 때 주로 사용한다. 선택자의 개수는 상관없다.

```
HTML
  <p>Selector Combinators</p>
  <div>div 그룹화</div>
  <span>span 그룹화</span>
  <main>main 그룹화</main>
```

```
CSS
div, span, main {
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/4a368d75-3c2a-425c-8197-7f2e9d11e859/image.png)

<br/>

## 5) Universal Selector (범용, 전체 선택자)

> `*`를 이용하는 선택자로 이름 그대로 전체를 선택하게 됨.

```
HTML
  <div>div 전체 선택자</div>
  <span>span 전체 선택자</span>
  <main>main 전체 선택자</main>
  <p>p 전체 선택자</p>
```

```
CSS
*{
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/693eae56-4d58-4c0d-b0d2-86eae35600f2/image.png)

> `*`만 사용할 땐, 보통 css 파일 맨 위에 작성함.
> ` div + *` , `div > *` 등 이런식으로 선택자 종류와 함께 사용 가능하다.

<br/>

## 6) Attribute Selector (속성 선택자)

> html 요소의 속성값이나 유무를 통해 선택한다.
> 예시)

```
HTML
  <ul>
    <li>
      <a href="http://example.com" target="_blank">
        Example Link (com/http)
      </a>
    </li>
    <li>
      <a href="http://example.org" target="_blank" class="red">
        Example Link (org/http)
      </a>
    </li>
    <li>
      <a href="https://exa-mple.com" class="bold">
        Exa-mple Link (com/https)
      </a>
    </li>
    <li>
      <a href="https://example.org">
        Example Link (org/https)
      </a>
    </li>
  </ul>
```

![](https://velog.velcdn.com/images/yoonieverse/post/1a73960b-f5e0-452d-a739-bf13c0d520c4/image.png)

### 6-1) [attr]

> a[target] { color : red; }
> 👉 target 속성이 들어있는 a 요소

### 6-2) [attr=vlaue]

> a[href="https://example.org"] { color : green; }
> 👉 속성 href의 갑이 https//example.org 인 a 요소
> a[class="bold"] { font-weight : bold; }
> 👉 속성 class의 값이 bold 인 a 요소

![](https://velog.velcdn.com/images/yoonieverse/post/286e4814-0ec2-40cc-a8e7-2673975b6363/image.png)

### 6-3) [attr^=vlaue]

> a[href^="https"] { color : red; }
> 👉 속성 href의 값이 https로 시작하는 a 요소

### 6-4) [attr$=vlaue]

> a[href$="com"] { font-weight : bold; }
> 👉 속성 href의 값이 com으로 끝나는 a 요소

### 6-5) [attr*=vlaue]

> a[href*="exa-mple"] { font-size : 1.3rem; }
> 👉 속성 href의 값이 exa-mple을 포함하는 a 요소

![](https://velog.velcdn.com/images/yoonieverse/post/6a2147f6-859a-47e5-a154-5b9f976100ae/image.png)

<br/>

## 7) 가상 요소 선택자

> html 요소의 위치를 이용한다.

### 7-1) ::before, ::after

> `content: ""`선언문과 함께 사용되며 요소 앞(before), 뒤(aftrer)에 추가한다.

### 7-2) ::first-letter

> 요소의 첫 글자를 선택한다.

### 7-3) ::first-line

> 요소의 첫 줄을 선택한다.

### 7-4) ::selection

> 드래그 했을 때 나타난다.

<br/>

## 8) 가상 클래스 선택자

### 8-1) :focus

> tab키 등으로 요소가 포커스가 되었을 때 적용한다.

### 8-2) :hover

> 마우스가 요소 위에 올려졌을 때 적용한다.

### 8-3) :active

> 마우스로 누를 때부터 뗄 때까지 적용한다.

### 8-4) :link

> 링크가 걸려있는 텍스트에 적용한다.

### 8-5) :visited

> 방문한 링크에 적용한다.

### 8-6) :nth-child(n), :first-child, :last-child

> 같은 요소 중 n번째, 첫 번째(first), 마지막(last) 요소를 선택한다.

### 8-7) :nth-of-type, :first-of-type, :last-of-type

> 여러 type 중 n번째, 첫 번째(first), 마지막(last) 요소를 선택한다.
> 만약 `.red:first-of-type` 이라면 class가 red인 요소들 중에 모든 첫 번째 요소를 선택.

```
HTML
  <p class="red">p태그</p>
  <div class="red">div태그</div>
  <p class="red">p태그</p>
  <span class="red">span태그</span>
  <div class="red">div태그</div>
```

```
CSS
.red:first-of-type {
  color: red;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/9e941e94-9a75-4c22-9349-50a51e911438/image.png)

> `class="red"`인 모든 첫 번째 요소들은 선택이 되었고 `class="red"`인 두 번째 요소들은 선택되지 않았다.

### 8-8) :not

> selector:not(속성)
> 선택자 빼고 나머지를 선택한다.

```
HTML
  <form action="">
    <input type="email" placeholder="email">
    <input type="password" placeholder="password">
    <input type="text" placeholder="text">
    <input type="submit">
  </form>
```

```
CSS
input:not([type=text]){
  background-color: lightblue;
}
```

![](https://velog.velcdn.com/images/yoonieverse/post/7a75b12e-587a-4bd1-8a2e-9183892c5162/image.png)

### 8-9) :enabled, :disabled, :checked

> `:enabled` : 활성화 되어있는 요소를 선택한다.
> `:disabled` : 비활성화 되어있는 요소를 선택한다.
> `:checked` : 요소를 체크했을 때 적용된다.

```
HTMl
  <form class="form">
    <input type="email" placeholder="email">
    <input type="password" placeholder="password">
    <input type="text" placeholder="text" disabled>
    <input type="submit">
  </form>
  <form>
    <input type="checkbox" name="check" id="check">
    <label for="check">check</label>
  </form>
```

```
CSS
input:enabled { background-color: lightblue;}
input:disabled { background-color: lightgray;}
input:checked { outline: 3px solid red;}
```

![](https://velog.velcdn.com/images/yoonieverse/post/408c66be-1c44-4d90-9349-7551704772bf/image.png)

<br/>

## 9) 선택자 우선순위

> 선택자가 동일하다면 뒤에 나온 스타일이 우선순위가 높다.
> <br/>
> **선택자는 다르지만 동일한 요소를 지정한다면?**
> "**명시도**"에 따라 우선순위가 결정된다.

1. 중요도(!improtant) : 가장 우선시 된다.
2. 인라인 스타일 : HTML 요소에 직접 적용된 스타일
3. ID 선택자
4. 클래스 선택자, 속성 선택자, 가상 클래스
5. 태그(요소) 선택자
6. 전역 선택자(\*) : 우선순위가 가장 낮다.
