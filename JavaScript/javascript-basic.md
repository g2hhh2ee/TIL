# JavaScript

## Chrome Javascript Console

- write javascript in the console
- interact with css
- testing something out
- change it in file after

### `PEMDAS` 연산자 우선순위

- parantheses 괄호
- exponents 지수
- multiplication 곱셈
- division 나눗셈
- addition 덧셈
- subtraction 뺄셈

## NaN
![nan](https://user-images.githubusercontent.com/57996351/172012253-26e2c0fd-500b-4f0d-9f1a-1f21428919b0.PNG)


- is a numeric value that represents something that is… not a number
- 자바스크립트에서 Number로 분류된다.
- represents a value that is not a number
- 그러니까, considered a number by JavaScript, but it represents sth that is not a number!
- NaN에 어떤 연산을 하더라도 결과는 NaN!
- `typeof` 로 확인해볼 수 있다.

```jsx
0 / 0; // NaN
1 + NaN; // NaN

typeof 7;
("number");
typeof 3.14159;
("number");
0 / 0;
NaN;
typeof NaN;
("number");
NaN * 1;
NaN;
NaN + NaN;
NaN;
```

## 5 JS Primitive Types

**5 Primitive Data Types**

- low-level, basic types of data

```js
//Numbers
4; //whole
9.3 - //fraction
  10; //negative

//Strings
("Hello World"); //one string, muliple words
("43"); //numbers

//Booleans
true;
false;

//null and undefined
null;
undefined;
```

- Numbers
  - treats all numbers the same
- Strings
  - basically text
  - inside quotes
- Booleans
  - only 2 options, no quotes, no numbers
- Null and Undefined
  - these are actually values

**Numbers and Numeric Operators**

```js
//Numbers
4;
9.3 - 10;

//we can do some math
4 + 10; //14
1 / 5; //0.2

//Modulo - remainder operator
10 % 3; //1
24 % 2; //0
15 % 11; //4
```

- Modulo - takes the second number and divide it into the first as many time as it goes into the whole number and take the remainder.

**Strings and Common String Methods**

```js
//Single or Double quotes OK
'hello world';
"hello world";

//Concatenation
"charlie" + "brown"; //"charliebrown"

//Escape Characters start with "\"
//Escape out of string to use special characters not allowed by string
('Singin "Do wah diddy, diddy, dum diddy do" ');
("This is a backslash: \\");

//Strings have a length property
"hello world".length; //11

//Access individual characters using [] and an index
"hello"[0]; //"h"
"hello"[4]; //"o"
// index is always one less than the total length of the string if looking for the last character in a string
```

#### EXERCISE

```js
//1.
100 %
  3(
    //1

    //2.
    "blah" + "blah"
  )[6]; //a //6 index is the 7th character

//3.
"hello".length % "hi\\".length; //5 % 3 = 2
```


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
score = 5;
console.log(score);

// new line
score = score + 5;
console.log(score);

// new line
score = score + 5;
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

```js
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

#### CONST and LET

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

```js
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
