# 방학 특강

WEB {

서버 (server) - back end : java

클라이언트 (client) - front end : jsp, html, css, js

spring controller = spring Servlet

}

도메인에는 ip주소와 명시적 도메인이 있음

유동과 고정

[http://localhost:8090/hello](http://localhost:8090/hello) + /servletPath (개발자가 정하는 거임)

[localhost](http://localhost)에 ip주소 넣을 수 있음

hello 부분은 컨텍스트(경로)라 함.

/(슬래시)까지 포함하면 path라 함.

내 ip주소 : 192.168.0.19

[http을](http://을) 프로토콜이라고 함. http프로토콜이라고 함.

public + 반환타입 + 소문자 → 메소드

윈도우  프리퍼런스 웹

${serverTime}은 EL(Expression Language)이라고 한다.

우리는 spring(frame work) WEB MVC를 하고있다~

자바 확장자 .jar

Maven(→ xml)과 gradle(→ .gradle)이 있다.

o

2점대 버전엔 xml만.

3점대 버전에서부터는 xml과 java 둘 다 쓸 수 있게됐다. xml과 java를 D(의존성)I(주입)라 한다.

라이브러리

1. 추가
2. 빈 등록 (DI) → xml, java / DI는 IOC

디펜덴시 인젝션

Date d = new(를 안 하면 메모리에 주소를 할당을 안했다 그럼 null이다.) Date( );

라이브러리를 직접 받지않고 Maven으로 받는다.

IOC는 인버전(거꾸로) 오브 컨트롤

(Inversion of Control)

[http://localhost:8090/member/insertOK.do?id=admin&pw=hi1234&name=kim&tel=010](http://localhost:8090/member/insertOK.do?id=admin&pw=hi1234&name=kim&tel=010)

/member → 컨텍스트패스

/inserOK.do → 서블릿

나머지 뒷 부분 → 파라미터

은닉할거냐 아니냐 전송량이 많냐 적냐

get방식과 post방식의 차이점은 전송 방식에 따른 파라미터가 보이냐 안 보이냐

서블릿을 깔끔하게 정리해주는게 redirect임.

VO → Value Object, DTO랑 똑같음.

MemberVO

1. 전역변수 은닉(=접근제한자의 접근을 private하게 해주는 것) (public 안됨.)
2. getters/setters 구현 (public으로 해줘야 함.)
3. 데이터 클래스화 (데이터 객체로 쓸거냐 일반 객체로 쓸거냐 데이터 객체로 쓰게 되면 ~~)
4. 디버깅용 toString 메소드를 오버라이딩

Source → generate 게터세터 → 제너레이트 해쉬코드 앤 이쿠어스 → 제너레이트 투스트링

database access object

회원DAO

[처리 기능들] —(검색, 입력, 수정, 삭제)—> DB

MemberDAO를 DI로.
