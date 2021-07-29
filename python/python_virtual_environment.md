## 가상 환경

- 파이썬 표준 라이브러리가 아닌 외부 패키지와 모듈을 사용하는 경우
  - `pip`를 통해 설치
- 다양한 프로젝트를 하는 경우, 각 프로젝트에서의 버전이 다를 수 있으므로, 가상환경을 통해 독립적인 패키지 관리



#### venv

- 가상 환경을 만들고 관리
- 특정 디렉토리에 가상 환경을 만듦
- git bash에 다음 메세지를 입력(생성되는데 시간이 조금 걸림)

```
$ python -m venv venv
```



#### 가상 환경 활성화/비활성화

- 활성화
  - 활성화되면 git bash 창에 `(venv)` 가 떠있는 것을 확인할 수 있음

``` 
$ source venv/Scripts/activate
```

- 비활성화

```
$ deactivate
```

- 현재 활성화 된 가상환경 확인

```
$ which python
```



#### 패키지 목록 관리 및 설치

- `pip freeze`를 활용하여 `requirements.txt`에 패키지 목록 저장

```
$ pip freeze > requirements.txt
```

- 적용하고자 하는 가상환경에 패키지 설치하는 법(`requirements.txt`)

```
$ pip install -r requirements.txt
```

