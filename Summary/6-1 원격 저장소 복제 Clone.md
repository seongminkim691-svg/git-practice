# 원격 저장소 복제 Clone
## 1. 지역에서 깃허브 원격 저장소 복제 clone
**clone 개념**
> * 원격 저장소를 지역 저장소에 복제(clone)
>  > * 공개된 저장소는 소유와 관계 엇이 누구나 가능

**원격 저장소 복제**
> * 깃허브 원격 저장소 생성 후 https 주소복사
> ```
> $ git clone [복사된 주소]
>
> ## 하부 폴더에 새로운 폴더명으로 복제
> $ git clone [복사된 주소] [새로운 폴더명]
>
> ## 원격 저장소 목록
> $ git remote
>
> ## 저장소 주소 등 원격 저장소 정보 목록 표시
> $ git remote -v
>
> ## 원격 저장소 별칭 저장
> $ git remote add origing URL
>
> ## 자세한 정보
> $ git remote show origin
>
> ## 이름 수정
> $ git remote origin [저장소 이름]
>
> ## 삭제
> $ git remote rm [저장소]
> ```
