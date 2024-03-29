p.12, 13, 21, 22

- println은 괄호( ) 안의 내용을 콘솔 화면에 표시한 후 줄 바꿈 (줄 바꿈 문자를 출력)하는 프로그램에 ‘부품’이다. 이런 부품을 메서드라고 한다.
- ( ) 안을 공란으로 둘 수 있는 것은 println()뿐이다. print에선 공란을 허용하지 않는다.
- 정수형
- byte형, short형, int형, long형 등이 있다.
- 실수형
- float형, double형 등이 있다.
- [System.in](http://System.in)은 키보드와 연결된 표준 입력 스트림standard input stream(STDIN)이다.
- final이 아닌 일반 변수와 쉽게 구분하기 위해 final 변수의 이름은 대문자를 사용하는 것이 일반적이다.
- 선언 시에 초기화하지 않은 final 변수에는 한 번만 값을 대입할 수 있다.
- if문과 switch문은 프로그램의 흐름을 분기한다는 점에선 동일하다. 따라서 이 둘을 합쳐서 선택문이라고 부른다.

{

  8진수 12는 10진수로 012 이다.
  10진수 12는 10진수로  12 이다.
  16진수 12는 10진수로 0x12 이다.

}

## 정수 접미어(integer type suffix)

- 정수 리터럴은 기본적으로 int형이지만, long형을 사용할 때에는 l 또는 L의 정수 접미어를 뒤에 붙여 사용한다. 예를 들어 5는 int형이지만 5l(또는 L)은 long형이다.

## 10진 정수 리터럴

- 10이나 57 등 일상생활에서 사용하는 10진수를 표기하는 정수 리터럴이다.

## 8진 정수 리터럴

- 10진 정수 리터럴과 구별할 수 있게 앞에 0을 붙여 두 자리 이상으로 표기한 정수 리터럴이다.
- 이번 프로그램에서 사용하는 12는 10진 정수 리터럴이고 012는 8진 정수 리터럴이다.

## 16진 정수 리터럴

- 앞에 0x 또는 0X를 붙여서 표기한다. 10진수의 10~15에 해당하는 A~F는 대문자와 소문자 모두 사용할 수 있다.
- 이번 프로그램의 0x12가 16진 정수 리터럴이다.
- 자바 SE8 버전부터는 2진 정수 리터럴도 사용할 수 있다.
- 앞에 0b 또는 0B를 붙여서 2진수를 표기한다.

## printf 메서드

- System.out.printf는 형식을 제어해서 화면에 표시하는 메서드이다.
- %d는 ‘쉼표 다음에 오는 정수를 10진수로 표시해주세요’라고 지시하는 형식 문자열이다.
- %는 형식 지정을 위한 시작 문자이고 변환 문자 d는 ‘10진수'라는 의미의 decimal의 머릿 글자이다.
- println 메서드와 달리, printf 메서드는 줄 바꿈 문자를 출력하지 않는다.
- % 기호 자체를 출력하고 싶을 때는 %%라고 표기해야 한다.

| %d | 10진수로 출력 |
| --- | --- |
| %o | 8진수로 출력 |
| %x | 16진수로 출력 (a~f는 소문자) |
| %X | 16진수로 출력 (A~F는 대문자) |
| %f | 소수점 형식으로 출력 |
| %c | 문자로 출력 |
| %s | 문자열로 출력 |

## 부동소수점형

- 실수를 나타내는 부동소수점형은 float형과 double형이 있다.
- 부동소수점형의 표현 범위는 크기와 정밀도에 제한을 받는다.
- float형과 double형의 정밀도(소수점 이하 자릿수)가 다르다는 것을 알 수 있다.
- 57.3처럼 실수를 나타내는 상수를 부동소수점 리터럴이라 한다.
- 자료형을 지정하는 것이 부동소수점 접미어이다.
- float형을 지정하는 것은 f와 F이고 double형을 지정하는 것은 d와 D이다. 지정하지 않는 경우에는 double형으로 간주한다.

| float | 약 6~7자리 |
| --- | --- |
| double | 약 15자리 |

## 이진 숫자 승격

- 형 변환을 이진 숫자 승격이라 한다.
- 산술 연산의 대상이 되는 피연산자의 자료형이 서로 다를 때에 자료형이 작은 피연산자가 자료형이 큰 피연산자로 변환된 상태에서 연산한다.
- 여기서 ‘크다'라는 표현은 논리적인 크기를 의미하는 게 아닌 double형이 소수점 이하 값을 저장하고 있어 int형보다 ‘여유가 있다'(크다)라는 의미이다.

## 정수형

- char형
- 문자를 나타내는 자료형이다.
- 양수만 표시할 수 있다는 점에서 다른 정수형과 성질이 다르다.
- 0과 양수를 표현하는 부호 없는 정수형이다.
- byte형/short형/int형/long형
- 정수를 나타내는 자료형이다.
- 음수, 0, 양수를 표현하는 부호 있는 정수형이다.

| Char | 16 bit |
| --- | --- |
| Byte | 8 bit |
| Short | 16 bit |
| int | 32 bit |
| Long | 64 bit |

## 캐스트 연산자

- (int)5.7은 double형의 유동소수점 리터럴인 5.7에서 소수점 이하를 버린 int형인 5를 생성한다.
- (double)5에선 int형인 정수 리터럴 5를 double형의 부동소수점 리터럴인 5.0을 생성한다.
- 이때 이루어지는 형 변환을 캐스트라고 한다.
- ( )은 우선적으로 연산을 하라는 의미가 아닌, 캐스트 연산자라 불리는 연산자이다.

## 확장 표기(escape sequence)

| \b | 백스페이스 | 표시 위치를 직전 위치로 이동 |
| --- | --- | --- |
| \f | 폼피드 | 다음 페이지의 처음으로 이동 |
| \n | 줄 바꿈 | 줄 바꿈해서 다음 줄의 처음으로 이동 |
| \r | 캐리지 리턴 | 현재 줄의 처음 위치로 이동 |
| \t | 수평 탭 | 다음 수평 탭 위치로 이동 |
