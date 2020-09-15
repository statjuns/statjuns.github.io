---
layout: post
title:  "Gitbub 백업"
subtitle: github 연결하기, remote repository
categories: Archive
tags: git
comments: true
---



# GIthub 백업

- 깃허브는 깃을 관리할 수 있는 원격저장소를 제공하는 대표적인 서비스이다
- 깃 사용, 지역저장소 백업, 협업프로젝트, 개발 이력 기록, 다른 사람의 소스 사용, 오픈소스 참여 등을 할 수 있다.

### local, remote 연결하기

- git remote add orgin 원격저장소주소 : .로컬 저장소에서 실행하면 원격저장소 주소를 가진 원격저장소와 연결된다.
- git remote -v : 연결확인 



### 원격 저장소에 파일 올리기, 내려받기

- git branch --set-upstream-to=origin/<원격브랜치> <로컬브랜치> : '<원격브랜치>' 브랜치가 리모트의 '<로컬브랜치>' 브랜치를 ('origin'에서) 따라가도록 설정.
  - 원격 저장소에서 여러개의 브랜치가 있고 브랜치끼리 연결시킬때 사용

- git push : 연결된 원격저장소에 파일 올리기
  - git push <원격저장소> <로컬브랜치>
  - 처음 push는 git push -u orgin master와 같이 -u 옵션을 붙여야 한다.
- git pull : 연결된 원격저장소의 파일 내려받기
  - git pull orgin master : orgin(원격저장소주소 줄임말)의 내용을 master 브랜치로 가져온다.
  - 깃에서 기본 브랜치를 master라고 하는 것 처럼 기본 원격 저장소는 orgin이라는 이름을 사용한다
- push전에 pull을 해줘서 원격저장소와 커밋상태를 맞춰줘야한다.
- 깃허브 사이트에서 직접 커밋할 수도 있다



### 깃허브 SSH원격 접속하기

- SSH 접속은 프리이빗 키와 퍼블릭 키를 이용해 깃헙 서브에 해당 컴퓨터를 인증하는 방식의 접속방법이다.
- SSH 접속을 이용하면 번거로운 로그인 등을 피할 수 있다.

1. `ssh-keygen` 으로 ssh키 생성하기, 키 생성경로 메모해두기
2. 메모해둔 경로로 둘어가 퍼블릭키 내용 복사
3. 복사한 내용을 github 계정 setting의 `SSH and GPG keys` 에 들어가 add ssh key에 붙여넣고 등록
4. 이제 퍼블릭키를 등록한 컴퓨터는 ssh 주소를 이용해 로그인 없이 언제든 깃헙 서버에 접속할 수 있다.
5. 연결은 위와 같은 방법(git remote add orign 주소) 명령어를 사용하면 된다.





## 여러 컴퓨터에서 원격저장소 함께 사용 - 같은 계정으로

1. 원격저장소 복사
   - git clone 원격저장소주소 로컬저장소이름: 원격저장소 주소를 로컬저장소에 복사한다. 
   - 로컬저장소이름을 가진 폴더가 없다면 생성되고 있다면 그 안에 생성된다. 
   - 로컬저장소를 지정해주지 않으면 현재폴더에 복사된다.
2. 여러 컴퓨터에서 같은 원격 저장소를 복사하여 같이 사용할 수 있다. 

![github_colla](/Users/seongjun/Documents/statjuns.github.io/assets/img/post_img/github_colla.png)



#### 원격 브랜치 정보 가져오기

- 원격 저장소를 로컬저장소와 합치기전에 원격저장소에 어떤 변화가 있었는지 확인할 필요가 있다.
- 이런 경우에는 원격저장소의 정보만 가져올 수 있다.
- 원격저장소와 연결 후 git log명령어 결과내용에 orgin/master, HEAD->master가 생긴다
  - HEAD -> master : 해당 커밋이 지역 저장소의 최종 커밋
  - orgin/master : 헤당 커밋이 원격 저장소의 최종 커밋

- git fetch : 원격 저장소 정보 가져오기
  - 원격 저장소의 내용을 지역 저장소와 바로 합치지 않고 정보만 가져와서 검토할 수 있다
  - 원격 저장소에서 가져온 정보는 `FETCH_HEAD` 브랜치로 가져온다.