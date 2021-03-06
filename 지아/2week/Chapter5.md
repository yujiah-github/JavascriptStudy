## 5장 표현식과 문
### 1. 값
- 값은 **식(표현식)** 이 평가되어 생성된 결과를 말한다.
> 예) 메모리에 저장된 값 0100 0001을 숫자로 해석하면 **65**이고 문자로 해석하면 **‘A’** 이다.
- 변수는 하나의 값을 저장하기 위해 확보된 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름이기 때문에, 변수에 할당되는 것은 값이다.

### 2. 리터럴
- **리터럴**은 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법이다.
- 리터럴에는 **정수 리터럴, 부동소수점 리터럴, 2진수 리터럴, 8진수 리터럴, 문자열 리터럴, 객체 리터럴** 등이 있다.

### 3. 표현식
- 표현식은 값으로 평가될 수 있는 문이다.
- **표현식이 평가되면 새로운 값을 생성하거나 기존 값을 참조한다.**
- 표현식은 리터럴, 식별자, 연산자, 함수 호출 등의 조합으로 이루어질 수 있다.
- **값으로 평가될 수 있는 문은 모두 표현식이다.**

```javascript
//리터럴 표현식
10
'hello'

//식별자 표현식
sum
person.name
arr[1]

//연산자 표현식
10 + 20
sum = 10
sum !== 10

//함수/ 메서드 표현식
square()
person.getName()
```

### 4. 문
- **문(명령문)** 은 프로그램을 구성하는 기본 단위이자 최소 실행 단위이다.
- 문의 집합으로 이루어진 것이 **프로그램**이고 문을 작성하고 순서에 맞게 나열하는 것이 **프로그래밍**이다.
- 토큰이란 문법적 의미를 가지며, 문법적으로 더 이상 나눌 수 없는 코드의 기본 요소를 의미한다.

```javascript
var sum = 1 + 2;
```
> 하나의 문 안에 7개의 토큰이 있다.
- 문은 **선언문, 할당문, 조건문, 반복문 등**으로 구분할 수 있다.

### 5. 세미콜론과 세미콜론 자동 삽입 기능
- 세미클론은 문의 종료를 나타내므로 문을 끝낼 때는 세미클론을 붙여야한다.
- {} 와 같은 **코드 블록**은 자체 종결성을 갖기 때문에 코드 블록 뒤에는 세미클론을 붙이지 않는다.
- 자바스크립트에서는 세미콜론 자동 삽입 기능이 암묵적으로 수행되기 때문에 **세미콜론 생략이 가능하다.**

### 6. 표현식인 문과 표현식이 아닌 문
- 문에는 **표현식인 문과 표현식이 아닌 문**이 있다.
- 구별 방법은 변수에 할당을 해보는 것이다.
- 표현식인 문은 값으로 평가되므로 변수에 할당될 수 있지만, 표현식이 아닌 문은 평가할 수 없으므로 변수에 할당하면 에러가 발생한다.
