# #.Branch

> git작업 1->2->3->4->5이다. 가지처럼 뻗어나가지 못한다.
>
> 하지만 branch를 이용해 가지처럼 뻗어나가게 할 수 있다.

`git branch` : 우리가 가지고 있는 세계를 나타냄

`git branch [새로운 세계 이름]` : git branch 햇을시 여러개나옴

`git switch [새로운 세계 이름]` : 새로운 세계로 간다. (git checkout master과 같다.)

`git switch -c new` : 만들면서 이동함



그러나 두 세계는 완전 다른 세계 마스터에서 커밋한것은 마스터에만 뉴에서 커밋한것은 뉴만

log 또한 각각 분리해서 찍힘. 다만 분리하기 전꺼까지는 새로 만드는 세계가 가지고 있다.

-> 이를 통해 여러명이 작업해도 메인은 유지해나갈 수 있고 여러 방향으로 발전할 수 있다.

# #.Merge

> branch된 것을 합치는 방법

- Fast Forward Merge (갈등발생X)

`git merge [병합 할 브랜치 이름]` 하고 esc 3번 : wq (writequite) //주인이 될 세계에서

`git log --oneline --graph` : 그래프로 볼수 있다.

`git branch -d new` : 브랜치를 합병하거나 끝났으면 제거해줘야한다.

> Merge Conflict

마스터에서의 문서가 다른 세계 neo에서 수정해서 같은 문서가 다른 내용으로 저장된 경우 -> 합병했을시 단지 수정만 이루어져있을 경우 수정된 것으로 바뀜

-->이를 fast forward merge (빨리감기)라고 한다. 이는 **마스터를 안건드렸을 때**  이 후로 마스터 작업이 안됐으니 neo로 업뎃이 된다.

--> `git merge new --no-ff` : fast forward merge 막는다.

본파일도 수정되고 branch파일도 수정됬을 시 --> 깃이 문제가 발생했다고 물어본다. 이 떄 이 파일을 메모장으로 열어보면 바뀌어있다. 여기서 원하는 것만 남기고 지운다. 이상한 표시까지 포함 && git status 를 치면 merging중이라고 나옴

-> 이 후 git add README.md

-> git commit -m "Resolve merge conflict"

**동시에 작업하더라도 동일한 파일을 건드리지 않는게 중요**

**진짜 합병이 아닌 동기화 느낌이다. Merge conflict가 발생하여 master에서 고쳤을 경우 master는 바뀌고 new는 합병하기 전상태이다. **



#### Merge 시나리오 정리

##### 1. Fast Forward Merge

브랜치 분기가 일어났지만, merge 시점에서 한쪽에서만 commit들이 쌓여 있는 경우 ( ex. new에만 commit이 있고, master에는 없었을 때)

##### 2. Auto-Merge

Merge 시점에 양쪽 브랜치에 commit들이 쌓여 있지만 conflict가 발생하지 않는 경우 (바뀐 것이)

##### 3. Merge conflict 발생

merge 시점에 양쪽 브랜치에 commit들이 쌓여 있고, conflict가 발생하는 경우

- **동일 파일 내에 상충하는 내용이 있을 경우**

- **이미 올라간 파일 github에서 병합하기**

깃허브에 compare&pull request -> Able to merge. These branches can be automatically merged. == 갈등안남 -> Create pull request : merge  -> Merge pull request

--> 여기까지하면 git bash와 git hurb는 다르게 업뎃되어 있다. 따라서 git bash에서 master로 이동한 후 git pull 해주면 업뎃된다.

*참고: git push origin master = origin이라는 이름으로 master(브랜치)에 push할 것이다.

브랜치가 여러개일 경우 git push origin new 가능

lone은 아무나할수 있지만 push는 아무나할 수 없다.

settings ->collaborators 으로 동료 지정

