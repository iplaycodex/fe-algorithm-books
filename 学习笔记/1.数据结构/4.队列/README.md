[TOC]

# 1. 队列

## 1.1. 队列的概念?

> 队列是一个"先进先出"的数据结构,Javascript 中没有队列,但可以用 `Array` 来实现队列的所有功能

图示就免了,很简单先进先出,`直筒筒`结构

## 1.2. 用 Array 来模拟一下

```javascript
// 新建一个队列
const queue = [];

// 模拟入队
queue.push(1);
queue.push(2);

// 模拟出队
const item1 = queue.shift();  // 移除数组的第一个元素并返回它
const item2 = queue.shift();
```

## 1.3. 队列的使用场景

- 所有需要"先进先出"的场景都可以使用队列
- 比如:食堂排队打饭,JS 异步中的任务队列,计算最近请求次数...

**场景一:食堂排队打饭**
略

**场景二:JS 异步中的任务队列**

- JS 是单线程,无法同时处理异步中的并发任务
- 使用任务队列先后处理异步任务

**场景三(一道算法题):计算最近请求的次数**

- 有新请求就入队, 3000ms 前发出的请求出队
- 队列的长度就是最近请求的次数

**CODE:**

```javascript
// 输入:
inputs = [[], [1], [100], [3001], [3002]];

// 输出:
[null, 1, 2, 3, 3];
```

## 1.4. Leetcode 队列算法题: 933.最近的请求次数

[Leetcode 算法题: 933.最近的请求次数](https://leetcode-cn.com/problems/number-of-recent-calls/)

## 1.5. 前端与队列

> 看一道面试题,下面的代码执行结果是什么?

```javascript
setTimeout(() => { console.log(1) }, 0);
console.log(2);

//答案:
2;
1;
```

很多人看到 `setTimeout` 的时间为 0,就会认为这个异步函数会立即执行,其实不然!JS 会跳过这个异步的函数,执行后面的同步代码,并把这个异步函数的回调函数放在任务队列中,依次执行.

### 1.5.1. 事件循环和任务队列

> JS 中一个很重要的概念:事件循环和任务队列!

看下面的一个图示:

![事件循环和任务队列](https://tva1.sinaimg.cn/large/007S8ZIlgy1giyobjbj6zj30cn06zdg1.jpg)

- JS (JS 引擎,用来执行 JS 代码)
- callback Queue 回调队列
- webAPI

**事件循环和任务队列非常重要!!!**

## 1.6. 队列总结

- 队列是一个`先进先出`的数据结构
- JS 中没有队列,但是可以用`Array`来模拟队列从而实现队列的所有功能
- 队列常用操作:`push`,`shift`,`queue[index]`

## 1.7. Leetcode 队列题集

[Leetcode 队列题集](https://leetcode-cn.com/tag/queue/)
