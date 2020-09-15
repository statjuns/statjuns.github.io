---
layout: post
title:  "Git 버전관리3"
subtitle: git checkout, git reset, git revert
categories: Archive
tags: git
comments: true
---



## 작업 되돌리기

- 스테이지에 올렸던 파일을 내리거나 커밋을 취소하는 등 각 단계로 돌아가는 방법

- HEAD는 현재 작업하고 있는 Branch를 가리키는 포인터 역할

  - git checkout : 작업트리에서 수정한 파일 되돌리기
  - git reset HEAD filename : 스테이징 되돌리기
  - git reset HEAD^ : 최신 커밋 되돌리기
  - git reset 커밋해시 : 특정 커밋(커밋해시를 기진 커밋)으로 되돌리기
  - git revert : 커밋 삭제하지 않고 되돌리기

  

### git checkout : 작업 트리에서 수정한 파일 되돌리기

- git checkout -- filename : filename이 modified file일 때 이전 상태로 되돌린다

### git reset HEAD filename : 스테이징 되돌리기

- git reset HEAD filename : 스테이징된 상태의 filename을 스테이징 전으로 되돌린다

### git reset HEAD^ : 최신 커밋 되돌리기

- git reset HEAD^ : 현재 HEAD가 가리키고 있는 브렌치의 최근 커밋과 스테이징을 취소하고 작업트리에만 파일이 남게 만든다.
  - --soft HEAD^ : 최근 커밋을 하기 전 상태로 되돌림
  - --mixed HEAD^ : 커밋과 스테이징을 하기 전 상태로 되돌림(디폴트)
  - --hard HEAD^ : 커밋, 스테이징, 파일수정 전 상태로 되될림, 복구 불가능
- git reset HEAD~n: HEAD가 가리키고 있는 브랜치의 최근 n개의 커밋을 취소한다.

###git reset 커밋해시 : 특정 커밋(커밋해시를 기진 커밋)으로 되돌리기

- git reset --hard 커밋해시: 해당 커밋해시를 가진 커밋으로 돌아가고 그 후의 커밋들은 삭제한다.

### git revert : 커밋 삭제하지 않고 되돌리기

- git revert 커밋해시: 커밋해시 이후의 커밋을 삭제하지 않고 해당 커밋해시로 돌아가는 새로운 커밋을 생성한다.



### 실습하기

1. git checkout

   1. 파일 수정, modified상태 만들기
   2. git checkout filename
   3. git status

2. git reset HEAD filename

   1. 파일을 수정하고 스테이징
   2. git reset HEAD filename
   3. git status

3. git reset HEAD^

   1. 파일 수정하고 커밋
   2. git reset HEAD^
   3. git status
   4. 파일 내용확인

4. git reset 커밋해시

   1. 여러개의 커밋
   2. 돌아가고 싶은 커밋의 커밋해시 복사(git log)
   3. git reset 커밋해시
   4. git log
   5. 파일 내용확인

5. git revert

   1. 여러개의 커밋
   2. 돌아가고 싶은 커밋의 커밋해시 복사(git log)
   3. git revert 커밋해시
   4. git log
   5. 파일 내용확인

   