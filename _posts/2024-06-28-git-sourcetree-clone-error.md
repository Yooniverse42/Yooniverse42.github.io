---
title: "Sourcetree로 clone 중 오류 해결!"
excerpt: "Sourcetree 오류 중 경로 관련 오류를 해결해보자. "

categories:
  - Git
tags:
  - [Git, sourcetree, clone, error, ssh]

permalink: /git/sourcetree-clone-error/

toc: true
toc_sticky: true

date: 2024-06-28
last_modified_at: 2024-06-28
---

# 📌 올바른 원본 경로/URL이 아닙니다.

## Problem

소스트리로 클론을 하려던 와중 아래쪽에 노란색 경고 표시와 함께 **올바른 원본 경로/URL이 아닙니다** 라는 문장을 만났다. 눌러서 어떤 문제점이 있는지 확인해보니 
"공개키 뭐시기라 저시기라..SSH 뭐시기라 저시기라.."
결론은 권한을 부여하라는 말 같은데ㅎ
이것저것 찾아보다 혼자 해결한 썰 풀어봅니당✌🏻

<br>
<br>

## Solution

![소스트리 에러 이미지](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories05-git/0628-sourcetree-error-01.png?raw=true)

먼저 소스트리에서 `계정`을 눌러 들어간다.

![소스트리 에러 이미지](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories05-git/0628-sourcetree-error-02.png?raw=true)



`계정 탭`에서 SSH 글자 옆에 노란색 경고 표시가 없는지 확인해본다.
경고 표시가 있다면 더블 클릭.

![소스트리 에러 이미지](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories05-git/0628-sourcetree-error-03.png?raw=true)


맨 아래쪽 `키 생성하기`를 누르고 키 생성은 선택사항이다. 나는 아무것도 작성하지 않고 바로 저장했다.
혹시 모르니 계정 연결 한 번더 해주기~

저장을 누르고 확인해보면 이제 경고 표시가 뜨지 않는 것을 확인 할 수 있다.

![소스트리 에러 이미지](https://github.com/Yooniverse42/Yooniverse42.github.io/blob/main/assets/images/posts_img/categories05-git/0628-sourcetree-error-04.png?raw=true)

다시 클론을 시도해보면? 오류가 없어진 것을 확인할 수 있다.
