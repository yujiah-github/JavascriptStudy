## Math
- 표준 빌트인 객체인 Math는 수학적인 상수와 함수를 위한 프로퍼티와 메서드를 제공한다.

### Math 메서드 모아보기

```javascript
원주율 값 반환
Math.PI; // 3.141592

절댓값 반환
Math.abs(-1); // 1
Math.abs(1); // 1

소수점 이하 반올림
Math.round(1.4); // 1
Math.round(1.6); // 2

소수점 이하 올림
Math.ceil(1.4); // 2
Math.ceil(1.6); // 2

소숫점 이하 내림
Math.floor(1.9);// 1
Math.floor(-1.9);// -2

제곱근 구하기
Math.sqrt(9);// 3

임의의 난수 반환
Math.random();

Const random = Math.floor((Math.random() * 10 ) +1 );
console.log(random); //1에서 10 범위의 정수

첫 번째 인수를 밑, 두 번째 인수를 지수
Math.pow(2, 8); //256
Math.pow(2, -1); //0.5

전달 받은 인수 중 가장 큰 수 반환
Math.max(1); //1
Math.max(1,2,3); //3

전달 받은 인수 중 가장 작은 수 반환
Math.min(1); //1
Math.min(1,2,3); //1
```