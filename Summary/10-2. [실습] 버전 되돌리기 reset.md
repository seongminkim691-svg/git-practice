# [실습] 버전 되돌리기
## 1. 버전 되돌리기 reset
**기능 reset의 이해**
> * 커밋 이력에서 이전 특정 커밋으로 완전히 되돌아 가는 방법

**버전 되돌리기 reset전에 수행**
> * 버전 되돌리기 전에 현재 작업 디렉토리와 스테이징 영역을 임시 저장
> ```
> $ git stash
>
> ## 확인
> $ git stash list
>
> ## 현재 상태 확인
> $ git status
> ```

**reset 옵션**
> * reset 옵션들을 사용하여 reset 진행

**다시 원래 상태로 복원**
> * reset 이전의 커밋 ID를 저장
> ```
> $ git reset --hard ORIG_HEAD
>
> ## 이전에 stash에 저장했던 작업 불러오기
> $ git stash apply --index
> ```

## 2. checkout과 reset비교
**reset과 checkout 비교**
> * reset: 브랜치의 마지막 커밋을 수정하는 명령
> * checkout: HEAD 포인터를 브랜치 마지막 커밋 이전으로 이동하는 명령
