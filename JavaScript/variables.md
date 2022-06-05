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

```jsx
//Variables are simply containers that store values
//They follow this pattern:
var yourVariableName = yourValue;

//They can store all of the values we've seen
var name = "Alice";
var secretNumber = 73;
var isAdorable = true;

//Recall the stored value by calling the variable name
var name = "Alice";
"hello there " + name; //"hello there Alice"

var num = 37;
num + 3 + 10; //50

//We can also update existing variables
var name = "Robert";
name = "Bob";
```

### EXERCISE

```jsx
const boilingPointC = 100;
const boilingPointF = 212;
```

### CONST and LET

```jsx
// Const - works just like let, except you cannot change the value
// good for storing things we know won't change

const hens = 4;
// hens = 20;
console.log(hens);

const age = 17;
// age = age + 1; assignment to constant variable
console.log(age);

// Const is good for storing things we know won't change

const feetMile = 5280;

// var - old way to make variables - these days no really reason to use it
```

- 1997 - JavaScript Started - VAR
- 2015 - let and const (idea of it introduced)
- 2018 - let and const (now supported widely)

**VAR**

- Scoped to "current execution context"
  - AKA a variable's enclosing function or the global scope | non a blocked scope variable
- Can be reassigned whenever
- Initializing w/ value is optional
- Can be redclared at any point
- Global variables are added to window
- both let and const are blocked scoped

**LET**

- BLOCK SCOPED
- Does not create property on global window object
- Can be reassigned
- Cannot be redeclared (in same scope)

**CONST**

- CANNOT be REASSIGNED
  - not immutable, but varilable reference cannot change
- BLOCK SCOPED
- Must be intialized with value
- Does not create property on global window object
- Cannot be redeclared (in same scope)
- can .push to objects to an array or object literal

LET | CONST | VAR and Hoisting

Let and Const are still hoisted and before you run your code but they are not set to undefined like VAR/It's not given a value. It is not being ignored

**TEMPORAL DEADZONE** (where your let declartion has been declared but it doesn't have a value yet)

- Prefer const over let
- Prefer let over const
- use var pretty much never (you probably don't need it)

## NULL and UNDEFINED

```jsx
//The two other primitives are null and undefined

//Variables that are declared but not
//initialized are undefined
//The following variables are undefined:
var name;
var age;

//null is "explicitly nothing"
var currentPlayer = "charlie";
currentPlayer = null; //game over
```

## console.log, alert, prompt

- Built in methods
- clear () - will clear the console

**alert**

- alert("Hello there")
- pop up window

**console.log**

- print to JS console
- console.log("hello from the console")
- not for user

**prompt**

- get info from user
- prompt("What is your name?")
- pop up window with text field
