> ### Доп. материалы
>
> - [Поддержка JS](https://kangax.github.io/compat-table/es6/)
> - [Поддержка JS 2](https://caniuse.com/es6)
> - 'use strict';

# База

## Типы данных

```js
typeof 3; // Определим какой тип у "3"

let str = "Hello";
let numb = 2;
let float = 1.2;
let bool = true;
str + numb; // NaN
str[10]; // undefined

let bool = true;
// 0, '', undefined, NaN, null = false
// Всё остальное приводится к true

2 + "3"; // = 23 — Не сторогая типизация
```

## Операторы

## Арифметические

```js
console.log((2 + (3 / 4) * 4) ** 2 % 2);

// a = a + 1  →  a += 1
// a = a - 1  →  a -= 1
// a = a * 2  →  a *= 2
// a = a / 1  →  a /= 1
// a = a + 'foo'  →  a += 'foo'
```

```js
let i = 0;
i++; // 0
i++; // 1
i--; // 2
i--; // 1

let i = 0;
++i; // 1
++i; // 2
--i; // 1
--i; // 0
```

## Логические

```js
let a = true;
leb b = false;

// И
a && b // false

// ИЛИ
a || b // true

// Отрицание
!a  // false
!!a // true

// Равенство / Не равенство
a === b // false
a !== b // true
```

```js
0 && 1; // = 1
0 || 1; // = 0

const value = name || "";
234 || ""; // 234
undefined || ""; // ''

// Оператор нулевого слияния
null ?? '!' // '!'
undefined ?? '!' // '!'
'This!' ?? '!' // 'This!'
```

## Строки

```js
"Hello world!";
"Hello world!";
`Hello world!`;
```

```js
"Dragon's \mother said \"No\"";
// => Dragon's mother said "No"

"- Are you hungry?\n- Aaaarrrgh!";
//- Are you hungry?
//- Aaaarrrgh!
```

```js
"Hello world".length; // 11
let lenStr = length("Hello!"); //11
```

```js
let str = "Hello";
str[0]; // H
```

## Переменные

```js
let variableOne = 'Father!';
let variableTwo = 2**3
const constThree

let greeting = 'Hello'
let name
console.log(`${greeting}, ${firstName}!`);
```

## Функции

Вызов функции

```js
// length это функция
import { length } from "hexlet-basics/string";

// Вызов функции length с параметром 'Hello!'
const result = length("Hello!");
console.log(result); // => 6
```

Сокращенный синтаксис

```js
const sum = (a, b) => a + b;

//  const sum = (a, b) => {
//  return a + b;
//  };
```

Определение функции

```js
function showMessage() {
  alert("Всем привет!");
}

const showMessage = () => {
  // Внутри тела отступ 2 пробела для удобства чтения
  alert("Всем привет!");
};

const showMessage = () => {
  return "Всем привет!";
};
```

Передача параметров

```js
const showMessage = (str, symb, val = 1) => {
  return "Всем привет!";
};
```

## Условные конструкции

IF

```js
if (lastChar === "?") {
  sentenceType = "question";
} else if (lastChar === "!") {
  sentenceType = "exclamation";
} else {
  sentenceType = "normal";
}
```

Тренарный оператор

```js
//<predicate> ? <expression on true> : <expression on false>
lastChar === "?" ? "question" : "normal";
```

SWITCH

```js
switch (count) {
  case 1:
    return "one";
  case 2:
    return "two";
  default:
    return null;
}
```

## Циклы

WHILE

```js
let i = 1;
let lastNumber = 10;
while (i <= lastNumber) {
  console.log(i);
}
```

```js
do {
  ...
    } while (swapped);
```

FOR

```js
for (let i = 0; i < str.length; i += 1) {
  result = `${str[i]}${result}`;
}

for (const name of userNames) {
  console.log(name);
}

const course = { name: 'JS: React', slug: 'js-react' };
for (const prop in course) {
  console.log(`course.${prop} = ${course[prop]}`);
}
// course.name = JS: React
// course.slug = js-react
```

Управляющие конструкции

```js
//break производит выход из цикла
for (const item of coll) {
  if (item === "stop") {
    break;
  }
}

//continue позволяет пропустить итерацию цикла
for (const item of coll) {
  if (item === null) {
    continue;
  }
}
```

## Модули

```js
import { surfaceArea, square } from "./math.js";
const surfaceOfMars = surfaceArea(3390);

import * as mathematics from "./math.js";
const surfaceOfMars = mathematics.surfaceArea(3390);
```

```js
export const pi = 3.14;

export const square = (x) => {
  return x * x;
};

export default (r) => {
  return 4 * pi * square(r);
};

export { pi, e, square };
export default pi;
```

## Массивы

```js
// Определение массива

let friends = [];
let friends = ["petya", "vasya", "ivan"];
const arr2 = [1, [3, 2], [3, [4]]];
```

```js
// Получение элемента массива

friends[0]; // 'petya'
friends.at(0); // 'petya'
friends.at(-1); // 'ivan'

const arr2 = [1, [3, 2], [3, [4]]];
arr2[2][1][0];
```

```js
// Изменение элемента массива

let friends[0] = 'mary' // ['mary', 'vasya', 'ivan']

friends.push('andy');    // ['mary', 'vasya', 'ivan', 'andy']

friends.unshift('andy'); // ['andy', 'mary', 'vasya', 'ivan']

const animals = ['cats', 'dogs', 'birds'];
animals[3] = 'horses'; // => ['cats', 'dogs', 'birds', 'horses']

const animals = ['cats', 'dogs', 'birds'];
delete animals[1]; // ['cats', <1 empty item>, 'birds']
```

```js
// Изменение массива

animals.pop(); // вернет 'birds', массив станет ['cats', 'dogs']
animals.push("bird"); //  вернет 'birds', массив станет ['cats', 'dogs','bird']
animals.slice(1); // массив станет ['dogs','bird']

const items = [3, 8, 1];
items.sort(); // [1, 3, 8]
items.reverse(); // [8, 3, 1]
```

```js
// Масив --> строка

let parts = ["JavaScript", "PHP", "Python"];
let output = parts.join(", "); // => JavaScript, PHP, Python

// Строка --> масив

let separator = " ";
"JavaScript PHP Python".split(separator); // => [JavaScript, PHP, Python]
```

```js
// Деструктуризация

const point = [3, 5];
const [x, y] = point; // x = 3, y = 5
const [, y] = point; // y = 5
const [x, y, z] = point; // x = 3, y = 5, z = undefined

const [first, second, third] = "two";
console.log(first); // => 't'
console.log(second); // => 'w'
console.log(third); // => 'o'
```

```js
// REST оператор

const fruits = ["apple", "orange", "banana", "pineapple"];

const [head, ...tail] = fruits;
// tail = ['orange', 'banana', 'pineapple']
const [first, second, ...rest] = fruits;
// rest = ['banana', 'pineapple']
const [first, second, third, ...rest] = fruits;
// rest = ['pineapple']

const [first, second, ...rest] = "some string";
console.log(first); // => 's'
console.log(second); // => 'o'
console.log(rest); // => [ 'm', 'e', ' ', 's', 't', 'r', 'i', 'n', 'g' ]
```

```js
// SPREAD оператор

const frenchCities = ["paris", "marseille"];

const cities = ["milan", "rome", ...frenchCities];
// ['milan', 'rome', 'paris', 'marseille']
const cities = [...frenchCities, "milan", "rome"];
// ['paris', 'marseille', 'milan', 'rome']
const cities = ["milan", ...frenchCities, "rome"];
// ['milan', 'paris', 'marseille', 'rome']

// То же самое без spread-оператора
const cities = ["milan", "rome"].concat(frenchCities);
```
```js
// Получение пары значений
//

const arr = [['name','Alex'],['Age','25']]

for (const [key, val] of arr) {
  ...
}
```

# Обьекты, как ассоциативные массивы

```js
let obj = {};
let anotherObj = {name: 'Alex', age: 22}

anotherObj.name // 'Alex'

anotherObj[name] // 'Alex'

anotherObj.name = 'Mary' // {name: 'Mary', age: 22}
obj.type = 'great' // {type: 'great'}

const filename = 'file';
const ext = 'jpg';
const info = { filename, extension: ext };
// const info = { filename: 'hexlet', extension: 'jpg' };
```
```js
// Проверка существования обьекта
// Object.hasOwn()

const object1 = {prop: 'exists'};
Object.hasOwn(object1, 'prop'); // true
Object.hasOwn(object1, 'name'); // true
```

```js
// Доступ к элементам обьекта

// Object.keys(obj)
// Возвращает массив ключей обьекта
const course = { name: 'JS: React', slug: 'js-react' };
const keys = Object.keys(course); // [ 'name', 'slug' ]

// Object.values(obj)
// Возвращает массив значений обьекта
const course = { name: 'JS: React', slug: 'js-react' };
const values = Object.values(course); // [ 'JS: React', 'js-react' ]

// Object.entries(obj)
// Возвращает вложенны массив ключь - значение обьекта
const course = { name: 'JS: React', slug: 'js-react' };
const entries = Object.entries(course); // [[ 'name', 'JS: React' ], [ 'slug', 'js-react' ]]
```
```js
// Слияние обьектов
//
const obj1 = { a: 'a', b: 'b' };
const obj2 = { c: 'c', b: 'v' };
Object.assign(obj1, obj2); // { a: 'a', b: 'v', c: 'c' }
```
```js
// Клонирование обьектов
//
const user = { name: 'Tirion', email: 'support@hexlet.io', age: 44 };

// Поверхностное клонирование
//
// Не затрагивает вложенные объекты. Они оказываются в новом объекте по ссылке из старого
const copyOfUser = Object.assign({}, user);
const copyOfUser = _.clone(user);

// Глубокое клонирование
const copyOfUser = _.cloneDeep(user);
```
```js
// SPREAD оператор
// Всё, что появляется с правой стороны спреда, будет иметь приоритет при слиянии

const user = { name: 'Vasya', age: 11 };
const newUser = { ...user, married: true, age: 25 };
// { name: 'Vasya', married: true, age: 25 }
// Возраст поменялся

const newUser = { age: 25, married: true, ...user };
// { name: 'Vasya', married: true, age: 11 }
// Возраст остался тем же


const user = { name: 'Irina', age: 25, married: false };
const user2 = { name: 'Petya', surname: 'Ivanov' };
const newUser = { ...user, married: true, ...user2 };
// { name: 'Petya', age: 25, married: true, surname: 'Ivanov' }
```

```js
// Деструктуризация обьекта
//

const person = { firstName: 'Rasmus', lastName: 'Lerdorf', manager: true };
const { firstName, manager } = person;
//firstName = 'Rasmus', manager = true

// Переназвать переменную
const { manager: isManager } = person;
// isManager = true

// Можно задать значение по умолчанию
const { age = 31 } = person;
// age = 31

// REST операция
const { firstName, ...rest } = person;
// rest = { lastName: 'Lerdorf', manager: true }
```
