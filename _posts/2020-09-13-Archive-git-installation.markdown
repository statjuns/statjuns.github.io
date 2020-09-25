---
layout: post
title:  "Git 설치하기"
subtitle:   "운영체제별 깃 설치법"
categories: Archive
tags: git
comments: true

---



# Git

<https://git-scm.com/docs> 참고하기

- git은 linux를 개발하는 과정에서 생긴 문서관리자이다.

- git의 핵심기능은 버전관리(version control), 백업(backup), 협업(collaboration) 세가지로 나뉜다

  1. 버전관리

     - 컴퓨터로 문서작성시 '다른이름으로 저장' 하며 '초안', '수정', '최종','진짜최종...' 등으로 문서 이름을 더럽히지 않고 문서버전관리를 가능하다ㅂ

     - 깃은 문서를 수정할 때마다 언제 수정했는지, 어떤 것을 변경했는지 편하고 구체적으로 기록하기 위한 버전 관리 시스템이다.

       

  2. 백업하기

     - 깃허브(github)등 깃의 원격저장소에 깃 파일을 백업할 수 있다.
     - 원격저장소의 종류는 여러가지..

  3. 협업하기

     - 깃허브와 같은 원격저장소를 이용해 팀원들간 협업이 가능하다.

- version control -> backup -> collaboration순으로 배워야 이해가 쉽다.
- 깃을 이용할 수 있는 깃 프로그램은 여러종류가 있다(예: github desktop, tortoisegit-window, source tree 등)
- 커맨드 라인 인터페이스(Command Line Interface)는 리눅스 명령어에 익숙해야하기 때문에 GUI를 사용하는 깃프로그램보다 사용하기 어렵지만 익숙해지면 다양한 기능을 사용할 수 있기 때문에 개발자 대부부은 CLI를 사용한다.



# Git 설치하기



## Window

1. 웹브라우저에서 <https://git-scm.com> 사이트로 접속해 운영체제에 맞는 프로그램 내려 받기

2. Select Components - 기본값 선택

3. Choosing the default editor used by Git - **Use Vim** 선택

4. Adjusting your PATH environment - **Get from the command line ...** 선택

5. Choosing HTTPS transport backend - **OpenSSL** 선택

6. Configuring the line ending conversions - **..Checkout Window style, commit unix-style..** 선택

7. Configuring the terminal emulator to use with GIt Bash - **Use Window..** 선택

8. Configuring extra options - 기본값 선택

9. 설치완료 후 **Git Bash** 프로그램 실행 후 git + enter 후 옵션이 나타나면 완료

   

## Mac

1. 웹브라우저에서 <https://git-scm.com> 사이트로 접속해 운영체제에 맞는 프로그램 내려 받기

2. 설치 완료 후 terminal에서 git + enter 후 옵션이 나타는지 확인



## Git 최초 설정

- 설정파일
  1. `etc/gitconfig` 파일 : git config --system (시스템 전체 설정파일)
  2. `~/.gitconfig`, `~/.config/git/config` 파일 :  git config --global (현재 사용자에게만 적용)
  3. `.git/config` : git config --local (현재 사용중인 저장소만 적용)
- 사용자 정보 설정
  - git config --global user.name = username
  - git config --global user.email = useremali
    - --unset: 설정 삭제

