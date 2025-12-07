# 브랜치 리베이스 rebase
## 1. 병합 rebase
**3-way 상태에서 base의 이해**
> * main과 brname라는 브랜치의 공통조상 -> base라고 칭함
>  > * Base가 커밋 B라고 가정

**선형적 통합 rebase 이해**
> * base를 수정
> * B에서 마스터의 최신 커밋인 D로 수정
> * D이후에 brname을 배치
> * 이후 fast-forward병합 수행

**rebase를 이용한 브랜치 병합 과정**
> * fast-forward 병합 방식
>  > * main 브랜치 뒤로 brname 브랜치의 이력이 이동 -> 하나의 줄기로 이어짐
>  > * 충돌 발생이 가능
>  > * 이 때 rebase만 하면 main의 위치는 그대로 유지
>  > ```
>  > $ git rebase main
>  > ```
>  > * 마스터 브랜치 위치를 변경하기 위해 fast-forward 병합 진행

## 2. 3-way, fast-forward와 rebase 비교 브랜치 리베이스 rebase
## 1. 병합 rebase
**3-way 상태에서 base의 이해**
> * main과 brname라는 브랜치의 공통조상 -> base라고 칭함
>  > * Base가 커밋 B라고 가정

**선형적 통합 rebase 이해**
> * base를 수정
> * B에서 마스터의 최신 커밋인 D로 수정
> * D이후에 brname을 배치
> * 이후 fast-forward병합 수행

**rebase를 이용한 브랜치 병합 과정**
> * fast-forward 병합 방식
>  > * main 브랜치 뒤로 brname 브랜치의 이력이 이동 -> 하나의 줄기로 이어짐
>  > * 충돌 발생이 가능
>  > * 이 때 rebase만 하면 main의 위치는 그대로 유지
>  > ```
>  > $ git rebase main
>  > ```
>  > * 마스터 브랜치 위치를 변경하기 위해 fast-forward 병합 진행

## 2. 3-way, fast-forward와 rebase 비교
**3-way merge와 rebase비교**
> * 3-way merge: 여러 분기가 생긴 변경 내용의 이력이 모두 남아 있기 때문에 이력이 복잡해짐
> ```
> $ git merge checkout main
> $ git merge [브랜치 이름]
> ```
> * rebase: 히스토리가 선형으로 단순해지고 좀 더 깨끗한 이력을 남김
>   > * 원래의 이력이 변경됨
>   > ```
>   > $ git checkout [브랜치 이름] 
>   > $ git rebase main
>   > ```

**fast-forward merge와 rebase비교**
> * fast-forward merge: 조상에 위치한 브랜치에서 선행 브랜치의 마지막으로 이동하는 병합
> * rebase: 두 갈래의 브랜치에서 병합할 브랜치 마지막 커밋을 새로운 베이스로 수정하는 병합

**git rebase [newparent] [branch]**
> * 일반적인 rebase 방법
> ```
> ## 브랜치에서 main을 rebase한 이후, 다시 main으로 이동하여 fast-forward병합 수행
> $ git checkout [브랜치]
> $ git rebase main
> $ git checkout main
> $ git merge [브랜치]
> ```
> * 다른 rebase 방법
> ```
> ## 어느 브랜치든 main [브랜치] 순서로 재배치 방법
> $ git rebase main [브랜치]
> $ git checkout main
> $ git merge [브랜치]
> ```
