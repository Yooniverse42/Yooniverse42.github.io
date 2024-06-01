---
title: "변수 호이스팅 뿌수기"
excerpt: "아주 중요한 변수 호이스팅에 대해 자세히 알아보자"

categories:
  - JavaScript
tags:
  - [javascript, variable, hoisting]

permalink: /javascript/variable-hoisting/

toc: true
toc_sticky: true

date: 2024-05-29
last_modified_at: 2024-05-29
---

# 🤔 변수 호이스팅

자바스크립트 파일을 웹 브라우저가 여는 순간 <mark>Global Execution Context</mark>가 생성 = 실행 환경 구축!  
그 후 var, let, const, 함수 선언부 등 모든 선언부들을 끌어올리게 된다. 이것이 **호이스팅**!

![](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories03-javascript/variable-hoisting-01.png?raw=true)
<small>출처 : 멋쟁이사자처럼 범쌤</small>

<br>

## var 키워드의 호이스팅 🎈

`➡️ Lexical Environment ➡️ Environment Record ➡️ Object Environment ➡️ Binding Object`

Object Environment = window = 전역 객체,  
그럼 Binding Object? = 전역 객체랑 바인딩 된다!

그리고 var 선언문은 끌어올려옴과 동시에 초기값(undefined)을 할당한다.

```jsx
console.log(a); // undefined

var a = 10;
let b = 20;
const c = 30;

console.log(a); // 10
```

그래서 위와 같은 코드에서 첫 번째 값은 undefined가 나오게 되고 그 이후 x의 재할당 값인 10이 출력이 되는 것이다.  
그리고 window(전역 객체)에 Binding 되므로 window.a 했을 때 10이 나올 수 있는 것!  
하지만 window.b, window.c 는 값이 나오지 않는다.

<br>

## let, const 키워드의 호이스팅 🪁

그 이유는 let, const 키워드가 Object Environment에 들어가 전역 객체와 Binding 되지 않기 때문이다.  
`➡️ Lexical Environment ➡️ Environment Record ➡️ Declarative Environment ➡️ let, const`
let과 const는 위와 같은 순서가 적용된다.

호이스팅이 일어나지만 어떠한 값도 할당되지 않은 상태로 메모리에 저장된다. 이것을 TDZ(Temporal Dead Zone, 일시적 사각지대)라 부른다.
![](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories03-javascript/variable-hoisting-02.png?raw=true)

```jsx
console.log(b); // ReferenceError
console.log(c); // ReferenceError

var a = 10;
let b = 20;
const c = 30;

console.log(b); // 20
console.log(c); // 30
```

그래서 선언 전에 출력을 하게 되면 `ReferenceError`가 출력된다.

<br>

---

## 참고 🎯

함수도 var 키워드와 같은 순서가 적용이 된다.

```jsx
sum(); // 3

function sum() {
  return 1 + 2;
}
```

그래서 선언 전에 실행을 해도 값이 나오게 되는 이유이며, window.sum 했을 시 값이 나온다.  
그리고 호이스팅 됐을 때, `sum: return 1+ 2` 함수 본문 그대로 등록이 된다!
