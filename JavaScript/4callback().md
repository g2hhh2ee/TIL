4. 콜백함수

## **[콜백함수(Callback Function) 란?](https://inpa.tistory.com/entry/JS-%F0%9F%93%9A-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%BD%9C%EB%B0%B1-%ED%95%A8%EC%88%98?category=889099#%EC%BD%-C%EB%B-%B-%ED%--%A-%EC%--%---Callback%--Function-%--%EB%-E%--%-F)**

> 파라미터로 함수를 전달하는 함수.
> 

콜백은 간단히 말하면 **함수 안에서 실행하는 또 다른 함수** 이다.

함수를 만들 때 인풋(parameters)을 함수로 받아서 사용할 수 있는데, 이 때 **인자로 사용되는 함수를 콜백 함수**라고 한다.

```jsx
function introduce (lastName, firstName, callback) {
	var fullName = lastName + firstName;
	callback(fullName); 
} 
introduce("홍", "길동", function(name) {
	console.log(name);
}); // 결과 -> 홍길동

```

****콜백함수가 필요한 이유?****

여러 함수들을 선언하고, 어느 한 함수가 실행될 때, 상황에 따라 필요한 다른 함수를 실행하고 싶을 때 활용할 수 있다.

콜백함수는 때로는 그냥 가독성이나 코드 재사용성 면에서도 활용한다.

콜백이 유용한 이유는, 콜백 함수만을 바꿔줌으로서 하나의 함수를 여러가지로 응용할 수 있기 때문이다.

```jsx
function introduce (lastName, firstName, callback) {
	var fullName = lastName + firstName; 
	callback(fullName); 
} 
function say_hello (name) { 
	console.log("안녕하세요 제 이름은 " + name + "입니다"); 
} 
function say_bye (name) { 
	console.log("지금까지 " + name + "이었습니다. 안녕히계세요"); 
} 
introduce("홍", "길동", say_hello); 
// 결과 -> 안녕하세요 제 이름은 홍길동입니다 
introduce("홍", "길동", say_bye); 
// 결과 -> 지금까지 홍길동이었습니다. 안녕히계세요
```

위와 같이 다른 동작을 수행하는 함수 say_hello와 say_bye를 정의해두고 introduce 함수에 인풋으로 사용해주면, introduce라는 함수에서 받아들이는 같은 인풋들을 가지고 다른 동작을 수행하는 것이 가능해진다.

**함수를 나눠줌으로써** 코드를 재활용 할 수 있고, 관리도 더 쉬워지게 되는거다.
