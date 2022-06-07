# Problem Solving

목표

- Define what an algorithm is
- Devise a plan to solve algorithms
- Compare and contrast problem solving patterns including frequency counters, two pointer problems and divide and conquer

### 이걸 왜 알아야 하는가?

Almost **everything** that you do in programming involves some kind of **algorithm!It's the foundation for being a successful problem solving and developer.**

### How do you develop yourself?

- How do you improve?
1. **Deivise** a plan for solving problems.
접근 방식: 문제 해결을 위한 계획을 세운다.
2. **Master** common problem solving patterns.
문제 해결 패턴을 마스터한다.

### Problem Solving

1. Understand the Problem
2. Explore Concrete Examples
3. Break It Down
4. Solve/Simplify
5. Look Back and Refactor

## 1. Understand the Problem

1. 내 말로 바꿔서 문제를 말할 수 있는가
2. 문제의 입력은 무엇인가
3. 출력은 무엇인가
4. 해당 정보를 사용해 예상되는 출력을 얻을 수 있는가
5. 이 문제에서 정말 중요한건 무엇이고 어떤 label을 지정해야하는가

```jsx
// 두 개의 숫자를 사용하고 다음을 반환하는 함수
# UNDERSTAND THE PROBLEM

1. Can I restate the problem in my own words?
2. What are the inputs that go into the problem?
3. What are the outputs that should come from the solution to the problem?
4. Can the outputs be determined from the inputs? In other words, do I have enough information to solve the problem?
5. How should I label the important pieces of data that are a part of the problem?

## Write a function which takes two numbers and returns their sum

1. Can I restate the problem in my own words?
    - "implement addition"
2. What are the inputs that go into the problem?
    - ints?
    - floats?
    - what about string for large numbers?
3. What are the outputs that should come from the solution to the problem?
    - int? float? string?
4. Can the outputs be determined from the inputs? In other words, do I have enough information to solve the problem?
5. How should I label the important pieces of data that are a part of the problem?
```

## 2. EXPLORE EXAMPLES

- 구체적인 예시들을 떠올리는 것은 문제를 이해하는데 도움이 된다.
- 예시는 우리들의 최종 답안을 확인할 수 있도록 도와준다.
    - 해결 방안을 작성했을 때 예시를 알고 있다면 입력값과 나와야 하는 결과값을 이미 알고 있기 때문에 어떻게 작동해야 하는지 알고 있다.

## 구체적인 예시들을 탐색하기 위해 거쳐야 하는 단계

- Start with Simple Examples
- Progress to More Complex Examples
- Explore Examples with Empty Inputs
- Explore Examples with Invalid Inputs

```jsx
// Write a function which takes in a string and returns counts of each character in the string.

charCount("aaaa") // {a:4}
charCount("hello") // {h:1, e:1, l:2, o:1}

"my phone number is 220837"
"Hello hi"
charCount() or charCount("")
charCount(123)
```

## 3. Break It Down

- Understand the Problem
- Explore Concrete Examples
- Break It Down
    - 질문을 나누어 분석한다는 것은 정말로 중요하다.
    - 문제를 풀기 위해 취해야 하는 단계들을 직접 적어보자.
    - 완전히 구체적일 필요 없고, 해결 방법의 가장 기본적인 구성요소들을 적기만 하면 된다.

이렇게 하면 단계들을 전체적으로 보는데 도움이 되고, 이것은 집중하는 데도 도움이 된다. 또한 자신없어 하는 문제들을 제대로 조명하는데도 도움이 된다.

```jsx
// Write a function which takes in a string and returns counts of
// each character in th string

function charCount(str) {
	// do something
	// return an object with keys that are lowercase alphanumeric characters in the string
}

function charCount(str) {
	// make object to return at end
  // loop over string, for each character...
	  // if the char is a number/letter AND key in object, add one to count
		// if the char is a number/letter AND not in object, add it to object and set value to 1
		// if character is something else (space, period, etc.) don't do anything
	// return obejct at end
}

```

## 4. SIMPLIFY

- Understand the Problem
- Explore Concrete Examples
- Break It Down
- Solve/Simplify

```
SOLVE THE PROBLEM

        ~if you can’t~

SOLVE A SIMPLER PROBLEM!

```

⇒ 시간이 오래 걸리는 어려운 부분은 무시해! 그리고 다른 모든 것에 우선 집중하자.

- **우선 풀 수있는 문제들부터 시작하고 더 어려운 부분들은 나중에 통합**한다.
- 둘째로, 문제를 단순하게 만드는 것은 꽤 흔한 일이고, 이르 통해 실제 해결방법과 문제의 더 어려운 부분에 대한 통찰력을 얻음으로써 무언가 맞아들어간다는 느낌을 얻을 수 있다.
- 그래서 문제를 풀 떼 무엇인가에 발목이 잡혔지만 어디서부터 시작해야 한다는 것을 안다면 그냥 바로 거기로 가라.

### SIMPLIFY

- Find the core difficulty in what you’re tying to do
- Temporarily ignore that difficulty
- Write a simplfied solution
- Then incorporate that difficulty back in

```jsx
function charCount(str) {
	// make object to return at end
var result = {};
  // loop over string, for each character...
for(var i = 0; i < str.length; i++){
	var char = str[i].toLowerCase()
	  // if the chat is a number/letter AND key in object, add one to count
	if(result[char] > 0) {
		result[char]++;
	}
		// if the char is a number/letter AND not in object, add it to object and set value to 1
	else {
		result[char] = 1;
	}
// if character is something else (space, period, etc.) don't do anything
	// return obejct at end
return result;
}
```

🚗 **무언가를 성급하게 달려들어서 작성하는 것보다는 해야 할 일을 적고 풀 수 있는 다른 모든 것에 집중하자.**

## 5. LOOK BACK & REFACTOR

- Understand the Problem
- Explore Concrete Examples
- Break It Down
- Solve/Simplify
- Look Back and Refactor

### LOOK BACK & REFACTOR

Congrats on solving it, but you’re not done!

### REFACTORING QUESTIONS

- Can you check the result?
- Can you derive the result differently?
- Can you understand it at a glance?
    - 당신의 코드는 얼마나 직관적인가요 ?
- Can you use the result or method for some other problem?
- Can you improve the performance of your solution?
    - 시간복잡도 & 공간복잡도
- Can you think of other ways to refactor?
- How have other people solved this problem?
    - 다른 접근법이 있는지 & 잊은 것이 있는지
