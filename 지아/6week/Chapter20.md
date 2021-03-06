## 20장 Strict mode
### 1. Strict mode란?
- 개발자의 의도와는 상관없이 발생한 암묵적 전역은 오류를 발생시키는 원인이 될 가능성이 크다. 따라서, 반드시 var, let, const 키워드를 사용하여 변수를 선언한 다음 사용해야한다.
- 그러나, 오타나 문법 지식의 미비로 인한 실수는 발생하기 마련이므로, 잠재적인 오류를 발생시키기 어려운 개발 환경을 만들고 그 환경에서 개발하는 것이 좀 더 근본적이 해결책이라고 할 수 있다.
- 이를 지원하기 위해 ES5부터 **strict mode**가 추가되었다.
- ESLint 같은 린트 도구를 사용해도 strict mode와 유사한 효과를 얻을 수 있다. **린트 도구**는 정적 분석 기능을 통해 소스코드를 실행하기 전에 소스코드를 스캔하여 문법적 오류만이 아니라 잠재적 오류까지 찾아내고 오류의 원인을 리포팅해주는 유용한 도구다.

### 2. Strict mode의 적용
- Strict mode를 적용하려면 전역의 선두 또는 함수 몸체의 선두에 **‘use strict’;**를 추가한다. 전역의 선두에 추가하면 스크립트 전체에 strict mode가 적용된다.

### 3. 전역에 strict mode를 적용하는 것은 피하자
- 전역에 적용한 것은 스크립트 단위로 적용된다. 그러나, non-strict mode 스크립트와 혼용하는 것은 오류를 발생시킬 수 있으므로 **즉시 실행 함수로 스크립트 전체를 감싸서 스코프를 구분하고 즉시 실행 함수의 선두에 strict mode를 적용한다.**

### 4. 함수 단위로 strict mode를 적용하는 것도 피하자
- 어떤 함수는 적용하고, 어떤 함수는 적용하지 않는 방식이면 문제가 발생할 수 있으므로 **strict mode** 는 즉시 실행 함수로 감싼 스크립트 단위로 적용하는 것이 바람직하다.

### 5. Strict mode가 발생시키는 에러
#### 5.1 암묵적 전역
- 선언하지 않는 변수를 참조하면 **referrenceerror**가 발생한다.

#### 5.2 변수, 함수, 매개변수의 삭제
- Delete 연산자로 변수, 함수, 매개변수를 삭제하면 **syntaxerror**가 발생한다.

#### 5.3 매개변수 이름의 중복
- 중복된 매개변수 이름을 사용하면 **syntaxerror**가 발생한다.

#### 5.4 with문의 사용
- with문은 동일한 객체의 프로퍼티를 반복해서 사용할 때, 객체 이름을 생략할 수 있어서 코드가 간단해지는 효과가 있지만 성능과 가독성이 나빠지는 문제가 있다. 따라서 with문을 사용하면 **syntaxerror**가 발생한다.

### 6. Strict mode 적용에 의한 변화
#### 6.1 일반 함수의 this
- Strict mode에서 함수를 일반 함수로서 호출하면 this에 undefined가 바인딩된다. 생성자 함수가 아닌 일반 함수 내부에서는 this를 사용할 필요가 없기 때문이다.

#### 6.2 Aruments 객체
- Strict mode에서는 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에 반영되지 않는다.
