---
title: "절대경로와 상대경로 차이"
excerpt: "절대경로와 상대경로, 경로 읽는 법에 대해 알아보자"

categories:
  -HTML/CSS
tags:
  - [HTML, CSS, path]

permalink: /htmlcss/relative-absolute-path/

toc: true
toc_sticky: true

date: 2024-05-03
last_modified_at: 2024-05-03
---

# 🧭 절대경로와 상대경로, 경로 읽는 법

컴퓨터 폴더나 사이트에서 많이 보이는 “슬래시(/)”는 경로를 나타냄.  
경로에는 절대경로와 상대경로가 있음.

- 절대경로 : 인터넷, url로 접속가능한 경로
- 상대경로 : (통상적으로) 개발 환경에서 시작되는 경로
  - . : 현재 파일이 위치한 경로
  - .. : 이전 경로, 상위 경로
  - / : 구분

현재 동일 폴더 일 땐 `./` 를 적지 않아도 됨.

<br>

## 상대경로로 파일 불러오기 🗄️

***[A]폴더***

- ***[a]폴더***
    - *[사진]폴더*
        - *picture_3.png*
    - *index.html*
    - *picture_2.png*
- ***picture_1.png***

나의 문서 파일에 위와 같이 정리된 폴더들과 사진들, 그리고 코딩 중인 html 파일이 있다고 가정 해보자.

여기서 picture_1.png, picture_2.png, picture_3.png 불러내는 방법은 아래와 같다.


⌨️ picture_1.png 불러오기

```css
<body>
    <img src="../picture_1.png">
</body>
```

코딩 중인 html파일은 [a]폴더에 있고 1번 사진은 상위폴더인 [A]폴더에 있으니 ‘이전경로, 상위경로’라는 의미에서 ../ 을 앞에 분여준 후 1번 사진을 불러온다.

⌨️ picture_2.png 불러오기

```css
<body>
    <img src="./picture_2.png">
    <img src="picture_2.png">
</body>
```

코딩 중인 html파일과 같은 폴더안에 있으므로 현재 폴더 안에 있다는 의미에서 ./ 를 붙여준 후 2번 사진을 불러온다. html과 동일한 폴더일 때는 ./ 를 붙여주지 않아도 되므로 바로 2번사진을 불러와도 된다.

⌨️ picture_3.png 불러오기

```css
<body>
    <img src="./사진/picture_3.png">
    <img src="사진/picture_3.png">
</body>
```

html파일은 [a]폴더에 있고 3번 사진은 [a]폴더 안에 [사진]폴더에 있으므로 ./ 에다가 ‘사진’을 붙여서 3번 사진을 불러온다. 2번 사진과 동일하게 [사진]이라는 폴더는 html과 동일한 폴더일 때는 ./ 를 붙여주지 않아도 되므로 바로 [사진]폴더를 불러온 후 3번사진을 불러와도 된다.

<br>

## 실전🏃🏻‍♀️

이제 어떤 사이트의 url을 보면 이게 어디서 이어진건지 이해가 될 것이다.

예를 들어 ‘macOS 안내서’를 들어가보면 url주소가 [https://subicura.com/mac/](https://subicura.com/mac/) 이라고 적혀 있는 것을 확인할 수 있다.

![path1](https://Yooniverse42.github.io/assets/images/posts_img/categories01-htmlcss/002-01-path.png)


 여기서 상단바 메뉴 중 ‘개발 환경 설정’ 이라는 메뉴를 들어가게 되면 url주소가 [https://subicura.com/mac/dev/hello.html](https://subicura.com/mac/dev/hello.html) 라고 되어있고 첫 번째 주소에서 dev/hello.html 이 추가된 것을 확인할 수 있다.

![path2](https://Yooniverse42.github.io/assets/images/posts_img/categories01-htmlcss/002-02-path.png)


 그럼 저 주소를 보고 유추할 수 있는 것은 첫 번째와 두 번째 사이트는 같은 사이트이고 두 번째 사이트는 첫 번째 사이트에서 dev 폴더 안에 있는 hello.html 인가보다 라고 생각해볼 수 있다.