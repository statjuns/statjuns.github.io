---
layout: post
title:  "자주 쓰는 linux 명령어"
subtitle:   "linux"
categories: Archive
tags: git
comments: true


---



# 자주 쓰는 linux 명령어

> <https://gomguard.tistory.com/73> 참고

- pwd : 현재위치 경로
- ls : 디렉토리 파일, 디렉토리 목록확인(list segments)
  - -l : 상세보기
  - -h : 용량 단위 표시, 그냥하면 바이트 단위로만 표시
  - -a :  숨김파일도 표시
  - -t :  추가된 순으로 표시
  - -r : 역순으로 표시
- cd 디렉토리명 : 디렉토리 이동(change directory)
  - . : 현재 디렉토리
  - .. : 상위 디렉토리
  - ~ : home 디렉토리
- mkdir 폴더명 : 폴더 생성(make directory)
  - -r : 디렉토리도 삭제
  - -p: 존재하지 않는 디렉토리의 하위디렉토리도 생성가능(mkdir -p dir/dir2)

- mv 이동할파일명 이동시킬위치 : 파일 이동(move)
- cp file cfile(경로표시) : file을 cfile로 복사(copy)
  - cp -f file cfile : 복사할 때 cfile이 존재할 경우 지우고 강제로 복사
  - cp -R dir cdir : 디렉토리 복사, 모든 파일과 하위 디렉토리를 복사
- vim 파일명 : 파일이 존재하는 경우 -파일 수정, 파일이 없는 경우 - 파일생성
- touch 파일명 : 파일의 용량이 0인 파일을 생성, 날짜 변경하는 명령어
  - touch filename : filename 파일 생성 
  - touch -c filename : filename의 시각을 현재 시각으로 변경

- rm filename: filename삭제 (remove)
  - rm -f filename : fname파일 강제 삭제
  - rm -r dirname : dirname폴더 삭제
- cat fname : 터미널에 fname 내용 출력
  - cat fname1 fname2 : 두 파일 내용 이어서 출력
  - cat fname1 fname2 | more : fname1, fname2 페이지별 출력
  - cat fname1 fname2 | head : fname1, fname2 첫 10줄만 출력
  - cat fname1 fname2 | tale : fname1, fname2 끝 10줄만 출력
- '>' '>>' : redirection, 스트림의 방향을 조정
  - cat fname1 fname2 > fname3 : fname1 fname2를 fname3에 저장
  - cat fname4 >> fname3 : >> 왼쪽 명령의 결과를 fname3에 추가
- alias : custom command 만들기
  - alias new = 'command' : command가 new로 대체됨
  - alias : 현재 alias 목록 출력
  - unalias new : new라는 alias 해제