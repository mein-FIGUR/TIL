### CLI란?

-----

- Command Line Interface 의 약자

- 명령어(command), 경로가 중요한 역할을 함



### 경로

----

* 파일이나 폴더의 고유한 위치를 나타내는 문자열(주소)

- 경로는 운영체제에 따라 다르게 표현됨

​	windows - `C:\Users\Document` 

​	macOS - `/Users/Document` 

- `.` 현재 디렉토리
- `..` 부모 디렉토리



##### 루트 디렉토리

- 모든 파일/폴더를 담고 있는 디렉토리(폴더)

- windows의 경우 보통 C 드라이브



##### `~` 틸드(Tilde)

- 현재 사용자의 홈 디렉토리

- 현재 사용자란 컴퓨터를 킬 때 로그인 하는 계정



##### 상대 경로

- 현재 워킹 디렉토리를 기준으로 계산된 경로

- 현재 워킹 디렉토리가 `C:\Users\User\바탕화면` 이라면, `cd code`를 치면 워킹 디렉토리는 `C:\Users\User\바탕화면\code` 가 된다.

  ex) 집 주소를 생각했을 때, 실제 집 주소 : 절대 경로, "옆집" , "204호": 상대 경로



### Command

----------

##### cd

- Change Directory
- 현재 워킹 디렉토리 변경

- `cd .. ` 부모 디렉토리로 이동



##### date

- 날짜



##### cal

- MAC OS에서는 달력



##### clear

- 화면이 깨끗해짐



##### touch 

- 파일을 만들기

* `touch a.txt` a.txt 파일 생성



##### mkdir

- 디렉토리 만들기

* `mkdir hi` "hi" 폴더 생성
* `mkdir happy hacking` happy와 hacking, 2개의 폴더 생성('happy hacking'으로 하면 1개의 폴더)



##### pwd

- 현재 작업중인 폴더(디렉토리)



##### rm

- 파일 삭제

* `rm -r`  폴더 삭제
* `rm ../a.txt` 부모디렉토리의 a.txt 제거
* `rm b/c.txt` 자식디렉토리(b)의 c.txt 제거



##### cp

- 복사, 붙여넣기
- `cp a.txt b.txt` a.txt를 b.txt로 복사



##### mv

- 이동
- `mv b.txt b/b.txt` b.txt를 b 디렉토리로 이동
- `mv aa.txt c.txt` aa.txt를 c.txt로 이름바꾸기



#### tip

- 과거 명령어 불러오려면 위, 아래 방향키 활용!
- 자동 완성(tab)
- ">" 에 갇혔을 경우, `ctrl + c` 로 나올 수 있음



#### vi

- 문서 편집
- 일반모드(esc)
- 편집`i` 
- 명령(저장 후 종료 `:wq` ) 