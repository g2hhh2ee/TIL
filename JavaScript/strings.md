# JavaScript Strings

Crucial

- String Basics
- Indexes and Length
- Undefined & Null
- String Methods
- String Template Literals

Important

- Random Numbers and the Object

## Intro Strings

**Primitive Types**

- Number
- String
- Boolean
- Null
- Undefined
- +) 2 others: Symbol and BigInt

### String

- Strings of characters

- represents **text**, and must be wrapped in quotes.

```jsx
// Introducing strings
// Strings are a primitive type

let username = "danny"; // "danny" is a string

let favAnimal = "Dumbo Octopus"; // this is a string

let goAway = "I told her to 'go away'!";
console.log(goAway);
```

### Exercise

```jsx
let bestColor = "purple";
let quote = 'You had me at "hello"';
```

## 2. Indexes and Length

- Index가 중요한 이유는?
  - **해당 인덱스를 기반으로 하는 개별 문자에 액세스할 수 있다.**

```jsx
// strings are indexed in JS
// each character has a corresponding index (a position number)
// 0부터 시작한다.

let animal = "Dumbo Octopus";

console.log(animal[3]);

let phone = "(231)345-1344";

console.log(phone[0]);

console.log(animal.length); // 13

console.log("lol".length);

let firstName = "Lolli";
let lastName = "Pop";
console.log(firstName + " " + lastName);

// typeof
// 문자열은 더할 수 있다.
```

## 3. String Methods

- Methods are built-in actions we can perform with individual strings
- help us do things like:
  - searching within a string
  - replacing part of a string
  - changing the casing of a string
- `thing.method()`

```jsx
// Methods are built-in actions we can perform with individual strings

// thing.method()

let msg = "leave me alone";
msg.toUpperCase; // 작동 안 한다.
msg.toUpperCase(); // 괄호 꼭 넣어줘야함.
console.log(msg.toUpperCase());

console.log("LOLOLO".toLowerCase());
```

- `Trim`
  - **문자열의 시작이나 끝 부분에 있는 공백을 제거**한다.
  - 입력 받을 때 유용하다.

```jsx
let greetings = "   greetings   ";
greetings.trim();
console.log(greetings);

console.log(greetings.trim().toUpperCase());

let whisper = message.trim().toLowerCase();
```

## 4. String Methods with Arguments

- `thing.method(arg)`
  - some methods accept **arguments** that modify their behavior.
  - Think of them as inputs that we can pass in.
  - We pass these arguments inside of the parentheses.
  - 인수는 동작 방식을 변경하기 위해 전달하는 입력
- `thing.indexOf()`
  - 0부터 시작
  - 없는 걸 찾으면 -1 출력 (Not Found)
  - 중복되는 게 있으면 첫 번째 위치 출력한다.
  - [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)

```jsx
// String Methods with Arguments
let tvShow = "catdog";
tvShow.indexOf("cat"); // 0
tvShow.indexOf("dog"); // 3
tvShow.indexOf("kitten"); // -1
// 없는 걸 찾으면 -1 출력한다.

console.log(tvShow.indexOf("cat"));

console.log("haha that is so funny!".indexOf("h"));
// first occurence of h
// 첫 번째 위치 출력한다.
```

- `thing.slice(시작 index[, 끝나는 index])`
  - 문자열의 일부를 추출하거나 잘라서 반환
  - [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
  - `thing.slice(음수)` : 마지막에서 음수만큼 잘라서 반환

```jsx
let message = "haha that is so funny";
console.log(message.slice(9));
console.log(message);

console.log(message.slice(0, 9));
message.slice(-2); // ny
```

- `thing.replace()`
  - **중복되는 게 있으면 첫 번째 것을 교체한다!**
  - 정규식
  - [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)

```jsx
// replace
let annoyingLaugh = "teehee so funny! teehee!";

console.log(annoyingLaugh.replace("teehee", "haa"));
annoyingLaugh.replace("teehee", "haa"); // 'haha so funny! teehee'
//Notice that it only replaces the first instance
```

- `thing.repeat()`
  - [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)

```jsx
// repeat
console.log("lol".repeat(10));
```
