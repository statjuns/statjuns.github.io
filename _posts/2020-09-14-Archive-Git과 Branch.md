---
layout: post
title:  "Git과 Branch"
subtitle: git branch 
categories: Archive
tags: git
comments: true

---



# Git과 Branch

> <https://git-scm.com/book/ko/v2> 참고

- 깃을 처음 시작하면 master라는 branch가 만들어 진다.
- 브랜치를 통해 기존에 저장한 파일을 master브랜치에 그대로 유지하면서 기존 파일 내용을 수정하거나 새로운 기능을 구현할 파일을 만들 수 있다.
- 개발할 때 코드를 통쨰로 복사해서 다른 내용의 코드를 만들어야 하는 상황을 복사하지 않고 가능하게 만들어 준다.





### Branch 만들기

- git branch : 브랜치 목록 확인

- git branch 브랜치이름 : 브랜치이름의 브랜치를 만듦

```
git branch testing
git checkout testing
```



![head-to-master](/assets/img/post_img/head-to-master.png)



### Branch 이동

- git checkout : 브랜치 사이 이동하기
- git checkout -b branchname : branchname을 만들고 이동 (git branch branchname + git checkout branchname)

```
git commit -am "made change"
```



![advance-testing](/assets/img/post_img/advance-testing.png)



```
git branch testing
git checkout testing
git commit -am "made change"
git checkout master)
```

![checkout-master](/assets/img/post_img/checkout-master.png)



```
git branch testing
git checkout testing 
git commit -am "made change"
git checkout master
git commit -am "made other change"
```



![advance-master](/assets/img/post_img/advance-master.png)

#### 실습

1. manual 폴더만들고 깃 저장소 초기화

2. 커밋 3번 하기

3. 브랜치 여러개 만들기

   

## Branch 정보 확인하기

- git log --oneline --branches : 각 브랜치의 커밋을 함께 볼 수 있다.
- git log --oneline --branches --graph : 각 브랜치의 커밋간의 관계를 보기 쉽게 그래프 형태로 표시
- git log master..testing : master branch에는 없고 testing branch에만 있는 커밋을 보여준다.
- git log testing..master : testing branch에는 없고 master branch에만 있는 커밋을 보여준다.

​		

#### 실습

4. 위의 실습상황에서 다른 브랜치로 이동 후 커밋하기
5. 브랜치간의 차이 확인하기

## Branch 병합하기

- 각 브랜치에서 작업하다 어느 시점에서 브랜치 작업을 마무리하고 기존의 브랜치와 합쳐야하는 상황 발생한다.

- git merge를 이용하는 방법과 git rebase를 이용하는 방법이 있다.

  - git merge branchname : HEAD가 가리키는 branch와 branchname을 병합(3-way)
  - git rebase branchname : HEAD가 가리키는 branch와 branchname을 병합(2-way)

- 병합할 때 파일 수정 위치에 따라 충돌이 발생할 수 있다.

  1. 서로 다른 파일 병합

  2. 같은 파일 다른 위치 수정 후 병합

  3. 같은 파일 같은 위치 수정 후 병합

     - 충돌 발생

       ![merge_collision](/assets/img/post_img/merge_collision.png)

       <<<<<<< HEAD

       현재 HEAD가 가리키고 있는 브랜치의 내용

       =============

       병합할 브랜치의 내용

       \>>>>>>>> branchname

     - 충돌이 발생하면 양쪽 브랜치의 내용을 참고하며 수정 후 구분선을 삭제후 다시 저장

     - 저장한 파일을 커밋하면 완료

     - 병합 및 충돌 해결프로그램 사용가능 

       - p4merge, meld, kdiff3 등
       - [p4merge설치법](https://teddylee777.github.io/git/study-git-2)

- git merge를 이용하면 옆의 그림과 같이 master, iss53이 가리키고 있는 커밋(c3, c4)과 두 개의 브랜치의 공동 조상 커밋(c2)를 합치는 새로운 커밋을 만든다( c6)

- 만약 master 브랜치가 iss53브랜치가 분기된 커밋에서 새로운 커밋이 만들어지지 않았다면 master브랜치는 iss53브랜치로 fast-forward(빨리감기)한다.

![branch_merge](/assets/img/post_img/branch_merge.png)





- git rebase는 merge와 달리 c3,c4,c2를 합치지는 새로운 커밋으로 합치지 않고 c3 앞에 c4를 복사해 합친다 

- rebase하고 master로 돌아가서 merge로 master를 옮겨 줘야한다(fast-forward)

- 시간 순서대로 자연스럽게 합치는 장점이 있다.

![branch_rebase](/assets/img/post_img/branch_rebase.png)



###Branch 삭제하기

- 병합 후 더 이상 사용하지 않는 브랜치는 삭제가능하다
- git branch -d branchname: git branch의 -d 옵션을 사용하면 삭제가능

#### 실습

1. 폴더만들고 깃 초기화
2. 마스터브랜치에서 텍스트파일 만들고 커밋
3. 다른 브랜치 만들기
4. 마스터브랜치에서 텍스트파일 수정
5. 다른브랜치로 이동후 같은위치 수정
6. 마스터브랜치로 이동후 병합
7. 충돌발생, 파일 수정후 다시 커밋 후 충돌해결
8. 병합된 브랜치 삭제





##Branch 관리

### 브랜치에서 checkout reset

- git reset 커밋 해시 : HEAD가 기리키고 있는 branch를 커밋해시가 가리키는 커밋으로 이동시킨다. 
- branch안에서만 커밋을 이동할 수 있을 뿐만아니라 branch간에도 커밋을 이동할 수 있다.

### 수정 중인 파일 감추기, 되돌리기

- git stash : modified file들을 잠시 unmodfied파일로 감춰둘 수 있다 
  - 현재 작업중인 파일들과 관련없는 작업을 따로 할때 실수로 관련 없는 파일들이 커밋되는 것을 방지할 수 있다.
  - 현재 시점의 modified file들을 unmodified file로 바꾼다
- git stash pop : stash 목록에서 가장 최근의 항목 목록에서 삭제 후 되돌린다
  - git stash list : stash 목록 출력
- git stash apply : stash 목록에서 가장 최근의 항목 목록에서 삭제 하지않고 되돌린다
- git stash drop : stash 목록에서 가장 최근의 항목을 삭제한다.



### git cherry-pick

- git cherry-pick commit1 commit2 ... : 현재 위치(HEAD) 아래에 있는 일련의 커밋들에대한 복사본을 만들겟다는 것을 간단히 줄인말이다.
- 다른 브랜치에 있는 커밋들을 rebase처럼 복사해온다
- Git 체리-픽은 여러분이 원하는 커밋이 무엇인지 알때(각각의 해시값도) 아주 유용하다,



### Interactive rebase

- git cherry-pick에서 가져올 커밋의 커밋해시를 정확하게 모를 때 사용할 수 있다.

- git rebase -i : 

  - git은 리베이스의 목적지가 되는 곳 아래에 복사될 커밋들을 보여주는 vim을 띄운다. 각 커밋을 구분할 수 있는 각각의 해시들과 메시지도 보여준다.

    ![interactive_rebase](/assets/img/post_img/interactive_rebase.png)

