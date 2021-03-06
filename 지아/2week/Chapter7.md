## 7장 연산자
- 연산자는 하나 이상의 표현식을 대상으로 **산술, 할당, 비교, 논리, 타입, 지수 연산** 등을 수행해 하나의 값을 만든다. 이 때 연산의 대상을 **피연산자** 라고 한다.
- 피연산자는 값으로 평가될 수 있는 표현식이어야 한다. 그리고 연산자의 조합으로 이뤄진 연산자 표현식도 값으로 평가될 수 있는 표현식이다.
- 피연산자는 연산의 대상이 되어야 하므로 값으로 평가할 수 있어야 한다.

### 1. 산술 연산자
- 산술 연산자는 피연산자를 대상으로 수학적 계산을 수행해 새로운 숫자 값을 만든다.
- 산술 연산자는 피연산자의 개수에 따라 이항 산술 연산자와 단항 산술 연산자로 구분할 수 있다.

#### 1.1 이항 산술 연산자
- 어떤 산술 연산을 해도 피연산자의 값이 바귀는 경우는 없고 언제나 새로운 값을 만든다.

#### 1.2 단항 산술 연산자
- 단항 산술 연산자는 1개의 피연산자를 산술 연산하여 숫자 값을 만든다.
증가/감소 연산자는 피연산자의 값을 변경하는 부수 효과가 있다.

- 피연산자 앞에 위치한 전위 증가/감소 연산자는 먼저 피연산자의 값을 증가/감소시킨 후, 다른 연산을 수행한다.
- 피연산자 뒤에 위치한 후위 증가/ 감소 연산자는 먼저 다른 연산을 수행한 후, 피연산자의 값을 증가/감소 시킨다.

- 숫자 타입이 아닌 피연산자에 + 단항 연산자를 사용하면 피연산자를 숫자 타입으로 변환하여 반환한다.

- '-' 단항 연산자는 피연산자의 부호를 반전한 값을 반환한다. + 단항 연산자와 마찬가지로 숫자 타입이 아닌 피연산자에 사용하면 피연산자를 숫자 타입으로 변환하여 반환한다.

#### 1.3 문자열 연결 연산자
- 연산자는 피연산자 중 하나 이상이 문자열인 경우 문자열 연결 연산자로 동작한다.

### 2. 할당 연산자
- 할당 연산자는 우항에 있는 피연산자의 평가 결과를 좌항에 있는 변수에 할당한다. 할당 연산자는 좌항의 변수에 값을 할당하므로 변수 값이 변하는 부수 효과가 있다.
- 할당문은 값으로 평가되는 표현식인 문으로서 할당된 값으로 평가된다.

### 3. 비교 연산자
#### 3.1 동등/일치 비교 연산자
- 동등 비교 연산자와 일치 비교 연산자는 좌항과 우항의 피연산자가 같은 값으로 평가되는지 비교해 불리언 값을 반환한다.
- 동등 비교 연산자는 좌항과 우항의 피연산자를 비교할 때 먼저 암묵적 타입 변환을 통해 타입을 일치시킨 후 같은 값인지 비교한다.
- 일치 비교 연산자는 좌항과 우항의 피연산자가 타입도 같고 값도 같은 경우에 한하여 true를 반환한다.

#### 3.2 대소 관계 비교 연산자
- 대소 관계 비교 연산자는 피연산자의 크기를 비교하여 불리언 값을 반환한다.

### 4. 삼항 조건 연산자
- 삼항 조건 연산자 