---
title: "Git 저장소 만드는 방법"
excerpt: "로컬 저장소와 원격 저장소를 연결하는 방법을 알아보자. "

categories:
  - Git
tags:
  - [git, github]

permalink: /git/create-repo/

toc: true
toc_sticky: true

date: 2024-04-28
last_modified_at: 2024-04-28
---

# 👯‍♀️로컬 저장소와 원격 저장소 연결👯‍♀️

## git init
폴더를 하나 만든 후 그 폴더로 이동하여 `git init` 명령어를 실행하여 새로운 git 저장소를 만든다.

## git clone
저장소를 복제한다는 의미로, 로컬 저장소 복제와 원격 저장소 복제가 있다.  
### git clone [로컬 저장소 경로]
> - 내 컴퓨터에 로컬 킷 저장소가 있는 경우에 사용한다. 그 후 원격 저장소에 새 리포지토리를 생성한다.
> - 그 후 `git remote add [name] [url]` 를 이용하여 원격 저장소와 로컬 저장소를 연결한다.
>   - [name]에는 기본적으로 `origin` 으로 한다.
>   - `origin` 대신 다른 저장소 이름으로 바꿀 땐?
>       - `git remote rename [old name] [new name]`
>   - 원격 저장소와 연결을 끊을 땐?
>     - `git remote remove [name]`
> - 원격 저장소와 연결되었는지 확인할 땐 `git remote` 또는 `git remote -v` 를 이용하여 원격 저장소의 이름과 url 주소를 확인할 수 있다.

### git clone [깃허브 저장소 주소]
> - 원격 저장소를 먼저 만든 후 사용하는 방식이다.
> - 원격 저장소에서 로컬로 가져오기 위해 `git clone` 이후 깃허브 저장소의 주소를 가지고 와 뒤에 적어주면 된다.
>   - 깃허브 저장소의 주소는 HTTPS 형식과 SSH 형식으로 가지고 올 수 있다.
>   - 참고로 SSH 형식은 [SSH 키를 생성](https://Yooniever42.github.io/2024-04-28-git-ssh-keygen)한 후 사용할 수 있다.

작성중