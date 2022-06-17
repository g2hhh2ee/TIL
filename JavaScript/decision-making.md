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

