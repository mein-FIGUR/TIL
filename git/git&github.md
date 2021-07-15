# Git & Github



#### Git 과 Github는 다른가?

- git은 버전 관리, github는 구글 드라이브와 같은 온라인 공간으로 볼 수 있다.



## Git

- 로컬 저장소, 분산형 버전 관리 프로그램이다.
  - 버전 관리 : 코드의 History를 관리
  - 분산 집중형(Distributed Version Control System)
- `git init`을 통해 repository 생성

- **Repository(저장소), Commit**
  - `.git` : repository, 버전 저장소(지우면 다 날라감)
  - commit : 버전 생성
  - commit message : 버전벌 변경 사항에 대한 설명





#### Git 초기 설정

- 커밋 작성자 설정

```
$ git config --global user.email "메일주소"
$ git config --global user.name "유저네임"
```





#### Git의 작업 흐름

- working directory(가수) , staging area(무대), commit(사진촬영)

1. 워킹 디렉토리(실제 폴더)에서 작업

2. `git add`를 통해 staging area로 작업한 내용을 올림

   - `git add .` 현재 디렉토리의 모든 파일 + 하위 디렉토리

   - `git restore --staged <file>` 을 통해 add로 올린 파일들을 내릴 수 있음
   - `git restore --staged all` 을 통해 모든 파일을 내릴 수도 있음

3. `git commit`을 통해 버전을 생성

   - `git checkout`을 통해 이전 commit 이동 가능
   - `git checkout master` 을 통해 마스터로 이동 가능

4. `git push`를 통해 github에 업로드

   - commit들이 기록되어 있는 곳에 생성된 커밋들 반영





#### 파일 라이프사이클

- Working Directory의 모든 파일은 특정 상태를 가지며, git 명령어를 통해 변경
- Tracked : 1번이라도 staging area에 올라간 것들
  - unmodified : 수정되지 않음
  - modified : 수정됨
  - staged : staging area에 있는 상태
- Untracked : 1번도 staging area에 올라간 적 없음

![1. Git 시작해보기](git&github.assets/R720x0.fpng)

출처 : https://brunch.co.kr/@anonymdevoo/4





#### Github와 연결하기(push)

- github에서 repository를 생성
- `git remote add origin https://github.com/(id)/(repository_name).git` 입력
  - 로컬에서 `git remote -v` 로 연결이 잘 되었는지 확인 가능
- `git push` 로 연결
  - 처음 연결하는 경우 `git push --set-upstream origin master` 입력해서 연결하기
- git은 파일만 관리하기 때문에, 빈 폴더는 복사되지 않음





#### Github에서 불러오기 (pull)

- `git clone https://github.com/(id)/(repository_name).git`  (처음 1회만)
  - 맨 뒤에 `.`을 추가로 붙이면, repository 이름부터가 아닌 바로 내용들이 복사되어 들어옴
- 이후에는 `git pull` 





#### Tips

- `git status` 를 통해 untracked files 확인 가능
- `git log`를 통해 현재 커밋 상태 파악 가능
  - `git log --oneline` 커밋 목록 한 줄로 확인 가능
- log 내의 `origin`은 github에서의 상태를 말하고, `HEAD`는 로컬에서의 상태를 말함



### gitignore

- git으로 관리하고 싶지 않은 파일들의 리스트를 작성하여 git이 버전관리를 하지 않도록 하는 것
- 개발환경과 같은 파일들은 github에 올라가서는 안됨
- `.gitignore` 파일을 만들어서 관리



### 자주 하는 실수

----

##### git 속 git

- Git 저장소 내부에 Git 저장소가 있는 경우
- submodule 방식으로 활용이 가능하지만, 복잡함

##### 경로 공백 처리

- 공백은 `_`로 활용하는 것이 좋고, 영어로 쓰는 것이 좋음

##### 약속 

- git 명령어는 항상 .git 폴더가 있는 곳에서 하기
  - `ls -al` 로 `.git` 있는지 확인하기
- git 저장소로 활용되는 폴더에 다른 git 저장소로 옮기지 않기

##### 커밋 없는 경우

- commit이 없는 경우, push를 할 수 없음

