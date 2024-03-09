# 0. Javascript 훑어보기

> [https://learnjs.vlpt.us/](https://learnjs.vlpt.us/) 를 기반으로 작성한 자료입니다.
> 

## Javascript란?

- 페이지에 상호 작용을 추가하기 위한 간단한 스크립팅 언어로 디자인 되었음
- 웹 브라우저에서만 사용했던 언어
- 웹 브라우저에서 Javascript를 사용하는 것은 console 에서 쉽게 확인할 수 있음

```
console.log('Hello World');
```

- [CodeSandbox](https://codesandbox.io/)

## 변수와 상수

### 선언

```
let value = 1;
console.log(value);

```

### 변수 (let)

```
let value = 1;
console.log(value);
value = 2;
console.log(value);

```

- 변할 수 있는 값
- 같은 이름으로 재정의 불가능

### 상수 (const)

```
const a = 1;

```

- 바뀌지 않는 값
- 같은 이름으로 재정의 불가능

### let을 써야하나요 const를 써야하나요?

- `const`를 우선 사용하고, 필요할 때만 `let`을 사용하기

### var (쓰지마세요)

```
var a = 1;

```

- 예전 Javascript에서 변수와 상수를 정의할 때 사용했던 문법
- IE9, IE10 같은 구형 브라우저에서는 var 밖에 사용할 수 없지만, 우리가 var를 이용해서 코딩할 필요는 없음
    - 최신 문법을 예전 문법으로 트랜스파일 해주는 도구(Babel 등)가 존재하기 때문

## 데이터 타입

### 숫자

```
let value = 1;

```

### 문자열

```
let text = 'hello';
let name = "자바스크립트";

```

### 참/거짓 (Boolean)

```
let good = true;
let loading = false;

```

### null과 undefined

- `없음`을 나타내는 데이터 타입
- `null` : 이 값이 없다!
- `undefined` : 값이 있을 건데 아직 설정되지 않았다.

```
let criminal;
console.log(criminal);

```

## 연산자

### 산술 연산자

- `+` : 덧셈
- `` : 뺼셈
- `` : 곱셈
- `/` : 나눗셈
- `++` : +1
- `-` : -1

```
let a = 1;
console.log(a++); // 1
console.log(++a); // 3

```

### 대입 연산자

```
let a = 1;
a += 3;

```

### 논리 연산자

- `!` : NOT
- `&&` : AND
- `||` : OR

### 비교 연산자

- `===` : 두 값이 일치하는지 확인 (타입 검사 o)

```
const a = 1;
const b = 1;
const equals = a === b;
console.log(equals);

```

- `==` : 두 값이 일치하는지 확인 (타입 검사 x)

```
const a = 1;
const b = '1';
const equals = a == b;
console.log(equals);

```

- `!==` : 두 값이 일치하지 않는지 확인 (타입 검사 o)

```
const a = 1;
const b = '1';
const equals = a !== b;
console.log(equals);

```

- `!=` : 두 값이 일치하지 않는지 확인 (타입 검사 x)

```
const a = 1;
const b = '1';
const equals = a != b;
console.log(equals);

```

### 크고 작음

- `<` `<=` `>` `>=`

### 문자열 붙이기

```
const a = '안녕';
const b = '하세요';
console.log(a + b); // 안녕하세요

```

## 조건문

### if 문

```
if (조건) {
  코드;
}

```

### if-else 문

```
if (조건) {
  코드;
} else {
  코드;
}

```

### if-else if 문

```
if (조건) {
  코드;
} else if (조건) {
  코드;
} else {
  코드;
}

```

### switch/case 문

```
const device = 'iphone';

switch (device) {
  case 'iphone':
    console.log('아이폰!');
    break;
  case 'ipad':
    console.log('아이패드!');
    break;
  case 'galaxy note':
    console.log('갤럭시 노트!');
    break;
  default:
    console.log('모르겠네요..');
}

```

## 함수

```
function add(a, b) {
  return a + b;
}

const sum = add(1, 2);

```

- a, b를 매개변수(parameter, argument)라고 부름

### 연습

- name 이라는 파라미터를 받음
- name으로 넣은 값 앞에 Hello, 뒤에 !를 붙여 Hello name! 을 출력하는 코드 작성하기

### 템플릿 리터럴

- `Hello ${name}!`

### 화살표 함수

```
const add = (a, b) => {
  return a + b;
};

const sum = add(1, 2);

```

```
const add = (a, b) => a + b;
const sum = add(1, 2);

```

- 문법적 설탕은 아니고 동작에도 차이가 있지만, 크게 중요하지 않음

## 객체 (Object)

```
const dog = {
  name: '멍멍이',
  age: 2
};

console.log(dog.name); // 멍멍이
console.log(dog.age); // 2

```

- name, age 부분: `key`
- 멍멍이, 2 부분: `value`

```
const sample = {
  'key with space': true
};

```

- key에 공백을 포함하고 싶을 때

```
const name = 'nyanji'

const sample = {
  [name]: true
};

```

- key에 변수를 포함하고 싶을 때

### 객체 비구조화 할당

```
	const hero = {
  name: '스티븐 로저스',
  actor: '크리스 에반스',
  alias: '캡틴 아메리카'
};

const { alias, name, actor } = hero;

console.log(alias); // 캡틴 아메리카
console.log(name); // 스티븐 로저스
console.log(actor); // 크리스 에반스

```

- 객체에서 값들을 추출해서 새로운 상수로 선언해주는 것

```
function print({ alias, name, actor }) {
  const text = `${alias}(${name}) 역할을 맡은 배우는 ${actor} 입니다.`;
  console.log(text);
}

```

- 파라미터에서도 객체 비구조화 할당이 가능

### spread 연산자

```
const nameAndAge = {
  name: '신현지',
  age: 23
}

const member = { ...nameAndAge, id: 1 }

console.log(member); // { name: '신현지', age: 23, id: 1 }

```

## 배열

```
const array = [1, 2, 3, 4, 5];

console.log(array[3]); // 4

```

### push

```
array.push(6);

```

### length

```
array.length;

```

### spread 연산자

```
const members = ['신현지', '이규진'];
const newMembers = [...members, '이은희'];

console.log(newMembers); // ['신현지', '이규진', '이은희']

```

## 반복문

### for

```
for (let i = 0; i < 10; i++) {
  console.log(i);
}

```

### while

```
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}

```

### break와 continue

```
for (let i = 0; i < 10; i++) {
  if (i === 2) continue; // 다음 루프를 실행
  console.log(i);
  if (i === 5) break; // 반복문을 끝내기
}

```

## 배열 내장함수

### forEach

```
const superheroes = ['아이언맨', '캡틴 아메리카', '토르', '닥터 스트레인지'];

superheroes.forEach(hero => {
  console.log(hero);
});

```

### map

```
const array = [1, 2, 3, 4, 5, 6, 7, 8];

const square = n => n * n;
const squared = array.map(square);
console.log(squared);

```

### indexOf

```
const superheroes = ['아이언맨', '캡틴 아메리카', '토르', '닥터 스트레인지'];
const index = superheroes.indexOf('토르');
console.log(index); // 2

```

### findIndex

```
const todos = [
  {
    id: 1,
    text: '자바스크립트 입문',
    done: true
  },
  {
    id: 2,
    text: '함수 배우기',
    done: true
  },
  {
    id: 3,
    text: '객체와 배열 배우기',
    done: true
  },
  {
    id: 4,
    text: '배열 내장함수 배우기',
    done: false
  }
];

const index = todos.findIndex(todo => todo.id === 3);
console.log(index); // 2

```

### find

```
const todos = [
  {
    id: 1,
    text: '자바스크립트 입문',
    done: true
  },
  {
    id: 2,
    text: '함수 배우기',
    done: true
  },
  {
    id: 3,
    text: '객체와 배열 배우기',
    done: true
  },
  {
    id: 4,
    text: '배열 내장함수 배우기',
    done: false
  }
];

const todo = todos.find(todo => todo.id === 3);
console.log(todo); // { id: 3, text: "객체와 배열 배우기", done: true }

```

### filter

```
const todos = [
  {
    id: 1,
    text: '자바스크립트 입문',
    done: true
  },
  {
    id: 2,
    text: '함수 배우기',
    done: true
  },
  {
    id: 3,
    text: '객체와 배열 배우기',
    done: true
  },
  {
    id: 4,
    text: '배열 내장함수 배우기',
    done: false
  }
];

const tasksNotDone = todos.filter(todo => todo.done === false);
console.log(tasksNotDone);

```

### splice

```
const numbers = [10, 20, 30, 40];
const index = numbers.indexOf(30);
numbers.splice(index, 1);
console.log(numbers);

```

### slice

```
const numbers = [10, 20, 30, 40];
const sliced = numbers.slice(0, 2); // 0부터 시작해서 2전까지

console.log(sliced); // [10, 20]
console.log(numbers); // [10, 20, 30, 40]

```

### shift, pop

```
const numbers = [10, 20, 30, 40];
const value = numbers.shift();
console.log(value); // 10
console.log(numbers); // [20, 30, 40]

```

```
const numbers = [10, 20, 30, 40];
const value = numbers.pop();
console.log(value); // 40
console.log(numbers); // [10, 20, 30]

```

### unshift

```
const numbers = [10, 20, 30, 40];
numbers.unshift(0);
console.log(numbers); // [0, 10, 20, 30, 40]

```

### concat

```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const concated = arr1.concat(arr2);

console.log(concated); // [1, 2, 3, 4, 5, 6]

```

### join

```
const array = [1, 2, 3, 4, 5];
console.log(array.join()); // 1,2,3,4,5
console.log(array.join(' ')); // 1 2 3 4 5
console.log(array.join(', ')); // 1, 2, 3, 4, 5

```

### reduce

```
const numbers = [1, 2, 3, 4, 5];
let sum = array.reduce((accumulator, current) => accumulator + current, 0);

console.log(sum);

```

## 삼항 연산자

```
조건 ? true일때 : false일때

```

## Truthy and Falsy

- Truthy : 대충 true
- Falsy : 대충 false
    - `false`, `null`, `undefined`, `0`, `''`, `NaN`

```
function print(person) {
  if (person === undefined || person === null) {
    console.log('person이 없네요');
    return;
  }
  console.log(person.name);
}

const person = null;
print(person);

```

```
function print(person) {
  if (!person) {
    console.log('person이 없네요');
    return;
  }
  console.log(person.name);
}

const person = null;
print(person);

```

## 단축 평가 논리 계산법 (?)

### &&

- As-is

```
const dog = {
  name: '멍멍이'
};

function getName(animal) {
  if (animal) {
    return animal.name;
  }
  return undefined;
}

const name = getName();
console.log(name);

```

- To-be

```
const dog = {
  name: '멍멍이'
};

function getName(animal) {
  return animal && animal.name;
}

const name = getName();
console.log(name); // undefined

```

- `A && B` : A가 Truthy한 값이면 B가 결과값, A가 Falsy한 값이면 A가 결과값

### ||

- As-is

```
const namelessDog = {
  name: ''
};

function getName(animal) {
  const name = animal && animal.name;
  if (!name) {
    return '이름이 없는 동물입니다';
  }
  return name;
}

const name = getName(namelessDog);
console.log(name); // 이름이 없는 동물입니다.

```

- To-be

```
const namelessDog = {
  name: ''
};

function getName(animal) {
  const name = animal && animal.name;
  return name || '이름이 없는 동물입니다.';
}

const name = getName(namelessDog);
console.log(name); // 이름이 없는 동물입니다.

```

- `A || B` : A가 Truthy한 값이면 A가 결과값, A가 Falsy한 값이면 B가 결과값

## 함수의 기본 파라미터

```
function calculateCircleArea(r = 1) {
  return Math.PI * r * r;
}

const area = calculateCircleArea();
console.log(area); // 3.141592653589793

```

```
const calculateCircleArea = (r = 1) => Math.PI * r * r;

const area = calculateCircleArea();
console.log(area); // 3.141592653589793

```

## 비구조화 할당 문법

```
const object = { a: 1 };

const { a, b = 2 } = object;

```

```
const animal = {
  name: '멍멍이',
  type: '개'
};

const { name: nickname } = animal
console.log(nickname);

```

```
const array = [1];
const [one, two = 2] = array;

```

## Rest 문법

```
const purpleCuteSlime = {
  name: '슬라임',
  attribute: 'cute',
  color: 'purple'
};

const { color, ...rest } = purpleCuteSlime;
console.log(color);
console.log(rest);

```

```
const numbers = [0, 1, 2, 3, 4, 5, 6];

const [one, ...rest] = numbers;

console.log(one);
console.log(rest);

```

```
function sum(...rest) {
  return rest.reduce((acc, current) => acc + current, 0);
}

const numbers = [1, 2, 3, 4, 5, 6];
const result = sum(...numbers);
console.log(result);

```

## 자바스크립트의 Scope에 대한 이해

- Global (전역) Scope : 코드의 모든 범위에서 사용 가능
- Function (함수) Scope : 함수 안에서만 사용 가능
- Block (블록) Scope : 블록 내부에서만 사용 가능

```
const value = 'hello!';

function myFunction() {
  const value = 'bye!';
  const anotherValue = 'world';
  function functionInside() {
    console.log('functionInside: ');
    console.log(value);
    console.log(anotherValue);
  }
  functionInside();
}

myFunction()
console.log('global scope: ');
console.log(value);
console.log(anotherValue);

```

### Hoisting 이해하기

```
myFunction();

function myFunction() {
  console.log('hello world!');
}

```

- 위 코드는 자바스크립트 엔진이 코드를 해석하는 과정에서 아래와 같이 받아들임

```
function myFunction() {
  console.log('hello world!');
}

myFunction();

```

- `const` 와 `let` 은 hoisting 이 발생하지 않음

## 비동기 처리 다루기

![[Pasted image 20221204015006.png]]

```
function work() {
  const start = Date.now();
  for (let i = 0; i < 1000000000; i++) {}
  const end = Date.now();
  console.log(end - start + 'ms');
}

work();
console.log('다음 작업');

```

- work 함수는 동기 함수이므로, work가 실행되는 동안 다른 작업을 처리하지 않음

```
function work() {
  setTimeout(() => {
    const start = Date.now();
    for (let i = 0; i < 1000000000; i++) {}
    const end = Date.now();
    console.log(end - start + 'ms');
  }, 0);
}

console.log('작업 시작!');
work();
console.log('다음 작업');
// 작업 시작!; 다음 작업; 508ms

```

- setTimeout 함수는 비동기 함수이므로, setTimeout의 콜백함수가 실행되는 동안 다음 작업이 진행됨
- work 함수가 끝난 다음에 어떤 작업을 처리하고 싶을 땐 콜백 함수를 파라미터로 전달해줘야 함

```
function work(callback) {
  setTimeout(() => {
    const start = Date.now();
    for (let i = 0; i < 1000000000; i++) {}
    const end = Date.now();
    console.log(end - start + 'ms');
    callback();
  }, 0);
}

console.log('작업 시작!');
work(() => {
  console.log('작업이 끝났어요!')
});
console.log('다음 작업');

```

- API 호출을 할 때 많이 사용하게 될 문법

## Promise

- 비동기 작업을 조금 더 편하게 처리 할 수 있도록 ES6 에 도입된 기능
- 동기(Synchronous)적 처리: 작업을 요청함과 동시에 작업의 결과를 그 자리에서 받을 수 있는 데이터 처리 방식
- 비동기(Asynchronous)적 처리: 작업을 요청하지만 결과는 그 자리에서 꼭 받지 않아도 되는 데이터 처리 방식

```
function increaseAndPrint(n, callback) {
  setTimeout(() => {
    const increased = n + 1;
    console.log(increased);
    if (callback) {
      callback(increased);
    }
  }, 1000);
}

increaseAndPrint(0, n => {
  increaseAndPrint(n, n => {
    increaseAndPrint(n, n => {
      increaseAndPrint(n, n => {
        increaseAndPrint(n, n => {
          console.log('끝!');
        });
      });
    });
  });
});

```

- 콜백 지옥

### Promise 만들기

```
const myPromise = new Promise((resolve, reject) => {
  // 구현..
})

```

- 성공하는 경우

```
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(1);
  }, 1000);
});

myPromise.then(n => {
  console.log(n);
});

```

- 실패하는 경우

```
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject(new Error());
  }, 1000);
});

myPromise
  .then(n => {
    console.log(n);
  })
  .catch(error => {
    console.log(error);
  });

```

```
function increaseAndPrint(n) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const value = n + 1;
      if (value === 5) {
        const error = new Error();
        error.name = 'ValueIsFiveError';
        reject(error);
        return;
      }
      console.log(value);
      resolve(value);
    }, 1000);
  });
}

increaseAndPrint(0)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .catch(e => {
    console.error(e);
  });

```

## async/await

- Promise 를 더욱 쉽게 사용 할 수 있게 해주는 문법

```
function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

async function process() {
  console.log('안녕하세요!');
  await sleep(1000); // 1초쉬고
  console.log('반갑습니다!');
}

process();

```

- 함수의 앞부분에 async 키워드 붙이기
- Promise의 앞부분에 await 키워드를 붙이면 Promise가 끝날때까지 기다렸다가 다음 작업 수행 가능
- async를 사용하면 함수의 결과값으로 Promise를 반환

```
process().then(() => {
  console.log('작업이 끝났어요!');
});

```

### 에러 핸들링

- async 함수에서 에러를 발생시킬 땐 throw를 사용하고, 에러를 잡아낼 때는 try/cath문 사용

```
function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

async function makeError() {
  await sleep(1000);
  const error = new Error();
  throw error;
}

async function process() {
  try {
    await makeError();
  } catch (e) {
    console.error(e);
  }
}

process();

```

### Promise.all

- Promise 여러 개를 동시에 실행시키고 모든 Promise가 끝날 때까지 기다림

```
function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

const getDog = async () => {
  await sleep(1000);
  return '멍멍이';
};

const getRabbit = async () => {
  await sleep(500);
  return '토끼';
};
const getTurtle = async () => {
  await sleep(3000);
  return '거북이';
};

// As-is
async function process() {
  const dog = await getDog();
  console.log(dog);
  const rabbit = await getRabbit();
  console.log(rabbit);
  const turtle = await getTurtle();
  console.log(turtle);
}

// To-be
async function process() {
  const results = await Promise.all([getDog(), getRabbit(), getTurtle()]);
  console.log(results);
}

process();

```

### Promise.race

- Promise 여러 개를 동시에 실행시키고 제일 빨리 끝난 Promise의 결과값만 가져옴

```
function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

const getDog = async () => {
  await sleep(1000);
  return '멍멍이';
};

const getRabbit = async () => {
  await sleep(500);
  return '토끼';
};
const getTurtle = async () => {
  await sleep(3000);
  return '거북이';
};

async function process() {
  const first = await Promise.race([
    getDog(),
    getRabbit(),
    getTurtle()
  ]);
  console.log(first);
}

process();

```

## HTML과 Javascript 연동하기

```
<!DOCTYPE html>
<html>
  <head>
    <title>Parcel Sandbox</title>
    <meta charset="UTF-8" />
  </head>

  <body>
    <h2 id="number">0</h2>
    <div>
      <button id="increase">+1</button>
      <button id="decrease">-1</button>
    </div>

    <script src="src/index.js"></script>
  </body>
</html>

```

- DOM : 각 태그에 대한 정보를 지니고 있는 Javascript 객체
- id 값을 설정해주면 해당 DOM을 쉽게 선택할 수 있음

### DOM 선택하기

```
const number = document.getElementById("number");
const increase = document.getElementById("increase");
const decrease = document.getElementById("decrease");

console.log(number);
console.log(increase);
console.log(decrease);

```

### 이벤트 설정하기

```
const number = document.getElementById("number");
const increase = document.getElementById("increase");
const decrease = document.getElementById("decrease");

increase.onclick = () => {
  console.log("increase 가 클릭됨");
};

decrease.onclick = () => {
  console.log("decrease 가 클릭됨");
};

```

- DOM 이벤트 종류는 매우 다양하다 ([참고](https://developer.mozilla.org/ko/docs/Web/Events))

```
const number = document.getElementById("number");
const increase = document.getElementById("increase");
const decrease = document.getElementById("decrease");

increase.onclick = () => {
  const current = parseInt(number.innerText, 10);
  number.innerText = current + 1;
};

decrease.onclick = () => {
  const current = parseInt(number.innerText, 10);
  number.innerText = current - 1;
};

```

- [모달 만들기](https://learnjs.vlpt.us/html/02-modal.html)