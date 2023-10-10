# Request Parameter 종류
REST API의 파라미터에는 4가지 타입이 존재함.

### ⚓️ header 파라미터

- request header에 포함된 파라미터
- 보통 **인증** 혹은 **권한 부여**에 관련되어 있다.

### ⚓️ request body 파라미터

- request body에 포함된 파라미터
- 보통 JSON 형식으로 제출
- POST request일 때 사용

### ⚓️ path 파라미터

- 엔드포인트에서 쿼리문 이전의 파라미터
- 경로를 변수로서 사용하는 것

> /board/:boardID
> 

### ⚓️ query string 파라미터

- 쿼리문 내의 파라미터
- 엔드포인트가 끝난 뒤 `?` 이후의 부분
- key, value의 쌍으로 이루어짐.
- `&`를 사용하여 여러 개의 데이터를 넘길 수도 있음.

> /board?boardID=3&userID=4
> 

### ⚓️ 그래서 path, query string 중에 뭘 써야 할까..

REST API의 모범을 준수하자면 

path 파라미터는 **특정 리소스를 정의**할 필요가 있을 때!

query 파라미터는 **정렬 혹은 필터링**이 필요할 때 사용한다.

그런데, 만약 존재하지 않은 resource의 id가 들어올 경우 각각 어떻게 동작할까??

Path Variable → 404 에러 발생

Query Parameter → 따로 에러처리를 해줘야함.

⇒ 즉, **resource를 식별해야하는 상황**에서는 Path Variable이 더 적합하다.
