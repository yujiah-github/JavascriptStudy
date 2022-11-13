## 28장 Number

- 표준 빌트인 객체인 Number는 원시 타입인 숫자를 다룰 때 유용한 프로퍼티와 메서드를 제공한다.

### 1. Number 생성자 함수

- 표준 빌트인 객체인 Number 객체는 생성자 함수 객체이다. 따라서 New 연산자와 함께 호출하여 Number 인스턴스를 생성할 수 있다.

### 2. Number 프로퍼티

- Number.ESSILON, Number.MAX_VALUE, Number.MIN_VALUE, Number.MAX_SAFE_INTEGER, Number.MIN_SAFE_INTEGER, Number.POSITIVE_INFINITY, Number.NEGATIVE_INFINITY, Number.NaN 등이 있다.

### 3. Number 메서드
- Number.isFinite, Number.isInteger, Number.isNaN, Number.isSafeInteger, Number.prototype.toExponential, Number.prototype.toFixed, Number.prototype.toPrecision, Number.prototype.toString 등이 있다.

```javascript
Number.isFinite(0);

Number.isFinite(NaN);

Number.isInteger(0);


Number.isNaN(undefined);

(77.1234).toExponential();

(12345.6789).toFixed();

(10).toString();
```
