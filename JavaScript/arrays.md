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

- `slice`(시작점, 정지점) : 배열에서 인수로 전달된 시작점부터 정지점 앞 인덱스까지를 출력한 **복사본 배열을 반환**한다. (배열의 일부를 복사) `slice(?start, ?end)`
- `splice`(시작점, 제거할 요소 개수, 대체할 값 ) : 기존 요소들을 제거하거나 대체하거나 새로운 요소들을 추가해서 **원본 배열의 내용을 변경**한다. (배열의 요소를 삽입, 삭제) `splice(start, ?deleteCount, ...items`
    - 삭제하지 않고 삽입만 하고 싶으면 `?deleteCount = 0`
        - splice(3, 0, ‘forestgreen’, ‘smokewhite’);
        - colors.splice(2, 2, 'DELETED~!'); `// 2개 요소가 하나의 'DELETED~!'로 바뀜`
- `sort` : 배열의 요소들을 정렬해준다.
    - 빈 괄호를 사용해 배열 정렬, 모든 것을 문자열로 변환한 다음 비교할 것임.
    - The `sort()` method sorts the elements of an array *in place* and returns the sorted array.
    - The default sort order: ascending,
    - built upon converting the elements into strings,
    - then comparing their sequences of UTF-16 code units values.
    - 숫자 배열에 sort를 사용하면 각 요소의 **앞자리수만 가지고 정렬**을 한다.⇒ 신뢰할 수 없다. (정렬과 관련된 경고임)
    - 따라서, 정렬을 작성하고 사용자 정의된 함수를 포함하는 방법이 있다. (이건 후에 알아볼 것임. arrays.toString(), reduce, filter 등)

```jsx
// slice
let colors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
colors.slice(2, 4); // ['yellow', 'green'];
colors.slice(-3); // last three elements. ["blue", "indigo", "violet"];

// splice
let colors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
colors.splice(1, 1);
// ["red", "yellow", "green", "blue", "indigo", "violet"];
colors.splice(1, 0, "red-orange");
colors; //["red", "red-orange", "yellow", "green", "blue", "indigo", "violet"];

// sort
let scores = [1, 70, 100, 2500, 9, -12, 0, 34];
scores.sort(); // [-12, 0, 1, 100, 2500, 34, 70, 9];
// 그냥 숫자 배열에 sort를 사용하면 각 요소의 앞자리수만 가지고 정렬을 한다.
```

## **배열의 참조 관계**
배열은 값을 비교하는 것이 아니라 **배열의 참조값(주소값)을 비교하는 것이기 때문에 값이 같아도 false를 반환한다.**

- 배열에서 비교하는 것은 **메모리의 참조**!
- **let numsCopy = nums; // numsCopy[]는 nums[]를 할당한 것이라 참조값을 공유한다.**
- nums는 [1,2,3]을 가리키고 있고, numsCopy는 또다른 화살표(포인터?)로 [1,2,3]을 가리키고 있다.
- 따라서 nums === numsCopy; // true. JavaScript 메모리에서 동일한 것을 가리키고 있다!
- 이중 등호, 삼중 등호는 메모리에서 참조를 확인한다. 그치만 같은 배열이라면, 같은 것을 참조하고 있다면 비교가 무의미하다. → 덜중요함.
```jsx
'hey' === 'hey'; // true
['hey', 'yo'] === ['hey', 'yo']; // false
[1] === [1]; // false
[1] == [1]; // false
[] == []; // false

// 배열은 값을 비교하는 것이 아니라 배열의 참조값(주소값)을 비교하는 것이기 때문에 
// 값이 같아도 false를 반환한다.

let nums = [1, 2, 3];
let numsCopy = nums; // numsCopy[]는 nums[]를 할당한 것이라 참조값을 공유한다.
nums; // [1, 2, 3];
numsCopy; // [1, 2, 3];
nums.push(4); // 그래서 nums[] 에 요소를 추가하면 numsCopy[]에도 추가된다.
nums; // [1, 2, 3, 4];
numsCopy; //[1, 2, 3, 4];
// numsCopy[]는 nums[]를 할당한 것이라 참조값을 공유한다. 
// 그래서 nums[] 에 요소를 추가하면 numsCopy[]에도 추가된다.
// numsCopy[]를 수정해도 nums[]도 같이 수정된다.
nums === numsCopy; // true;
```

### **배열과 const**
- const 변수는 재할당 불가!! ❌ (const is primitive. can’t change at all. ) can’t change reference and reassign,
- 중요한 건, **변수 자체가 재할당되지 않는다는 것!**
- const nums = [1, 2, 3];
    - nums는 내용을 저장하는 게 아니고 참조를 저장한거임.
    - 따라서 배열에 대한 참조가 변경되지 않는한!
    - 그러니까 shell이 그대로 유지되면 내용이 변경될 수 있다.
    - 왜? 그 어떤 것도 이 배열의 주소인 참조에 영향을 미치지 않기 때문.
- 결론은, const 변수는 재할당 할 수 없다고 했지만,
- `const 변수 = [];` **← 이 경우엔 변수 자체는 배열의 메모리 주소를 가리키고 있기 때문에 배열의 요소와는 상관이 없다. 따라서, 배열 내부 요소는 수정 가능! 변수가 가리키고 있는 메모리의 주소를 바꾸는 게 아니니까!**
- 하지만 이 변수에 새로운 참조를 설정하려고 하면 Uncaught TypeError: Assignment to constant variable. 에러 발생한다.
- const nums = [1,2,3];
nums.push(4); // nums가 가리키고 있는 배열의 메모리 주소에는 영향 없으니까 에러 안 난다. [1,2,3,4]
const nums = [1,2,3,4,5]; // ❌ nums 변수에 배열을 재할당하는 것임 이건.
- 우리 눈엔 똑같이 보이지만, 할당된 메모리 주소가 다르다!!! 조심!
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
// null에 접근하려면
gameBoard[1][1]; // null
```
