---
title: "revert와 reset의 차이"
excerpt: "버전을 되돌리는 git revert와 git reset에 대해 알아보자."

categories:
  - Git
tags:
  - [Git, revert, reset, github]

permalink: /git/revert-reset/

toc: true
toc_sticky: true

date: 2024-07-06
last_modified_at: 2024-07-06
---

# git revert 와 reset 차이

만들어진 버전을 되돌릴 땐 두 가지 방법이 있다.

1. <mark>revert</mark>

   - 버전을 되돌린 새로운 버전 만들기
   - 만약 10번째 버전을 만들고 작업하던 도중, 9번째 버전으로 돌아가고 싶을 때, `revert` 를 사용하면 9번째 버전과 똑같은 버전인 11번째 버전이 만들어지는 방법.

   <br/>

2. <mark>reset</mark>
   - 버전을 완전히 되돌리는 방법
   - 시간을 되돌리 듯 원하는 버전으로 돌아가게 됨. 그럼 지금까지 만들었던 버전들은 없어짐
   - `reset` 에도 3가지 방법이 있음
     - soft : 커밋만 되돌리기
     - mixed : 스테이지까지 되돌리기
     - hard : 작업 디렉토리까지 되돌리기
       > 하나의 버전이 만들어지는 과정
       >
       > 1. ~~작업 디렉토리에서 변경 사항 생성~~ ⇒ hard reset
       > 2. ~~스테이지로 추가~~ ⇒ mixed reset
       > 3. ~~저장소로 커밋~~ ⇒ soft reset
