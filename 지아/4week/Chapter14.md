## 14장 전역 변수의 문제점
- 전역 변수의 무분별한 사용은 위험하다. 전역 변수를 반드시 사용해야 할 이유를 찾지 못한다면 지역 변수를 사용해야 한다.

### 1. 변수의 생명 주기
#### 1.1 지역 변수의 생명 주기
- 변수는 생물과 유사하게 생성되고 소멸되는 생명 주기가 있다.
- 전역 변수의 생명주기는 애플리케이션의 생명 주기와 같지만 함수 내부에서 선언된 지역 변수는 함수가 호출되면 생성되고 함수가 종료되면 소멸한다.
- 따라서, 변수는 자신이 등록된 스코프가 소멸될 때까지 유효하다.
- 누군가가 메모리 공간을 참조하고 있으면 해제되지 않고 확보된 생태로 남아있게 된다.
- 호이스팅은 스코프를 단위로 동작한다.
- 이스팅은 변수 선언이 스코프의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징을 말한다.

#### 1.2 전역 변수의 생명 주기
- 전역 코드는 함수 호출과 같이 전역 코드를 실행하는 특별한 진입점이 없고 코드가 로드되자마자 곧바로 해석되고 실행된다.
- 전역 코드에는 반환문을 사용할 수 없으므로 마지막 문이 실행되어 더 이상 실행할 문이 없을 때 종료한다.
- Var 키워드로 선언한 전역 변수의 생명 주기는 전역 객체의 생명 주기와 일치한다.

### 2. 전역 변수의 문제점
#### 암묵적 결합
- 전역 변수를 선언한 의도는 전역, 즉 코드 어디서든 참조하고 할당할 수 있는 변수를 사용하겠다는 것이다.
- 이는 모든 코드가 전역 변수를 참조하고 변경할 수 있는 암묵적 결합을 허용하는 것이다.

#### 긴 생명 주기
- 전역 변수는 생명 주기가 길다. 따라서 메모리 리소스도 오랜 기간 소비한다.
- 지역 변수는 전역 변수보다 생명 주기가 훨씬 짧기 때문에 지역 변수의 상태를 변경할 수 있는 시간도 짧고 기회도 적다.

#### 스코프 체인 상에서 종점에 존재
- 전역 변수는 스코프 체인 상에서 종점에 존재하기 때문에 변수를 검색할 때 전역 변수가 가장 마지막에 검색된다.
- 따라서, 전역 변수의 검색 속도가 가장 느리다.

#### 네임스페이스 오염
- 자바스크립트 가장 큰 문제점 중 하나는 파일이 분리되어 있다 해도 하나의 전역 스코프를 공유한다는 것이다.

### 3. 전역 변수의 사용을 억제하는 방법
- 전역 변수를 반드시 사용해야 할 이유를 찾지 못한다면 지역 변수를 사용해야 한다. 변수의 스코프는 좁을수록 좋다.

#### 3.1 즉시 실행 함수
- 모든 코드를 즉시 실행 함수로 감싸면 모든 변수는 즉시 실행 함수의 지역 변수가 된다.

#### 3.2 네임스페이스 객체
전역에 네임스페이스 역할을 담당할 객체를 생성하고 전역 변수처럼 사용하고 싶은 변수를 프로퍼티로 추가하는 방법이다.

#### 3.3 모듈 패턴
- 듈 패턴은 클래스를 모방해서 관련이 있는 변수와 함수를 모아 즉시 실행 함수로 감싸 하나의 모듈을 만든다.
- 모듈 패턴은 자바스크립트의 강력한 기능인 클로저를 기반으로 동작한다.
- 캡슐화는 객체의 상태를 나타내는 프로퍼티와 프로퍼티를 참조하고 조작할 수 있는 동작인 메서드를 하나로 묶는 것을 말한다.
- 캡슐화는 객체의 특정 프로퍼티나 메서드를 감출 목적으로 사용하기도 하는데 이를 정보 은닉이라 한다.
- 자바스크립트는 접근 제한자를 제공하지 않고, 모듈 패턴은 전역 네임 스페이스의 오염을 막는 기능은 물론 한정적이긴 하지만 정보 은닉을 구현하기 위해 사용한다.

#### 3.4 ES6 모듈
- ES6 모듈은 파일 자체의 독자적인 모듈 스코프를 제공한다.
- 따라서, 모듈 내에서 var 키워드로 선언한 변수는 더는 전역 변수가 아니면 window 객체의 프로퍼티도 아니다.
- 모던 브라우저에서는 ES6 모듈을 사용할 수 있다.
- ES6 모듈은 IE를 포함한 구현 브라우저에서는 동작하지 않으며, 브라우저의 ES6 모듈 기능을 사용하더라도 트랜스파일링이나 번들링이 필요하기 때문에 아직까지는 브라우저가 지원하는 ES6 모듈 기능보다는 Webpack 등의 모듈 번들러를 사용하는 것이 일반적이다.
