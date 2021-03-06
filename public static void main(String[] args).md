## public static void main(String[] args)의 의미

- #### public![자바의 접근 제한자_public_private](http://hongong.hanbit.co.kr/wp-content/uploads/2021/09/01-%EC%9E%90%EB%B0%94%EC%9D%98-%EC%A0%91%EA%B7%BC-%EC%A0%9C%ED%95%9C%EC%9E%90_public_private.png)

  public을 포함한 접근 제한자에는 protected, private이 있다.

  

  - public은 다른 클래스, 다른 패키지 모든 곳에서 접근이 가능하다.

  

  - protected는 같은 패키지 내에서만 접근이 가능하고, 다른 패키지일 경우 해당 클래스를 상속받은 경우에 접근이 가능하다.

  

  - private는 단어 뜻 그대로 개인적인 것이라 같은 패키지 및 다른 패키지 모두 접근이 불가능하고, 같은 Class 내에서만 접근이 가능하다.

  

  - default는 같은 패키지에서만 접근이 가능하고, 클래스를 선언할 때 public(접근 제한자)이 생략되어 있을 땐 클래스는 default 접근 제한을 가진다. 클래스가 default 접근 제한을 가지면 같은 패키지에서는 아무런 제한 없이 사용할 수 있지만 다른 패키지에서는 사용할 수 없도록 제한된다.![java default 접근 제한](http://hongong.hanbit.co.kr/wp-content/uploads/2021/09/03-java-default-%EC%A0%91%EA%B7%BC-%EC%A0%9C%ED%95%9C-e1630984543712.png)

    

---

- #### static

  - static은 정적을 나타내고 '고정된'이라는 의미를 포함하고 있다.

  - static 키워드를 사용하여 Static변수와 Static메소드를 만들 수 있다 -> 정적 필드, 정적 메소드라고 부른다.

  기존의 객체의 경우 할당이 끝나면 메모리에서 사라지는 데 반해 static을 사용하면 프로그램이 종료될 때까지 유지된다. static으로 함수 또는 클래스를 선언했을 경우에는 해당 객체는 자바가 컴파일 되는 순간 정의된다. 



---

- #### void

  - void는 함수가 끝날 때 리턴 값이 없다. 
  - 일반 함수는 void를 사용해도 되고 int, char 등 다른 타입을 사용해도 문제 없이 동작한다.
  - 하지만, main함수는 void여야한다.



---

- #### main

  - 디버깅 시 제일 먼저 시작하는 코드이다.
  - 자바에서 모든 코드의 디버깅은 main에서 시작-끝을 이루게 된다.



---

- #### String[] args

  - 연속적인 문자열 데이터가 들어가는 저장공간이다.
  - String "문자열" -> 문자열의 데이터의 형태를 String이라는 클래스 변수로 정의하겠다는 의미이다.
  - [] "배열" -> [0], [1], 와 같이 인덱스로 구분되는 공간에 데이터를 넣겠다는 의미이다.
  - args -> 단순히 변수명이다.
  - 프로그램의 실행 순간에 외부의 값을 가져와서 프로그램 내 사용하고자 할 때 메모리에 저장할 공간을 미리 선언해 두는 것이다.

  

---

- #### public static void 정리

  이 메인 메서드는 자바 실행 시 제일 먼저 동작하고 어느 객체에서든 접근 가능하고 자바가ㅏ 컴파일 되는 순간 정의되는 돌려주는 값이 없는 함수이다.

