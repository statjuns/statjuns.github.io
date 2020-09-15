---
layout: post
title:  "Gitbub 협업"
subtitle: github으로 협업하기
categories: Archive
tags: git
comments: true
---

# Github 협업



## 다른 사용자와 협업하기



- 깃헙 무료계정은 최대 3명의 공동작업자를 추가할 수 있다.

1. 원격저장소의 팀장 계정이 공유할 원격저장소 `settings -> manage access` 에서 공동작업자 추가가능

2. 팀장 계정 작업환경구성
   - git config --local user.name 사용자이름
   - git config --local user.email 사용자이메일

3. 팀원 계정이 원격 저장소 복제
   - git clone 원격저장소주소
   - 복제한 저장소의 첫 커밋을 하는것이아니라면 git pull 먼저 실행
   - 커밋후 원격저장소에 업데이트 : git push -u origin master



### 협업에서 브랜치 사용

- git push origin <브랜치> : orgin에 <브랜치>브랜치를 푸시한다.
  - 웹브라우저 깃헙에서 확인하면 브랜치가 추가된 것을 확인할 수 있다.

- pull requests로 푸시한 브랜치 병합
  - 푸시한 브랜치는 pull request를 통해 병합해야 원격 저장소에 반영된다.

1. 로컬 저장소에서 새 브랜치를 푸시한다
2. 웹브라우저로 깃헙의 원격 저장소에 접속해 `pull request` 버튼을 누르고 `new pull request` 를 누르면 새로운 pull request가 생성된다.
3. 생성된 pull request는 collaborator중 한명이 승인해야 원격저장소 master브랜치에 병합할 수 있다.



