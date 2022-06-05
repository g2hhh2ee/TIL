# JavaScript

## Define and Reference Javascript | VAR

- Variables are like labels for values
- we can sftore a value and give it a name so that we can:
- refer back to it later
- use that value to do…stuff
- or change it later one

### EXERCISE

```jsx
//1,2.
let myLuckyNumber = 37;
let octopusLimbs = 8;
```

## Updating Variables

```jsx
// Updating Variables
let score = 0;
console.log(score);

// new line
score = score + 5;
console.log(score);

// new line
score = score + 5;
console.log(score);

// new line - shorter syntax
score += 5;
console.log(score);

// new line
score *= 5;
console.log(score);

// new line
score -= 5;
console.log(score);

// Remember that ++ increments by one and -- decrements by one
```

## VARIABLES | OLDER WAY

실제로 변수를 만드는 데 사용할 수 있는 두 개의 다른 키워드가 있다.

- `const` : 상수(constant)
  - const works just like let, except you **CANNOT** change the value!!
  - 변경하거나 다시 할당할 수는 없다.
  - 그럼 왜 const를 쓰는가?
    ```jsx
    const pi = 3.141592;
    const daysInWeek = 7;
    const minHeightForRide = 60;
    ```
    Once we cover Arrays & Objects, we’ll see other situations where _const_ makes sense over _let_.
- `var`
  - the old variable keyword
  - before let & const, var was the only way of declaring variables. These days, there isn’t really a reason to use it.

### EXERCISE

```jsx
const boilingPointC = 100;
const boilingPointF = 212;
```
