JavaScript Decision Making

## 1. **Comparison Operators 비교 연산자**

| 기호 | 이름 | 예시 |
| --- | --- | --- |
| > | greater than | 5 > 1 true |
| < | less than | 1 < 5 true |
| >= | greater than or equal to | 18 >= 18 true |
| <= | less than equal to | 18 <= 18 true |
| == | equality | 20 == 20 true |
| != | not equal | 10 != 20 true |
| === | strict equality | --- |
| !== | strict non-equality | 1 === ‘1’ false |
- 비교연산자는 숫자뿐만 아니라 문자열도 비교가 가능하다.
- 유니코드에 정리되어 있는 숫자 코드를 이용하면 문자열도 대소비교가 가능하다.
```jsx
'a' < 'b'; ~>true ~> comparison based on unicode 

'A' < 'b'; ~>true
```

## 2. **Equality: Triple vs. Double Equals 등호**

> 결론은, 삼중 등호 써라!
> 

### **`이중 등호 ==`**

이중등호 는 타입이 달라도 값이 같으면 true를 반환한다.

```jsx
// 이중 등호
1 == "1"; // true
0 == ""; // true
0 == false; // true
null == undefined; // true
```

### **`삼중 등호 ===`**

삼중등호 는 타입과 값이 모두 같아야 true 를 반환한다.

```jsx
1 === "1"; // false
```

## 3. **Console, Alert, & Prompt 코드를 실행하는 방법**

### **console.log()**

콘솔에 인자로 넣어준 값을 출력한다.콘솔 메서드도 문자열 메서드와 마찬가지로 여러가지 메서드가 존재한다. 그 중에 log()가 가장 많이 쓰인다.

### **alert()**

브라우저에 팝업창을 띄우고 인자로 넣어준 값을 출력한다.

### **prompt()**

브라우저에 입력창이 있는 팝업창을 띄우고 인자로 넣어준 값을 출력한다. 사용자가 입력창에 값을 입력하면 입력된 값을 문자열로 반환받는다.parseInt() 메서드를 사용해서 숫자로 변환할 수 있다.

## 4. **조건문 if**

> if(조건식) { 조건식이 참일 때 실행문 } else if (조건식) { else if(조건식)의 조건식이 참일 때 실행문 } else { 모든 조건식이 거짓일 때 실행문 }
> 

```jsx
let random = Math.random();
if (random < 0.5) {
  console.log("YOUR NUMBER IS LESS TAHN 0.5!!!");
  console.log(random);
}
console.log("YOUR NUMBER IS GREATER THAN 0.5!!!");
console.log(random);
```

## 5. **조건부 네스팅 (Nesting : 중첩)**

비밀번호 설정하는 간단한 예제로 조건부 네스팅을 연습해보자.

```jsx
const password = prompt("please enter a new password");

// Password must be 6+ characters
if (password.length >= 6) {
  // Password cannot include space
  if (password.indexOf(" ") === -1) {
    console.log("Valid Password!");
  } else {
    console.log("Password cannot contain spaces!");
  }
} else {
  console.log("PASSWORD TOO SHORT! Must be 6+ characters");
}
```

## 6. **논리 연산자**

두 가지 표현식을 합쳐 여러 논리를 하나로 결합함으로써 하나의 큰 논리를 형성한다.

### **AND ( && )**

두 가지 표현식을 && 키워드로 연결한다. 두 가지 표현식 모두 true 이면 true를 반환.둘 중에 하나라도 false 이면 false를 반환.

```jsx
1 <= 4 && "a" === "a"; // true
9 > 10 && 9 >= 9; // false
"abc".length === 3 && 1 + 1 === 4; // false

// 비밀번호 설정하는 예시
const password = prompt("Enter your password");
if (password.length >= 6 && password.indexOf(" ") === -1) {
  console.log("VALID PASSWORD!");
} else {
  console.log("INCORRECT FORMAT FOR PASSWORD!");
}
```

### **OR ( || : 파이프기호 )**

두 가지 표현식을 || 키워드로 연결한다.두 가지 표현식 중에 하나만 true 이면 true를 반환.

```jsx
1 !== 1 || 10 === 10; // true
10 / 2 === 5 || null; // true
0 || undefined; // false

// 0 - 5 FREE
// 5 - 10 $10
// 10 - 65 $20
// 65+ FREE

const age = 50;
if ((age >= 0 && age < 5) || age >= 65) {
  console.log("FREE");
} else if (age >= 5 && age < 10) {
  console.log("$10");
} else if (age >= 10 && age < 65) {
  console.log("$20");
} else {
  console.log("INVALID AGE!");
}
```

AND 가 OR 보다 먼저 실행된다.

### **NOT**

값이 true이면 false를 반환, false 이면 true를 반환한다.

```jsx
!null; // true
!(0 === 0); // false
!(3 <= 4); // false

const firstName = prompt("enter your first name");
if (!firstName) {
  firstName = prompt("TRY AGAIN!!!");
}
```

## 7. **Switch 문**

조건문인 switch 문에서는 switch 와 case, break, default 키워드를 사용한다.

```jsx
const day = 2;
switch (day) {
  case 1:
    console.log("MONDAY!");
    break;
  case 2:
    console.log("TUESDAY!");
    break;
  case 3:
    console.log("WEDNESDAY!");
    break;
  case 4:
    console.log("THURSDAY!");
    break;
  case 5:
    console.log("FRIDAY!");
    break;
  case 6:
  case 7:
    console.log("WEEKEND!");
    break;
  // 인수에 해당하는 case 가 없으면 default가 실행된다.
  default:
    console.log("INVALID NUMBER!");
}
```

break 가 없다면 스위치가 인수로 받은 값에 맞는 case를 실행하고 그 다음 case를 이어서 쭉 실행한다.

- ex) day = 2 이면, case 2 ~ 5 까지 전부 실행된다. 그래서 break 키워드를 사용하여 switch문을 종료한다.
