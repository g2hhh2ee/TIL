JavaScript Arrays 배열

## **배열의 개요**

배열은 값의 순서 있는 집합이다.

```jsx
// To make an empty array
let students = [];

// An Array of strings
let colors = ["red", "orange", "yellow"];

// An array of numbers
let lottoNums = [19, 22, 56, 12, 51];

// A mixed array
let stuff = [true, 68, "cat", null];
stuff[2]; // 68
stuff[2][1]; // 8 - 첫번째는 인덱스, 두번째는 요소의 자릿수
let days = ["Mon", "Tue", "Wed"];
days[2][0] = "W"
```
**인덱스는 배열의 요소가 위치한 자릿수이고, 문자열과 마찬가지로 0부터 시작한다.** 

Each element has a corresponding index. (counting starts at 0)

인덱스는 배열의 요소가 위치한 자릿수이고, 문자열과 마찬가지로 0부터 시작한다. 

인덱스로 배열의 요소를 출력할 수 있다.

```jsx
let colors = ["red", "orange", "yellow"];
colors[2] = "green";
colors; // ['red', 'orange', 'green'];
colors[5] = "gray";
colors; // ['red', 'orange', 'green', empty*2, 'gray'];
```

배열은 문자열과 달리 요소 값을 바꿀 수 있다.

## **배열의 내장 객체**

- `push` : 배열의 끝에 요소를 추가한다. add to **end**
- `pop` : 배열의 끝의 요소를 제거한다. remove from **end → 맨 끝 요소 반환함.**
- `shift` : 배열의 첫 번째 요소를 제거한다. remove from **start**
- `unshift` : 배열의 첫 번째 요소를 추가한다.add to **start → 배열의 시작에 새 요소 추가함.**

```jsx
// push
let movieLine = ["tom", "nancy"];
movieLine.push("oliver", "eva"); // 4
movieLine; // ["tom", "nancy", "oliver", "eva"];

// pop
movieLine.pop(); // "eva"
movieLine; // ["tom", "nancy", "oliver"];
let person = movieLine.pop();
person; // "oliver"
movieLine; // ["tom", "nancy"];

// shift
movieLine; // ["tom", "nancy", "oliver", "eva"];
movieLine.shift(); // "tom"
movieLine; // ["nancy", "oliver", "eva"];
let nextPatron = movieLine.shift();
nextPatron; // "nancy";
movieLine; // ["oliver", "eva"];

// unshift
movieLine.unshift("VIP"); // 3
movieLine; // ["VIP", "oliver", "eva"];

// Excercise
const planets = ['The Moon','Venus', 'Earth', 'Mars', 'Jupiter'];
planets.shift();
planets.push("Saturn");
planets.unshift("Mercury");
```

- `concat` : 두 개의 배열을 이어붙인다.→ 두 배열 이어서 세 번째 배열 만듦.
- `includes` : 배열에 특정 값이 포함되어 있는지 알려준다. → returns true or false(boolean값 반환)
- `indexOf` : 배열에 특정 값의 인덱스를 알려 준다.
- `reverse` : 원본 배열의 값들의 인덱스를 거꾸로 바꾼다.
    - 첫 번째 배열 값을 마지막으로, 마지막 배열 값을 첫 번째로 바꾼다.

```jsx
// concat
let cats = ["blue", "kitty"];
let dogs = ["rusty", "wyatt"];
cats.concat(dogs); // ['blue', 'kitty', 'rusty', 'wyatt'];

// includes
cats.includes("blue"); // true;

// indexOf
dogs.indexOf("wyatt"); // 1
dogs.indexOf("0"); // -1 없으면 -1 반환.
// 같은 것 중복해서 들어가있으면 첫 번째 인덱스를 반환. ('blue' 둘이면 첫 번째 'blue'의 인덱스 반환.


// reverse
cats.reverse(); // ['kitty', 'blue'];
```

- slice(시작점, 정지점) : 배열에서 인수로 전달된 시작점부터 정지점 앞 인덱스까지를 출력한 복사본 배열을 반환한다.
- splice(시작점, 제거할 요소 개수, 대체할 값 ) : 기존 요소들을 제거하거나 대체하거나 새로운 요소들을 추가해서 원본 배열의 내용을 변경한다.
- sort : 배열의 요소들을 정렬해준다.

```jsx
// slice
let colors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
colors.slice(2, 4); // ['yellow', 'green'];

// splice
let colors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
colors.splice(1, 1);
// ["red", "yellow", "green", "blue", "indigo", "violet"];
colors.splice(1, 0, "red-orange");
colors; //["red", "red-orange", "yellow", "green", "blue", "indigo", "violet"];

// sort
let scores = [1, 70, 100, 2500, 9, -12, 0, 34];
scores.sort(); // [-12, 0, 1, 100, 2500, 34, 70, 9];
// 그냥 배열에 sort를 사용하면 각 요소의 앞자리수만 가지고 정렬을 한다.
```

## **배열의 참조 관계**

```jsx
(["hi", "bye"] === ["hi", "bye"][1]) === // false
  [1]; // false
// 배열은 값을 비교하는 것이 아니라 배열의 참조값(주소값)을 비교하는 것이기 때문에 값이 같아도 false를 반환한다.

let nums = [1, 2, 3];
let numsCopy = nums;
nums; // [1, 2, 3];
numsCopy; // [1, 2, 3];
nums.push(4);
nums; // [1, 2, 3, 4];
numsCopy; //[1, 2, 3, 4];
// numsCopy[]는 nums[]를 할당한 것이라 참조값을 공유한다. 그래서 nums[] 에 요소를 추가하면 numsCopy[]에도 추가된다.
// numsCopy[]를 수정해도 nums[]도 같이 수정된다.
nums === numsCopy; // true;
```

### **배열과 const**

```jsx
const nums = [1, 2, 3];
nums.push(4);
nums; // [1, 2, 3, 4];
// 배열에 const를 사용해도 배열의 요소는 수정할 수 있다.
nums = [1, 2, 3, 4];
// Uncaught TypeError: Assignment to constant variable.
// const 키워드로 선언한 배열 변수는 같은 요소들이라도 재할당 할 수 없다.
```

### **중첩 배열**

배열 안에는 어떠한 값이라도 넣을 수 있다.배열이나 객체도 넣을 수 있다.

```jsx
const gameBoard = [
  ["X", "O", "X"],
  ["O", null, "X"],
  ["O", "O", "X"],
];
```
