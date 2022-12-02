# Coding standard

## General

- Do not repeat
- Frontend component
  - Under 150 lines, at most 250 lines
  - render: 30 lines
- Function
  - under 2 parameters
  - Functional programming
- No global variable
  ```js
  // BAD
  Array.prototype.diff = function () {};
  // GOOD
  class SuperArray extends Array {}
  ```
- just use someArray.length in for loop
- inhert: use `class` not `function`
- [Single-responsibility principle](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#BbJWx)
- [Open–closed principle](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#BbJWx)
- `Async/Await` > `Promise` > `callback function`
- [只对存在一定业务逻辑复杂性的代码进行注释](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#BbJWx)

## Naming

- Readable & Meaningful
- Unify

```js
// Readable & Maningful
var yearMonthDay = moment().format("YYYY/MM/DD");
var MINUTES_IN_A_YEAR = 525600;
// Unify
getUserInfo();
getUserData();
getUserRecord();
// Do not repeat
var Car = {
  make: "Honda",
  model: "Accord",
  color: "Blue",
  // carStyle: '' <- use `style` for key is fine
};
```

## Function

- Under 2 parameters
- Only 1 loop in 1 function
- Functional programming
  - [函数功能的单一性](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#fcHkr)
  - [Avoid side effect](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#BbJWx)

## Condition

- [封装判断条件](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#BbJWx)
- Avoid `!` in condition
  ```js
  // GOOD
  function isDOMNodePresent(node) {}
  function isDOMNodeNotPresent(node) {}
  ```

## Object

- [使用 Object.assign 设置默认对象](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#BbJWx)

## ES6

```js
// conditional assign value
function createMicrobrewery(name) {
  var breweryName = name || 'Hipster Brew Co.'
}
function writeForumComment(subject = 'No subject', body = 'No text') {
  ...
}

```

## Test

- [单一的测试每个概念](https://www.yuque.com/yuquefeifei-4wxne/ei1k02/lomppq#CJIAJ)

## Others

- [调用函数的函数和被调函数应放在较近的位置]
- [删除无效的代码]
- [不要在代码库中遗留被注释掉的代码]
- [不需要版本更新类型注释]
