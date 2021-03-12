---
layout: post
title:  "Git 버전관리1"
subtitle: git init, git add, git commit
categories: Archive
tags: git
comments: true



---



# Git 버전 관리1



## Git 저장소 만들기

- 저장소를 만들고 그곳에서 깃을 초기화 하면 해당 디렉토리에 있는 파일들을 버전관리할 수 있다.

1. mkdir dirname : 폴더 만들기

2. cd dirname : dirname 으로 이동

3. git init : 깃 저장소 초기화

4. ls –la : .git 폴더가 만들어졌는지 확인



## 버전 만들기

### 깃 버전

- 깃에서 버전이란 문서를 수정하고 저장할 때마다 생기는 것이다
- 파일을 다른 이름으로 저장(초안, 수정, 최종, 진짜최종..등)해 버전을 만드는 것보다 쉽게 버전을 만들고 만든 시간과 수정내용까지 기록할 수 있는 것이 깃 버전관리 시스템이다
- 깃을 이용하면 이름을 그대로 사용하고 파일에서 무엇을 변경했는지 변경 시점마다 저장 가능하다



### 스테이지와 커밋 

- 깃은 작업 디렉터리(작업 트리) 영역. 스테이지(stage,staging area) 영역, 저장소(repository)개념을 이용해 버전을 관리한다.
- 작업 디렉토리는 우리가 만드는 폴더를 생각하면 된다.
- 스테이지와 저장소는 '.git'폴더안에 존재 한다.
- 스테이지는 버전으로 만들 파일이 대기하는 곳이다.
- 저장소는 스테이지에 있던 파일들을 버전으로 만들어 저장하는 곳이다.
- 스테이지와 커밋이 동작하는 과정은 다음과 같다.
  1. 작업 트리에서 문서를 수정
  2. 수정한 파일 중 버전으로 만들고 싶은 것을 스테이징 영역에 추가(git add filename..)
  3. 스테이지에 있던 파일을 저장소로 커밋(git commit)



![areas](/assets/img/post_img/areas.png)

(source: git doc)



### snapshot

- 저장소에는 폴더의 스냅샷(현재의 상태)들을 연속적으로 저장한다.

- Git의 스냅샷은 HEAD가 가리키는 커밋을 기반으로 스냅샷(사진)을 찍고 이를 스테이지 영역과 비교해 새로운 커밋으로 기록한다.

- 이러한 방식은 다른 버전관리 프로그램과 달리 빠르게 버전의 차이점을 처리하고, 용량을 적게 사용합니다.

![snapshow](/assets/img/post_img/snapshow.png)





### 버전관리 실습

#### 파일 수정 (vim)

1. git status : 현재 깃 상태 확인
   - on branch master - 현재 master브랜치에 있다. (브랜치는 저장소안의 폴더로 생각)
   - No commits yet : 아직 커밋한 파일이 없음
   - nothing to commit : 커밋할 파일이 없음 (add된 파일이 없음)
2. vim hello.txt - 아무 내용 입력 후 저장
3. git status 
   - untracked file : 아직 작업트리에만 존재하는 파일

#### 파일 스테이징(git add)

4. git add hello.txt : hello.txt파일을 스테이지에 올림
5. git status
   - changes to be commited : 스테이지에 파일이 있음(커밋될 수 있는 change)

#### 파일 커밋(git commit)

6. git commit -m "message1" 

   - -m commitmessage : 커밋과 함께 저장할 메모저장 가능

7. git status

   - 모두 커밋되어 처음 상태로 돌아감

8. git log : 저장소에 저장된 버전을 확인

9. git commit -am 'commitmessage' : 스테이징과 커밋을 한번에 할 수 있다. 하지만 한 번이라도 커밋한 적이 있는 파일을 다시 커밋할 때만 사용할 수 있다.

10. git commit -amend : 커밋 메시지 수정하기

    

    



