# Nest 커밋 오류

## master브랜치 main으로 바꾸기

- [https://blog.outsider.ne.kr/1598](https://blog.outsider.ne.kr/1598)

> git branch -m master main
> 

> git fetch origin
> 

> git branch -u origin/main main
> 

> git remote set-head origin -a
> 

## 커밋 목록에 안 뜨는 오류

‘깃 폴더 커밋’ 검색 후, 최상단에 뜨는 게시글

- [https://tychejin.tistory.com/357](https://tychejin.tistory.com/357)

1. 업로드할 폴더의 상위 폴더로 이동
2. 깃을 사용할 수 있도록 폴더를 초기화

> git init
> 
1. 상태 변경이 필요한 파일이 있는지 확인

> git status
> 
1. add 명령어를 실행하여 tracked 파일로 변경

> git add 폴더명
> 

이렇게 했는데도 에러가 뜬다.

> error: 'nestboard/' does not have a commit checked out
> 

이런 에러가 뜬다면 하위 폴더에서 `.git`을 초기화해준다.

 하위 폴더로 이동한 다음, 다음 명령어를 쳤더니 해결!

> rm -rf .git
>
