# 임시 저장 stash
## 1. 깃 4영역과 임시 저장 개요
**깃 4영역**
> * 깃 4영역
>  > * 깃 3영역(working directory, staging area, git repository) + 임시저장 stash

**Git stash**
> * git stash: 놓다 남겨두다 감추다
> * 따로 안전한 곳에 저장했따가 다시 가져올수 있는 기능
> * 저장구조: 가장 최근의 내용이 가장 위에 저장되는 구조(스택 형식)
> * 필요성
>  > * 커밋할 게 없고, 작업트리가 깨끗해댜 브랜치, 커밋이동이 가능함
>  > * 수정한 내용이 있지만 커밋하지 않고 이전으로 돌아갈때 사용
> * 저장되는 내용
>  > * 작업 디렉토리 내용과 스테이징 영역 내용이 stash에 저장

## 2. 임시 저장 명령 stash
**임시저장 명령 stash**
>```
>$ git stash
>$ git stash -m '메세지'
>$ git stash save
>$ git stash save '메세지'
>```
> * 옵션
>  > * --keep-index, -k: 스테이징 영역은 제외하고 작업 폴더만 저장
>  > * --include-untracked, -u: untracked 파일도 포함해 저장
>  > * --patch -p: 변경된 모든 사항들을 저장하는 것이 아닌 자신이 stash에 저장할 것을 지정

**임시저장의 최신 저장 내용으로 다시 복원**
> * 최근 임시저장 내용을 가져와 반영, stash 목록은 그대로
>```
>## 기본으로 작업 디렉토리 내용만 다시 복사해 활용
>$ git stash apply
>
>## 스테이지 영역도 함께 복사하기 위해서는 옵션 사용
>$ git stash apply --index
>```
> * 목록 보기
>```
>$ git stash list
>```
> * 결과
>  > * stash@{0}: 가장 최신 것이 0번

**stash 확인**
> * stash 확인
>```
>## 해당 stash 항목이 생성되었을 때 커밋 자료와 최신 stash 항목간의 차이로 표시
>$git stash show
>
>## 해당 stash 항목이 생성되었을 때 커밋 자료와 해당 stsash 항목간의 차이로 표시
>## -p: 내용의 차이까지 보이기
>$ git stash show stash@{n}
>$ git stash show stash@{n} -p
>```

**임시 저장된 stash 반영**
> * 최근 또는 지정된 임시 저장소 내용을 가져와 반영하고 삭제
> ```
> $ git stash pop
> $ git stash pop stsh@{n}
> ```
> * 최근 또는 지정된 임시저장소 내용을 가져와 작업 디렉토리만 반영, stash 목록은 그대로
> ```
> $ git stash apply
> $ git stash apply stash@{n}
> ```
> * 최근 또는 지정된 임시저장소 내용을 가져와 작업 디렉토리, 스테이징 영역에 반영, stash 목록은 그대로
>```
>$ git stash apply --index
>$ git satsh apply --index stash@{n}
>```

**특정 stash 삭제와 모든 stash 삭제**
> * 최근 임시저장 내용을 삭제
> ```
> $ git stash drop
> ```
> * 지정된 임시저장 내용을 삭제
> ```
> $ git stash drop stash@{n}
> ```
> * 모든 stash 목록을 모두 제거
> ```
> $ git stash clear
> ```

**Untracked 파일 삭제**
>```
>$ git clean
>```
> * 바로 삭제 불가
> * 원하는 파일 삭제
>```
>$ git clean -i
>Would remove the following items:
>[원하는 파일]
>```
> * 무조건 삭제
> ```
> $ git clean -f
> ```
