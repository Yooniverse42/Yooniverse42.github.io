---
title: "npm ERR! code EACCES 오류 해결"
excerpt: "npm 패키지를 설치 및 실행 중 오류 해결 방법"

categories:
  - Git
tags:
  - [Git, gitignore, npm, npx, sudo]

permalink: /git/npm-error-solution/

toc: true
toc_sticky: true

date: 2024-05-01
last_modified_at: 2024-05-01
---

# 📌 npm ERR! 오류 해결 방법에 대해 알아보자.

## Problem

npm을 사용하다가 아래 사진 처럼 `npm ERR!` 이라고 적히며 에러 코드가 뜰 때가 있다.  
나와 비슷한 분들에게 도움이 되길 바라며...😭 해결 방법에 대해 알아보자.

![gitignore-error01](https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/004-01-gitignore.png)

<mark>npm ERR!</mark> 이라는 여러 줄이 나오며 에러 코드(npm ERR! code EACCES)가 나오며 권한 문제라고 얘기해주는 것 같다.

이런 에러 코드는 npm 패키지를 설치하거나 실행할 때 뜨는 경우가 있다.  
이럴 경우 **sudo** 를 붙이거나 에러 코드에서 하라고 하는대로 따라하면 해결을 할 수 있다.


## Solution
보통 내가 적으려고 하는 명령어 맨 앞에 `sudo` 라는 단어를 붙여주면 해결된다.
```
sudo [원래 사용하려고 했던 명령어]
```
또는 에러 코드가 말해주는대로 해보자. 나는  
`To permanetly fix this problem, please run: sudo chown -r 501:20 "/Users/yooni/.npm"`  
이 문제를 해결하려면 세미콜론 뒤를 실핼 하란다.
그대로 해주면 해결이 된다. yooni 대신에 사용자 이름을 적으면 된다.

보통 에러가 나면 해결 방법을 알려주니 구글링을 먼저 하는 것보다 번역기 돌리고 생각해보자. 나처럼 바보짓 하지말고..🤯