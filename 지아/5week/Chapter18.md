## 18장 함수와 일급 객체
### 1. 일급 객체
- 다음과 같은 조건을 만족하는 객체를 일급 객체라 하는데, 자바스크립트 함수는 해당 조건을 모두 만족하므로 일급 객체다.
1. 무명의 리터럴로 생성할 수 있다. 즉, 런타임에 생성이 가능하다.
2. 변수나 자료구조(객체, 배열 등)에 저장할 수 있다.
3. 함수의 매개변수에 전달할 수 있다.
4. 함수의 반환값으로 사용할 수 있다.

- 함수는 값을 사용할 수 있는 곳(변수 할당문, 객체의 프로퍼티 값, 배열의 요소, 함수 호출의 인수, 함수 반환문)이라면 어디서든지 리터럴로 정의할 수 있으며 런타임에 함수 객체로 평가된다.

- 일급 객체로서 함수가 가지는 가장 큰 특징은 일반 객체와 같이 함수의 매개변수에 전달할 수 있으며, 함수의 반환값으로 사용할 수도 있다는 것이다.

### 2. 함수 객체의 프로퍼티
- 함수는 객체이기 때문에 함수도 프로퍼티를 가질 수 있다.

#### 2.1 Arguments 프로퍼티
- 함수 객체의 arguments 프로퍼티 값은 arguments 객체다. 함수 외부에서는 참조할 수 없다.
- 함수 내부에서 지역 변수처럼 사용할 수 있도록 한다.

- 함수가 호출되면 함수 몸체 내에서 암묵적으로 매개변수가 선언되고 undefined로 초기화된 이후 인수가 할당된다.

- 선언된 매개변수의 개수와 함수를 호출할 때 전달하는 인수의 개수를 확인하지 않는 자바스크립트의 특성 때문에, 함수가 호출되면 인수 개수를 확인하고 이에 따라 함수의 동작을 달리 정의할 필요가 있을 수 있다. 이 때 유용하게 사용하는 것이 arguments 객체이다.

#### 2.2 Caller  프로퍼티
- Caller 프로퍼티는 ECMAScript 사양에 포함되지 않은 비표준 프로퍼티다.

#### 2.3 Length 프로퍼티
- 함수 객체의 length 프로퍼티는 함수를 정의할 때 선언한 매개변수의 개수를 가리킨다.

#### 2.4 Name 프로퍼티
- 함수 객체의 name 프로퍼티는 함수 이름을 나타낸다. Name 프로퍼티는 ES6에서 동작을 달리하므로 주의해야한다.
- 익명 함수 표현식의 경우, 함수 객체를 가리키는 식별자를 값으로 갖는다.

#### 2.5 '__proto__' 접근자 프로퍼티
- 모든 객체는 [[prototype]] 이라는 내부 슬롯을 갖는다. [[prototype]] 내부 슬롯은 객체지향 프로그래밍의 상속을 구현하는 프로토타입 객체를 가리킨다.
- __proto__ 프로퍼티는 [[prototype]] 내부 슬롯이 가리키는 프로토타입 객체에 접근하기 위해 사용하는 접근자 프로퍼티다.

#### 2.6 Prototype 프로퍼티
- Prototype 프로퍼티는 생성자 함수로 호출할 수 있는 함수 객체, 즉 constructor 만이 소유하는 프로퍼티다. 일반 객체와 생성자 함수로 호출할 수 없는 non-constructor에는 prototype 프로퍼티가 없다.
