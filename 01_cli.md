# CLI

> 커맨드 라인 인터페이스

### 터미널 명령어들

- `ls` :  폴더 내부의 파일 & 폴더를 나열
- `pwd` : 내 현재 위치(print working dirctory)
- `~` : 홈디렉토리,시작점 기준  c/users/student *표시
- `git` --version 버전확인
- `mkdir` [폴더명]:  ㅡmake directory + 만들고자하는 폴더명
- `cd` [폴더명]: 폴더 변경
- `cd ..` : 상위 폴더로
- `cd ~` : 홈폴더
- `TAP` : 자동완성
- `git init` :깃으로 현재 폴더를 관리 (master 표시 뜸, .git파일이 생김) //git 폴더 안에 git선언x , git폴더 안에 git은 알아서 git폴더이다.
- `ls -a` : 숨김 파일까지 포기(git이 보임)
- `git status` : git의 현재 상태를 물어봄 
- `touch [파일명]` : 파일만들기 (a.txt)
- `rm [파일명]` : 파일 지우기
- `mv [이동할 파일] [이동할 곳]` : 파일 이동



### 버전관리

- `git add [파일명]`: 사진대에 파일을 올린다. --버전관리시작
-  `git config --global user.email "geranium16@naver.com"`
- `git config --global user.name "DaeHyeon Park"`
  - 컴퓨터를 처음사용할때만 필요

---------여기까지 초기설정

- 확인법: git config --global user.name or user.email
- `git commit -m "first commit"`: 사진 찍기(버전만들기) message 약자
- `git log` : 버전에 대항 정보가 나온다. (한줄: $ git log --oneline)
- `git checkout  66d4b` : 과거로 가기
- git checkout master : 현재로 돌아오기 

1. add : 사진대에 파일을 올린다.

2. commit : 사진을 찍는다. (버전관리)

3. 이전 버전을 보는 방법 

   -  66d4b 복사
   - git checkout  66d4b ->결과: ls 쓰면 1개 저장(1) -> 1개(2) 저장 했으면  (1) 상태가 보인다.
   - git checkout master ->현재로 돌아오기

   ---> 현재까지는 컴퓨터에 저장한 것임

   

### 파일올리기

- `git remote` : 원격 관리 대부분의 시작
- `git remote add origin 주소` : origin 첫ㅎ번째 저장소 이름 origin  위치에 아무 이름 써도된다. 원래   add 이름+ 주소  //프로젝트가 커지면 repository가 많아진다.
- git remote -v : 확인
- git push origin master : 올리기
- //origin = 버전이름이다. 새로 올리때마다 버전을 다르게 한다.

> $ git remote add origin https://github.com/geranium16/TIL.git



1. 어디에 올릴지 알아야한다.(https://github.com/geranium16/TIL.git)

### 파일 수정

- add(사진찍을 물건 준비) -> git commit -m(사진찍기)-> github repository만들기-> git remote add 버전 주소 (올릴 주소)=> git push(올리기) :즉 파일을 수정해도 add 똑같다.

- `git remote rename 원래이름 바꿀이름`



