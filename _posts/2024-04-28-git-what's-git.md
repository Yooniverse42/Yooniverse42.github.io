---
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

<img src="https://Yooniverse42.github.io/assets/images/posts_img/categories05-git/001-gitLogic.png" alt="git-logic">

## Git

Git 이란 <mark>버전 관리 시스템(VCS)</mark> 중 하나로, 프로젝트의 소스 코드나 파일들의 변경 이력을 관리하고 추적하는 도구이다.  
작동방식은 스냅샷 방식으로 여러 명의 개발자가 동시에 작업할 수 있고, 변경 사항 추적과 관리할 수 있다. 이를 통해 프로젝트의 버전을 관리하고, 이전 상태로 손쉽게 복구하거나 변경 사항을 비교할 수 있다.  
위쪽의 작동 구조 이미지를 보면 쉽게 이해할 수 있다.  
**내 컴퓨터 (local)** : `Working Directory`, `Staging Area`, `local Repositoy`  
**원격(remote, GitHub)** : `Remote Repository`

## GitHub

GitHub는 Git을 기반으로한 <mark>웹 기반의 호스팅 서비스</mark>로, Git 저장소를 호스팅하고 버전 관리를 위한 다양한 기능을 제공한다. GitHub를 사용하면 개발자들은 프로젝트를 협업하고 관리할 수 있으며, 소스 코드를 온라인 상에서 공유하고 협업할 수 있다.

## Git & Github 관련 용어 및 주요 명령어

### <u>Working Directory</u>

> 내 컴퓨터에 있는 작업 폴더를 말한다. Git에서 관리하지만 추적은 하지 않는다.

### <u>Staging Area</u>

> git 디렉토리에 있으며, 단순한 파일이고, 곧 커밋할 파일에 대한 정보를 저장한다. 즉, 임시 저장 영역이라고 보면 된다.

### <u>Local Repository</u>

> 커밋들이 영구적으로 저장되는 영역이다. 내가 수정한 파일들을 커밋할 때마다 _Local Repository_ 에 커밋들이 쌓인다. 또한 원격 저장소로부터 clone한 커밋들이 존재하는 역역이기도 하다.

### <u>Remote Repositry</u>

> _Local_ 이 아닌 원격 서버(GitHub)에 저장된 저장소로, 사용자가 직접 관리하는 저장소이다.

### <u>Add</u>

> `git add [파일 이름]`  
> Git이 해당 파일의 변경 사항을 추적하도록 하는 단계이다.  
> _Working Directory_ 에서 _Staging Area_ 로 추가한다.

### <u>Commit</u>

> `git commit -m [확정본에 대한 설명]`  
> Git에 저장하는 단계로, _Staging Area_ 에 있는 변경된 파일을 *Local Repository*에 영구적으로 기록한다. 이러한 변경된 파일은 **HEAD** 에 반영 된다.

### <u>Push</u>

> `git push` `git push origin [가지 이름]`  
> 로컬 저장소의 커밋들을 원격저장소로 업로드하는 단계이다. 커밋한 파일들은 아직 원격 저장소가 아닌 로컬 저장소의 **HEAD** 안에 머물고 있어 push를 이용하여 원격 서버로 올려야 한다.

### <u>Branch</u>

> `git branch [new 가지 이름]` : 가지 생성  
> 이름 그대로 '가지를 친다' 라고 말한다. 저장소를 만들면 기본으로 **main(또는 master)** 가지가 만들어지고 거기서 다른 가지( = branch)를 만들어 개발을 하는 것이다. 개발이 완료되면 **main(또는 master)** 가지로 돌아와 병합 (merge)를 하면 된다.

### <u>Pull</u>

> `git pull`  
> 내 컴퓨터에 있는 로컬 저장소를 원격 저장소에 맞춰 갱신할 때 사용하며, 원격 저장소의 변경 내용이 로컬 작업 디렉토리에 받아지고(fetch) 병합(merge)된다. **pull**을 이용하면 최신 상태의 원격 저장소 파일을 받을 수 있어 작업 시작 시에 이용하기 좋다.

### <u>Merge</u>

> `git merge [new 가지 이름]`  
> 두 개의 다른 브랜치를 하나로 합치는 명령어이다. 하지만 병합 중 충돌(conflicts)이 일어날 때도 있다. 그럼 git은 충돌 부분을 알려주고, 내가 직접 수정하여 병합이 가능하도록 한다.  
> `git diff [원래 가지 이름] [new 가지 이름]` 을 이용하면 변경 내용을 병합하기 전에 어떻게 바뀌었는지 비교할 수 있다.

### <u>Checkout</u>

> `git checkout --[파일 이름]`  
> 오래된 Git 명령어로, 브랜치 전환, 새 브랜치 생성, 파일 복구 등 다양한 작업을 처리하는데 사용한다. 만약 파일의 변경 사항이 잘못 되었을 때, checkout을 통해 변경 전 상태(HEAD)로 되돌려 준다.
>
> > 만약 로컬에 있는 모든 변경 내용과 확정본을 **포기**하려면, `git fetch origin` 또는 `git reset --hard origin/master`로 원격 저장소의 최신 이력으로 가져오고, 로컬 master 가지가 저 이력을 가리키도록 할 수 있다.

### <u>Switch</u>

> `git switch [가지 이름]`  
> 말 그대로 브랜치를 변경할 때 사용하고, `-c`를 추가하면 새 브랜치 생성 및 이동을 할 수 있다. **checkout**과 기능적으로 중복되는 부분이 있지만 가지간 이동할 때 switch 사용을 하는 것이 편하다.

### <u>Fetch</u>

> `git fetch`  
> 원격 저장소에서 최신 데이터 정보를 확인할 뿐, 변경된 데이터를 로컬 Git에 실제로 가져오지는 않는다. 그래서 병합 전 변경 내용을 검토할 수 있어, pull 보다는 fetch가 안전하다.

### <u>Pull Request</u>

> 기존 `branch`에 내가 만든 branch를 merge 해달라고 요청 또는 피드백 받는 곳이다.

### Fork

> 남의 저장소(Remote)에서 내 저장소로 가져오는 작업이다.

### ISSUES

> GitHub에서 커뮤니케이션을 통해 문제 해결하는 곳이다. 예를 들어 남이 만든 저장소에 내가 수정하고 싶은 곳이나 버그가 있어 따로 Branch 파일을 만들었다면, 그 Branch 파일을 남의 ISSUES 탭에 내가 만든 Branch 파일을 올리고 ㅇㅋ 하면 내가 만든 파일을 합쳐서 수정하기도 한다. 다른 사람이 수정 사항이 있으면 댓글을 달아주기도 한다.

### README

> Markdown을 통해 README.md 를 만들 수 있다. 나의 작업물에 대한 설명을 적어놓는 곳이기도 하며 저장소 하단에 나타난다.
