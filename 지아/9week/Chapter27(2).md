## 27장 배열
### 27.6 배열 요소의 추가와 갱신
- 객체에 프로퍼티를 동적으로 추가할 수 있는 것처럼 배열에도 요소를 동적으로 추가할 수 있다.
- 존재하지 않는 인덱스를 사용해 값을 할당하면 새로운 요소가 추가된다. 이 때 length 프로퍼티 값은 자동 갱신된다.

```javascript
const arr = [0];

//배열 인덱스 1에 요소 1을 추가
arr[1] = 1;

console.log(arr); // [0,1];
console.log(arr.length); //2

arr[100] = 100;

console.log(arr); // [0,1, empty * 98, 100]
console.log(arr.length); //101
```

- 인덱스는 요소의 위치를 나타내므로 반드시 0 이상의 정수를 사용해야 한다. 만약 정수 이외의 값을 인덱스처럼 사용하면 요소가 생성되는 것이 아니라 프로퍼티가 생성된다.

### 27.7 배열 요소의 삭제
- 배열은 사실 객체이기 때문에 배열의 특정 요소를 삭제하기 위해 delete 연산자를 사용할 수 있다.

```javascript
const arr = [1,2,3];

delete arr[1];
console.log(arr); // [1, empty, 3]

//length 프로퍼티에 영향을 주지 않느다. 즉, 희소 배열이 된다.
console.log(arr.length); //3
```

- delete 연산자는 객체의 프로퍼티를 삭제한다.
- 이때 배열은 희소 배열이 되며 length 프로퍼티 값은 변하지 않는다.
- 희소 배열을 만들지 않으면서 배열의 특정 요소를 완전히 삭제하려면 Array.prototype.splice 메서드를 사용한다.

### 27.8 배열 메서드
- 배열에는 원본 배열(배열 메서드를 호출한 배열, 즉 배열 메서드의 구현제 내부에서 this가 가리키는 객체)을 직접 변경하는 메서드와 원본 배열을 직접 변경하지 않고 새로운 배열을 생성하여 반환하는 메서드가 있다.

```javascript
const arr = [1];

//push 메서드는 원본 배열을 직접 변경한다.
arr.push(2);
console.log(arr); //[1,2]

const result = arr.concat(3);
console.log(arr); //[1,2]
console.log(result); //[1,2,3]
```

### 27.8.1 Array.isArray
- Array.isArray는 Array 생성자 함수의 정적 메서드이다.

### 27.8.2 Array.prototype.indexOf
- indexOf 메서드는 원본 배열에서 인수로 전달된 요소를 검색하여 인덱스를 반환한다.

### 27.8.3 Array.prototype.push
- push 메서드는 인수로 전달받은 모든 값을 원본 배열의 마지막 요소로 추가하고 변경된 length 프로퍼티를 반환한다. push 메서드는 원본 배열을 직접 변경한다.

### 27.8.4 Array.prototype.pop
- pop 메서드는 원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환한다. 원본 배열이 빈 배열이면 undefined를 반환한다. pop 메서드는 원본 배열을 직접 변경한다.


```javascript
const arr = [1,2];

// 원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환한다.
let result = arr.pop();
console.log(result); //2

console.log(arr); //[1]
```

### 27.8.5 Array.prototype.unshift
- pop 메서드는 원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환한다. 원본 배열이 빈 배열이면 undefined를 반환한다. pop 메서드는 원본 배열을 직접 변경한다.

```javascript
const arr = [1,2];

// 원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환한다.
let result = arr.pop();
console.log(result); //2

console.log(arr); //[1]
```
