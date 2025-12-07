# [실습] 파일 diff rm restore
## 1. 파일 비교 diff
**저장소 gifile**
>```
>$ git init gifile
>$ cd gfile
>$ echo aaa > f
>$ git add f
>$ git commit -m A
>$ git log --oneline
>```

**파일 수정 후 비교**
>```
>$ echo bbb >> f
>$ git status -s
>$ git diff
>$ git diff --staged
>$ git diff HEAD
>```

**파일 추가 후 비교**
>```
>$ git add f
>$ git status -s
>$ git diff
>$ git diff --staged
>$ git diff HEAD
>```

**파일 커밋 후 비교**
>```
>$ git commit -m B
>$ git log --oneline
>$ git status
>$ git diff
>$ git diff --staged
>$ git diff HEAD
>```

## 2. 파일 삭제 rm과 복구 restore
**명령 별칭 생성**
>```
>$ git config --global alias.별칭이름 '원명령어 --긴옵션 -짧은옵션'
>```

**파일g 삭제**
> * 파일 g를 작업 디렉토리와 스테이징 영역에서 함께 삭제
>```
>$ git rm g
>```
> * 파일 g를 스테이징 영역에서만 삭제
>```
>git rm --cached g
>```
> * 파일 g를 작업 디렉토리에서만 삭제
> ```
> $ rm g
> ```

**파일g 복원**
> * 스테이징 영역에서 파일g 복원
>```
>## 스테이징 영역에 HEAD~의 파일 g를 복사
>$ git restore --source=HEAD~ --staged g
>
>## 스테이징 영역의 파일g를 작업 디렉토리에 복사
>$ git restore g
>```
> * 깃 저장소의 최신 커밋 상태의 파일 f를 작업 디렉토리에 복원
> ```
> $ git restore --source=HEAD f
> ```
> * 깃 저장소의 최신 커밋 상태의 파일 f를 두 영역에 모두 복원
> ```
> $ git store --source=HEAD --staged --worktree f
> ```
