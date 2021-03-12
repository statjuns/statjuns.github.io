---
layout: post
title:  "Git 버전관리2"
subtitle: git log, git diff, file status
categories: Archive
tags: git
comments: true




---



# Git 버전 관리2



## 커밋 내용 확인

- 버전을 관리하기 위해서는 지금까지 어떤 버전을 만들었는지 확인할 수 있고 버전마다 어떤 차이가 있는지 확인할 수 있어야 한다.



### 커밋 기록 보기 - git log

- git log : commit hash(git hash), author(작성자), date(날짜), 커밋메세지, 최신 버전 등 커밋 로그 정보 확인가능
- 로그메시지가 많으면 `enter`로 다음 화면을 볼 수 있고 `Q`  를 누르면 로그화면을 빠져나온다.
- 자주쓰는 옵션
  - --stat : 커밋에 관련된 파일도 같이 출력
  - --oneline :  커밋 로그를 커밋당 한줄로 출력
  - --branches : 모든 branch의 커밋 로그 정보확인가능
  - --graph : branch의 분기과정을 graph로 나타내줌

![image-20200914235742142](/Users/seongjun/Library/Application Support/typora-user-images/image-20200914235742142.png)

- 기타 옵션

  -p : 각 커밋에 적용된 패치를 보여준다.

  --stat : 각 커밋에서 수정된 파일의 통계정보를 보여준다.

   --shortstat

   --stat 명령의 결과 중에서 수정한 파일, 추가된 라인, 삭제된 라인만 보여준다.

   --name-only : 커밋 정보중에서 수정된 파일의 목록만 보여준다.

   --name-status : 수정된 파일의 목록을 보여줄 뿐만 아니라 파일을 추가한 것인지, 수정한 것인지, 삭제한 것인지도 보여준다.

  --abbrev-commit : 40자 짜리 SHA-1 체크섬을 전부 보여주는 것이 아니라 처음 몇 자만 보여준다.

  --relative-``date : 정확한 시간을 보여주는 것이 아니라 “2 weeks ago” 처럼 상대적인 형식으로 보여준다.

   --graph : 브랜치와 머지 히스토리 정보까지 아스키 그래프로 보여준다.

   --pretty : 지정한 형식으로 보여준다. 이 옵션에는 oneline, short, full, fuller, ``format``이 있다. ``format``은 원하는 형식으로 출력하고자 할 때 사용한다.

   --oneline

   --pretty=oneline --abbrev-commit 두 옵션을 함께 사용한 것과 같다.

   -(n) : 최근 n 개의 커밋만 조회한다.

   --since, --after : 명시한 날짜 이후의 커밋만 검색한다.

   --``until``, --before : 명시한 날짜 이전의 커밋만 조회한다.

   --author : 입력한 저자의 커밋만 보여준다.

  --committer : 입력한 커미터의 커밋만 보여준다.

   --``grep : 커밋 메시지 안의 텍스트를 검색한다.

   -S : 커밋 변경(추가/삭제) 내용 안의 텍스트를 검색한다.



### 변경 사항 확인 - git diff

- git diff : 작업 트리에 있는 파일과 스테이지에 잇는 파일을 비교하거나, 스테이지에 잇는 파일과 저장소에 있는 파일을 비교해서 수정한 파일을 커밋하기 전에 최종적으로 검토할 수 있다.
- 존재하는 파일 수정 -> git diff -> 가장 최신의 버전과 어떻게 다른지 확인 가능

![git_version3](/assets/img/post_img/git_version3.png)







## 버전 단계별 파일 상태 확인

- 깃에서는 버전을 만드는 단계별로 파일 상태를 다르게 표시한다
- tracked / untracked file
  - tracked : 깃이 수정여부를 추적하는 파일,깃은 한 번이라도 커밋, 스테이징한 파일의 수정 여부를 계속 추적
  - untracked : 깃이 수정여부를 추적하지 않는 파일, 한번도 커밋되지 않은 파일
- unmodified / modified / staged - tracked 파일에서
  - unmodified : 수정 없는 파일
  - modified : 수정된 파일
  - staged : commit이 가능한 파일



```
untracked -> unmodified -> modified -> staged

->->->->->->->->->->->->->->->->->->->->->->->스테이징
		->->->->->->->->파일수정
				->->->->->->->스테이징
	<-<-<-<-<-<-<-<-<-<-<-<-<-<-커밋
```



#### .gitignore 파일로 버전관리에서 제외

- 버전 관리 중인 디렉터리 안에 버전관리를 하지 않을 특정 파일 또는 디렉토리를 .gitignore파일을 만들어 버전관리에서 제외시킬 수 있다.
- 파일명, 폴더명, 확장자(ex .png) 등 입력 가능
- .gitignore파일은 .git 폴더가 있는 최상위 폴더에 존재해야 한다. 

