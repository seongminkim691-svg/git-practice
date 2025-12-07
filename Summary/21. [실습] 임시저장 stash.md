# [실습] 임시 저장 stash
## 1. 임시 저장 기초
**임시 저장 기초**
> * 저장소 생성 후 커밋
> * 파일 f가 3영역이 모두 다르고 추적되지 않는 파일 g생성
> ```
> ## 옵션 -u가 없으면 untracked file은 그대로 남음
> $ git stash
>
> ## 저장에서 삭제 되지 않고 복사
> ## 스테이징 영역은 복원 불가
> $ git stash apply
>
> ## 스테이징 영역도 함께 복원
> $ git stash apply --index
> ```

## 2. 임시 저장 관련 다양한 명령
**Save로 저장**
> * --keep-index, -k
>  > * 스테이징 영역은 SA 제외하고, 작업 디렉토리만 저장
> * --include-untracked, -u
>  > * Untracked 파일도 포함해 저장

**커밋과 임시 저장과의 비교**
>```
>$ git stash show -p
>
>## 커밋과 지정한 임시 저장과의 비교
>$ git stash show -p stash@{1}
>```

**옵션 -m으로 메세지 저장**
>```
>$ git stash -m [메세지 내용]
>```

**임시 저장 목록 삭제**
> * drop: 최신이나 지정한 임시 저장 삭제
> * clear: 모든 임시저장 삭제
