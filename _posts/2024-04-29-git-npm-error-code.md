---
title: "npm ERR! code EACCES 오류 해결(with gitignore 파일 생성)"
excerpt: "npm 패키지를 설치 및 실행 중 오류 해결 방법"

categories:
  - Git
tags:
  - [Git, gitignore, npm, npx, sudo]

permalink: /git/npm-error-code/

toc: true
toc_sticky: true

date: 2024-04-29
last_modified_at: 2024-04-29
---

# 📌 npm ERR! 오류 해결 방법에 대해 알아보자.

## Problem

내가 작업하려고 하는 파일에 `.gitignore` 파일을 만들고 싶었다.
그래서 `npx mrm gitignore` 를 이용하여 파일을 만드려고 했지만..

![gitignore-error01](https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/004-01-gitignore.png)

<mark>npm ERR!</mark> 이라는 여러 줄이 나오며 에러 코드(npm ERR! code EACCES)가 떠버린 것이다..

이런 에러 코드는 npm 패키지를 설치하거나 실행할 때 뜨는 경우가 있다.  
이럴 경우 **sudo** 를 붙이면 해결을 할 수 있다.

나와 같은 오류로 헤매이고 있는 분들을 위해 포스팅을 하게 되었다. 😢

## Solution
위 이미지가 해당한 폴더는 해결을 해버렸기 때문에 새로운 폴더를 이용하여 solution을 적어 보겠음. 그리고 `.gitignore` 파일을 생성 중 일어난 일이므로 파일을 생성하는 방법을 토대로 보여주겠음.

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

---
<br />

💡 **추가** 💡  
`sudo`를 이용하는 것은 생각보다 귀찮았다..  
그래서 여러번 시도하다보니 에러 코드 _npm ERR! code EACCES_ 가 아닌 
>  Try running with sudo or get access to the local update config store via  
`sudo chown -R $USER:$(id -gn $USER) /home/yooni/.config`

라는 새로운 내용이 표시되었다.

그래서 시키는 대로 
```
sudo chown -R $USER:$(id -gn $USER) /home/yooni/.config
``` 
를 그대로 작성하니 `sudo`를 사용하지 않아도 에러가 나지 않는다.
혹시 나처럼 같은 에러가 난다면 위 코드를 실행 해보기를 바란다.
실행 시 *yooni* 대신에 자신의 컴퓨터에 입력된 자신의 이름을 넣으면 된다.