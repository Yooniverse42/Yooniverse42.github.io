---
title: "헷갈리는 sort() 함수에 대해 알아보자"
excerpt: "sort는 뭐고 compare는 뭔가요?"

categories:
  - JavaScript
tags:
  - [javascript, sort, compare, callback]

permalink: /javascript/sort-compare-function/

toc: true
toc_sticky: true

date: 2024-06-14
last_modified_at: 2024-06-14
---

# 🤔 sort() 함수 사용 시 compare 함수를 꼭 사용해야 하나요?

## ⚙️ `sort()` 는 어떻게 동작하나요?

`sort()` 함수는 배열의 요소를 정렬하는데 사용된다. 선택적으로 비교 함수를 인자로 받을 수 있는데, 비교 함수가 없다면 배열 값을 <mark>_유니코드 코드 포인트 순서대로 정렬_</mark> 한다.

배열을 오름차순으로 정렬해보자.
```jsx
let arr = [1, 23, 5, 48];

arr.sort();

/*
(4) [1, 23, 48, 5]
*/
```
`sort()` 함수에 비교 함수를 넣지 않으면, 유니코드 코드 포인트 순서대로 정렬하기 때문에 오름차순으로 정렬되지 않았다.

## ⚖️ compare function 이용하기
그래서 정확한 비교를 위해 비교 함수(Compare function)을 사용해야 한다.
그리고 `sort()` 함수는 비교 함수에서 나온 반환값에 의해 정렬 타입이 정해진다.
- `반환값 = 음수` : b보다 **a가 먼저 정렬**
- `반환값 = 0` : 변경 없음
- `반환값 = 양수` : a보다 **b가 먼저 정렬**

```jsx
let arr = [1, 23, 5, 48];

function compare(a, b){

  if(a > b) return 1;
  if(a === b) return 0; // 동등연산자를 사용하면 형 변환이 일어날 수도 있기에 일치연산자로 사용함. 숫자만 있다면 동등연산자 사용 가능.
  if(a < b) return -1;
}

arr.sort(compare)
/*
(4) [1, 5, 23, 48]
*/
```
현재 코드도 오름차순으로 정렬하기 위해 만든 코드이다. 만약 내림차순으로 정렬하고 싶다면 return 값을 반대로 적어주면 된다.

```jsx
function compare(a, b){

  if(a > b) return -1;
  if(a === b) return 0;
  if(a < b) return 1;
}
```
사용할 때마다 if문을 사용하면 너무 귀찮아진다.. 그래서 아래 처럼 arrow function을 이용하여 짧게 사용하면 같은 결과를 얻을 수 있다.

```jsx
let arr = [1, 23, 5, 48];

// 오름차순
arr.sort((a, b) => a - b);

// 내림차순
arr.sort((a, b) => b - a);
```
그럼 return 값에 의해 순서 정렬이 될 것이다.

그래서 정확하게 오름차순, 내림차순을 하기 위해 비교함수인 compare 함수를 쓰는 것이다.
