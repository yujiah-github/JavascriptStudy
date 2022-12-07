## Chapter30. Date
- 표준 빌트인 객체인 **Date는 날짜와 시간(연,월,일,시,분,초,밀리초)을 위한 메서드를 제공**하는 **빌트인 객체이면서 생성자 함수**이다.

### 1. Date 생성자 함수
- Date 생성자 함수로 생성한 Date 객체는 **내부적으로 날짜와 시간을 나타내는 정수값을 갖는다.**
- 1970년 1월 1일 00:00:00을 기점으로 **Date 객체가 나타내는 날짜와 시간까지의 밀리초**를 나타낸다.

```javascript
new Date();

new Date(86400000);
```

> 생성자 함수에 숫자 타입의 밀리초를 인수로 전달하면 **1970년 1월 1일 00:00:00을 기점으로 인수로 전달된 밀리초만큼 경과한 날짜와 시간을 나타내는 Date 객체**를 반환한다.

- Date 생성자 함수에 날짜와 시간을 나타내는 문자열을 인수로 전달하면 저장된 날짜와 시간을 나타내는 **Date 객체를 반환**한다.
- 인수로 전달한 문자열은 **Date.parse 메서드**에 의해 해석 가능한 형식이어야 한다.

```javascript
new Date(‘may 26, 2020 10:00:00’);

new Date(‘2020/03/26/10:00:00’);

new Date(2020, 2, 26, 10, 00, 00, 0);
```

> Date 생성자 함수에 **연,월,일,시,분,초,밀리초를 의미하는 숫자를 인수로 전달하면 지정된 날짜와 시간을 나타내는 Date 객체를 반환한다.** 단, 이 때 연 월은 반드시 지정해야 한다. 지정하지 않은 옵션 정보는 **0 또는 1**로 초기화된다.

### 2. Date 메서드

```javascript
Date.now(); //1970년 1월 1일 00:00:00을 기점으로 현재 시간까지 경과한 밀리초를 숫자로 반환한다.

Date.parse(); //1970년 1월 1일 00:00:00을 기점으로 인수로 전달된 지정 시간까지의 밀리초를 숫자로 반환한다.
```

```javascript
new Date(‘2020/07/24’).getFullYear(); //Date 객체의 연도를 나타내는 정수를 반환한다.

const today = new Date();

today.setFullYear(2000);
today.getFullYear();

today.setFullYear(1900, 0, 1);
today.getFullYear();

new Date(‘2020/07/24’).getMonth();

const today = new Date();

today.getMonth(0);
today.getMonth();

today.setMonth(11,1);
today.getMonth();

new Date(‘2020/07.24’).getDate();

const today = new Date();

today.setDate(1);
today.getDate();
```

> 이 외에도 **Day, Hours, Minutes, Seconds, Milliseconds,Time** 등의 메서드를 가지고 있다.
