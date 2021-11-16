## 원격 저장소에 이미 업로드 된 파일을 지우는 방법

- 로컬에서는 지우지 않고, 원격에서만 지우는 방법
- 원격 저장소에 이미 push된 파일을 ignore에 추가하는 경우 자주 사용
- 하단에 써있는 방법은 캐시를 통째로 날리는 방법

```
$ git rm -r --cached .
$ git add .
$ git commit -m "commit message"
$ git push
```

