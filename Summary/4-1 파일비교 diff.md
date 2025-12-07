# 파일 비교 diff
## 1. 3영역 파일 비교 diff
**커밋 간의 파일 비교**
> * HEAD: 현 커밋
> * HEAD~, HEAD^: 하나 전 커밋
> * HEAD~~, HEAD~2, HEAD^^, HEAD^~: 두개 이전 커밋

**깃 3영역**
> * PC의 탐색기 저상소 폴더에서 보이는 파일
>  > * 작업 디렉토리의 파일
> * 저장소 하부의 .git 폴더에 정보로 숨겨진 파일
>  > * 스테이징 영역
>  > * 깃 (지역)저장소
> * 리눅스 명령어 ls로 보이는 파일
>  > * 작업 디렉토리의 파일
> * 깃 명령어 git ls-files로 보이는 파일
>  > * 스테이징 영역의 파일

**git diff**
>```
>## 스테이징 영역 기준에서 작업 디렉토리 비교
>$ git diff
>
>## 깃 저장소 HEAD 기준으로 스테이징 영역 비교
>$ git diff --staged [HEAD]
>
>## 깃 저장소 HEAD 기준으로 작업 디렉토리 비교
>$ git diff HEAD
>
>## 깃 저장소 HEAD~2 기준으로 작업 디렉토리 비교
>$ git diff HEAD~2
>```

## 2. 두 버전과의 파일 비교 diff
>```
>$ git diff HEAD~2 HEAD~
>$ git diff HEAD~ HEAD
>$ git diff HEAD~2 HEAD
>```
