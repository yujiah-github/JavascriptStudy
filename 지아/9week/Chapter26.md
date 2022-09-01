## 26. ES6 함수의 추가 기능
### 26.1 함수의 구분
- ES6 이전의 모든 함수는 일반 함수로서 호출할 수 있는 것은 물론 생성자 함수로서 호출할 수 있다.

### 26.2 메서드
- ES6 사양에서 메서드는 메서드 축약 표현으로 정의된 함수만을 의미한다.
- ES6 사양에서 메서드는 메서드(이하 ES6 메서드)는 인스턴스를 생성할 수 없는 non-constructor이다.
- ES6 메서드는 자신을 바인딩한 객체를 가리키는 내부 슬롯 HomeObject를 갖는다.

### 26.3 화살표 함수
- 화살표 함수는 function 키워드 대신 화살표를 사용하여 기존의 함수 정의 방식보다 간략하게 함수를 정의할 수 있다.

#### 26.3.1 화살표 함수 정의
화살표 함수의 문법은 다음과 같다.

```javascript
const multiply = (x,y) => x * y;
multiply(2,3);

const arrow = (x,y) => { ... };

const power = x => x ** 2;
power(2);

const power = x => {return x ** 2}

const create = (id, content) => ({id, content});

const create = (id, content) => {return {id, content};};
```

### 26.4 Rest 파라미터
#### 26.4.1 기본 문법

- 메서드 내부의 this에는 메서드를 호출한 객체, 즉 메서드를 호출할 때 메서드 이름 앞의 마침표 연산자 앞에 기술한 객체가 바인딩 된다.

#### 2.3 생성자 함수 호출

- 생성자 함수 내부의 this에는 생성자 함수가 생성할 인스턴스가 바인딩된다.

#### 2.4 Function.prototype.apply/call/bind 메서드에 의한 호출

- apply와 call 메서드의 본질적인 기능은 함수를 호출하는 것이다. apply와 call 메서드는 함수를 호출하면서 첫 번째 인수로 전달한 특정 객체를 호출한 함수의 this에 바인딩한다.
- apply와 call 메서드는 호출할 함수에 인수를 전달하는 방식만 다를 뿐 동일하게 동작한다.
