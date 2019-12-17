### #.파일 받기(push_pull)

> 멀캠 <-> 집

### 1. 명령어

- `git clone 주소` : git허브에서 저장소의 주소를 가져와서 폴더에 복사  (해당 폴더가 없을 때, 처음 프로젝트할 시) 
- `git pull origin master` : 멀캠에서 집에서 했었던 추가했던 c.txt만 가져오고 싶으면 (프로젝트를 진행하면서 추가,수정)

### 2. 과정

​	<멀캠->집>

1. git허브에서 주소 복사

2. git clone https://github.com/geranium16/test_project.git

3. cd test_project

4. git remote -v 해보면 클론해왔기 때문에 같은 원격저장소가 연결되어있다.

5. 작업하고 다시 push

   <집->멀캠>

6. 다시 멀캠으로 가져올 때 이미 a,b는 있고 집에서 c만 추가해줬다. 따라서 push로 다 가져오는게 아니고 c만 가져와야한다.

7. git pull origin master



*log했을 때 공간이 부족해서 : 가 나오면 q 입력

*git commit에 들어갔을 때 esc 3번 누르고 :q 입력

*git 안에 새로운(다른) git 추가X