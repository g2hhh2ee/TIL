# JavaScript 객체 리터럴(Literals)

객체는 일종의 구조로 여러 데이터 조각을 함께 저장하는 데에 도움이 된다.

- 데이터에 순서 부여하는 배열과 달리 객체는 그렇지 않다.

## 개요

- Objects are collections of properties.
- Properties are a key-value pair
- Rather than accessing data using and index, we use custom keys.

객체는 키-값 쌍(프로퍼티) 으로 데이터가 저장된다.

프로퍼티(property)는 두 개의 정보가 모인 것으로 레이블과 같은 키(key)와 값(value)로 구성된다. 이 둘이 쌍(pair)을 이루게 되고 객체는 이 쌍들의 집합이다.

- 데이터를 객체에 넣은 다음 우리가 무엇을 저장하든 사용자 정의 키를 사용해 다시 액세스 할 수 있다.

## 객체 데이터를 불러오는 법

1. 대괄호 안에 키를 따옴표로 감싸서 호출하면 값이 출력된다.

```javascript
const person = {firstName: "Han", lastName: "Jihee"}
person["lastName"]; // "Jihee"
```
2. 점 표기법으로 변수.키 형식으로 호출하면 값이 출력된다.

```javascript
person.firstName; // "Han"
person.lastName; // "Jihee"
```
- 숫자를 키로 쓸 수도 있지만, 저장 될 때는 모두 문자열로 저장된다.
- 점 구문은 편하게 쓸 수 있어서 좋지만, 변수 같은 유동적인 것을 객체에서 키로 쓰고 싶을 땐 대괄호를 사용해야 한다.
