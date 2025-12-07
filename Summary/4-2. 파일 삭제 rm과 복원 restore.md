# 파일 삭제 rm과 복원 restore
## 1. 파일 삭제 rm
**파일 삭제**
> * 리눅스 명령 파일 삭제
>```
>$ rm [파일]
>```
> * 깃 명령 파일 삭제
>```
>## 작업 디렉토리와 스테이징 영역에서 모두 파일 삭제
>$ git rm [파일]
>
>##스테이징 영역에서만 파일 삭제
>$ git rm --cached [파일]
>```

## 2. 파일 복원 restore
**파일 복원**
>```
>## 3영역 파일 상태가 전부 다른 상태
>## 작업 디렉토리의 파일을 스테이징 영역의 파일 상태로 복구
>$ git restore [파일]
>
>## 깃 저장소의 최신 커밋 상태의 파일을 스테이징 영역에 복구
>$ git restore --staged [파일]
>$ git restore --source=HEAD --staged [파일]
>
>## 깃 저장소의 최신 커밋 상태의 파일을 작업 디렉토리와 스테이징 영역에 한번에 복구
>$ git restore --source=HEAD --staged --worktree [파일]
>
>## 깃 저장소의 최신 커밋 상태의 파일을 작업 디렉토리에 복원
>$ git restore --source=HEAD [파일]
