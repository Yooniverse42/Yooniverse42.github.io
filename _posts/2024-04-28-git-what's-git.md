p---
title: "Git & GitHub 개념 및 용어"
excerpt: "Git/GitHub에 대해서 전체적인 작동 구조와 개념, 용어에 대해 알아보자 "

categories:
  - Git
tags:
  - [git, github]

permalink: /git/what's-git/

toc: true
toc_sticky: true

date: 2024-04-28
last_modified_at: 2024-04-28
---

# 🎁 Git & GitHub 이해하기
<img src="https://Yooniverse42.github.io/assets/images/posts_img/categories04-git/001gitLogic.png" alt="git-logic">


## Git
Git 이란 <mark>버전 관리 시스템(VCS)</mark> 중 하나로, 프로젝트의 소스 코드나 파일들의 변경 이력을 관리하고 추적하는 도구이다.  
작동방식은 스냅샷 방식으로 여러 명의 개발자가 동시에 작업할 수 있고, 변경 사항 추적과 관리할 수 있다. 이를 통해 프로젝트의 버전을 관리하고, 이전 상태로 손쉽게 복구하거나 변경 사항을 비교할 수 있다.  
위쪽의 작동 구조 이미지를 보면 쉽게 이해할 수 있다.  
**내 컴퓨터 (local)** : `Working Directory`, `Staging Area`, `local Repositoy`  
**원격(remote, GitHub)** : `Remote Repository`


## Git 용어 및 명령어
### <u>Working Directory</u>
>내 컴퓨터에 있는 작업 폴더를 말한다. Git에서 관리하지만 추적은 하지 않는다.

### <u>Staging Area</u>
>git 디렉토리에 있으며, 단순한 파일이고, 곧 커밋할 파일에 대한 정보를 저장한다. 즉, 임시 저장 영역이라고 보면 된다.

### <u>Local Repository</u>
>커밋들이 영구적으로 저장되는 영역이다. 내가 수정한 파일들을 커밋할 때마다 *Local Repository* 에 커밋들이 쌓인다. 또한 원격 저장소로부터 clone한 커밋들이 존재하는 역역이기도 하다.

### <u>Remote Repositry</u>
>*Local* 이 아닌 원격 서버(GitHub)에 저장된 저장소로, 사용자가 직접 관리하는 저장소이다. 

### <u>Add</u>
>`git add [파일 이름]`  
Git이 해당 파일의 변경 사항을 추적하도록 하는 단계이다.  
*Working Directory* 에서 *Staging Area* 로 추가한다.

### <u>Commit</u>
>`git commit -m [확정본에 대한 설명]`  
Git에 저장하는 단계로, *Staging Area* 에 있는 변경된 파일을 *Local Repository*에 영구적으로 기록한다. 이러한 변경된 파일은 **HEAD** 에 반영 된다.

### <u>Push</u>
>`git push` `git push origin [가지 이름]`  
로컬 저장소의 커밋들을 원격저장소로 업로드하는 단계이다. 커밋한 파일들은 아직 원격 저장소가 아닌 로컬 저장소의 **HEAD** 안에 머물고 있어 push를 이용하여 원격 서버로 올려야 한다.

### <u>Fetch</u>
>`git fetch`
작성중









## GitHub
GitHub는 Git을 기반으로한 <mark>웹 기반의 호스팅 서비스</mark>로, Git 저장소를 호스팅하고 버전 관리를 위한 다양한 기능을 제공한다. GitHub를 사용하면 개발자들은 프로젝트를 협업하고 관리할 수 있으며, 소스 코드를 온라인 상에서 공유하고 협업할 수 있다.

<br />

## GitHub 용어 정리
### Repository
스테이지에서 대기하고 있던 파일들을 버전으로 만들어 저장하는 곳이다.
Gi은 원격(remote) 저장소와 로컬(local) 저장소, 두 종류의 저장소를 제공한다.

### Remote Repositry(원격 저장소)


