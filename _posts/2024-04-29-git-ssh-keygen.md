---
title: "GitHub 사용자 설정 및 ssh key 등록하는 법(with Terminal)"
excerpt: "git clone 중 SSH 형식으로 주소를 불러오기 위한 ssh key 생성하는 법을 알아보자."

categories:
  - Git
tags:
  - [Git, ssh key]

permalink: /git/ssh-keygen/

toc: true
toc_sticky: true

date: 2024-04-29
last_modified_at: 2024-04-29
---

# 🔐 ssh key 등록법을 알아보자.

**✅ Git 사용자 설정**
GitHub이 아닌 Local에서 사용하는 git에 사용자의 이메일과 이름을 설정해줄 수 있다.  
설정은 git config를 통해 가능하고 git에대한 설명을 추가 하거나 변경하고 삭제할 때 쓰이는 명령어이다.  
명렁어를 통해 여러가지 설정 가능하다.  
설정파일 자체는 git config를 통해 설정 가능한데  
`System 설정 파일`, `Global 설정 파일`, `Local 설정 파일` 총 3가지 있다.

```
System 설정 파일 : 모든 시스템 사용자에게 적용
Global 설정 파일 : 한 사용자의 전치 Git Repository에 적용
Local 설정 파일 : 하나의 Repository에만 적용
```

**✅ ssh 공개키를 등록하는 이유**
GitHub에는 절대경로를 통해서 로그인을 한다. 하지만 프로젝트를 GitHub에 생성하고 그것을 Local로 받아와 작업을 하기 위해서는 ssh 방식으로 받아와야 하는 경우가 있다. 그래서, ssh key를 GitHub에 등록을 해둔다. ssh key는 나의 컴퓨터에서 만들었기 때문에 GitHub 입장에서는 나의 컴퓨터라는 것이 인증된다(=사용자인식). 그러니 사용하는 컴퓨터가 바뀔 때 마다 새로운 ssh key를 만들어 작업을 해야 한다.

---

## 🗄️ Terminal로 사용자 설정하는 방법

먼저 Terminal에 아래 두 개의 명령어를 적어준다.

> git config --global user.email "깃헙에서 사용중인 이메일"  
> git config --global user.name "깃헙에서 사용중인 이름"

쌍 따옴표 앞에는 ❗️**꼭**❗️ 띄어쓰기를 해야한다. 그 후 list를 이용하여 이메일과 이름에 알맞게 들어갔는지 확인을 해준다.

> git config --list

![sshkey01](https://Yooniverse42.github.io/assets/images/posts_img/categories05-git/002-01-sshkey.png)
빨간색 네모끼리, 파란색 네모끼리 잘 들어갔다면 완료.

🥹 이제 반 왔습니다. 할 수 있습니다. 아자아자 안화이팅 😇

---

## 🔐 Terminal로 ssh 공개키 만들기

먼저 `cd ~/.ssh` 를 작성하여 현재에서 ssh 폴더로 들어간다. (cd=홈)

> cd ~/.ssh

📌 꼭 ssh폴더로 들어가서 만들어야함!  
그 후 `ssh-keygen`을 작성하면 키 파일의 이름을 작성 하라고 나온다.  
(사진에서 주황색 라인 확인. 각자 알아서 지으면 됨. 나는 *gitlecture*라고 지음.)

> ssh-keygen

그 후 비밀번호를 적어라하고 한 번더 비밀번호 확인하는 메세지가 나온다. 비밀번호 없이 바로 엔터치고 넘어가도 된다.

![sshkey02](https://Yooniverse42.github.io/assets/images/posts_img/categories05-git/002-02-sshkey.png)

잘 생성됐는지 확인해보려면 `ls`(=list)

> ls

![sshkey03](https://Yooniverse42.github.io/assets/images/posts_img/categories05-git/002-03-sshkey.png)

그러면 `만든 파일명` 과 `만든 파일명.pub` 파일이 만들어진 것을 확인해 볼 수 있다.
📋
이제 깃헙에 넣을 ssh key를 불러올 것이다.(cat : concatenate 또는 catenate에서 따온 이름이다.)

> cat ~/.ssh/파일명.pub

나는 파일명을 _gitlecture_ 라고 했으므로 `cat ~/.ssh/gitlecture.pub`

그러면 **ssh-rsa ~머시기라 저시기라~ .local** 이라는 알 수 없는 키가 나온다. 이것이 ssh key! 😎  
그냥 마우스로 그 부분을 그대로 복사해도 되고

`cat 파일명.pub | pbcopy` 라고 적으면 깔끔하게 클립보드에 복사가 된다.

> cat 파일명.pub | pbcopy

나는 파일명을 _gitlecture_ 라고 했으므로 `cat gitlecture.pub | pbcopy`

⬇️⬇️⬇️

이제 GitHub에 들어가 **settings** > **SSH and GPG keys** > **new SSH key**

![sshkey04](https://Yooniverse42.github.io/assets/images/posts_img/categories05-git/002-04-sshkey.png)

Title은 아무거나 알아서 적으면 되고 key 부분에 아까 terminal에서 복사한 ssh key를 붙여넣으면 완료~~❗️👏🏻👏🏻
