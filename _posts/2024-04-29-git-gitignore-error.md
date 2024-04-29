---
title: "gitignore 파일 생성 및 오류 해결 방법"
excerpt: "gitignore 파일 생성 중 오류 해결 방법"

categories:
  - Git
tags:
  - [Git, gitignore, npm, npx, sudo]

permalink: /git/gitignore-error/

toc: true
toc_sticky: true

date: 2024-04-29
last_modified_at: 2024-04-29
---

# 📌 .gitignore 파일 생성 중 오류 해결 방법에 대해 알아보자.

## Problem

내가 작업하려고 하는 파일에 `.gitignore` 파일을 만들고 싶었다.
그래서 `npx mrm gitignore` 를 이용하여 파일을 만드려고 했지만..

![gitignore-error01](https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/004-01-gitignore.png)

<mark>npm ERR!</mark> 이라는 여러 줄이 나오며 에러가 나버린 것이다..

나와 같은 오류로 헤매이고 있는 분들을 위해 포스팅을 하게 되었다. 😢

## Solution
위 이미지가 해당한 폴더는 해결을 해버렸기 때문에 새로운 폴더를 이용하여 solution을 적어 보겠음.

먼저 `.gitignore` 파일을 생성하고 싶은 폴더에 들어온다.

아래의 코드를 적어준다.
```
sudo npx add-gitignore node
```
그럼 `sudo` 명령어를 통해 파일을 생성한다.

![gitignore-error02](https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/004-02-gitignore.png)

그럼 Password를 적으라고 나오는데, 그건 자신의 컴퓨터 비밀번호를 적으면 된다.

![gitignore-error03](https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/004-03-gitignore.png)

비밀번호 작성 후 완료 되었으면 위 이미지처럼 나오게 된다.

그러고 다시 `ls -a`를 통해 파일이 생성되었는지 확인해보자.

![gitignore-error04](https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/004-04-gitignore.png)

