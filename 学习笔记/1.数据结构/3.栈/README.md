[TOC]

# 1. 栈

## 1.1. 栈是什么?

`栈`是一个**后进先出**的数据结构(类似煤炉子一样,先放进去煤球最后才能拿出来,后放进去的煤球最先拿出来这样的一个道理)

> `javascript`中没有栈,但可以用`Array`来实现栈的所有功能

## 1.2. 栈的图示

> 如下图所示,核心就是一点:**先进后出**

 <img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gixb922ie3j30ai09sweg.jpg" width = "200" height = "200" alt="图片名称" align=center />

## 1.3. 模拟栈的操作

> 上面我们说了在`js`中没有栈,但是我们可以通过`array`来模拟栈的几个操作:

### 1.3.1. 入栈

```javascript
// 入栈
let stack = [];
stack.push(1);
stack.push(2);
```

### 1.3.2. 弹栈(也叫出栈)

```javascript
// pop 出栈,这个方法会返回被移除的元素哦~切记~
let stack = [1, 2, 3];
stack.pop();
stack.pop();
```

## 1.4. 什么场景下使用栈?

- 简单来说需要`后进先出`的场景
- 例如:十进制转二进制,判断字符串的括号是否有效,函数调用堆栈

**场景已:十进制转换为二进制**

> 略

**场景二:有效的括号(这是一道算法题)**

- 越靠后的左括号,对应的右括号越靠前
- 左括号入栈遇到与之匹配的右括号就出栈,最后栈空了就是合法的!
- 左括号入栈遇到与之匹配的右括号就出栈,遇到与之不匹配的右括号就直接报错!

```javascript
((((()))))  //合法
()()()()    //合法
(((()   //不合法
((()()()))  //合法
```

**场景三:函数调用堆栈**

- 栈在 JS 中最常用的估计就是函数堆栈模型了吧,通俗来讲就是"最后调用的函数最先执行完!"
- JS 解释器使用`栈`来控制函数的调用顺序,不需要我们来控制,已经有大神帮我们写好了 `JS` 解释器

```javascript
function greeting() {
  // [1] some codes here
  sayHi();
  // [2] some codes here
}
function sayHi() {
  return "Hi";
}

// 调用 greeting 函数
greeting();

// [3] some codes here
```

## 1.5. leetcode 原题: ( 20. 有效的括号 )

> 给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。....查看更多参考原题

[Leetcode 20.有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function (s) {
  // 1.括号一对一消除则知道奇数肯定无法消除,先判断是否为奇数,如果是奇数直接 return false
  if (s.length % 2 === 1) return false;
  // 2.新建一个"栈"
  let stack = [];
  // 3.开始遍历字符串遇到([{就入栈,如果遇到右侧括号则将其与栈顶的字符进行匹配,如果可以匹配则将栈顶元素进行弹栈操作,否则直接报错
  for (let i = 0; i < s.length; i++) {
    if (s[i] === "(" || s[i] === "[" || s[i] === "{") {
      stack.push(s[i]);
    } else {
      let top = stack[stack.length - 1]; //栈顶元素
      if (
        (top === "(" && s[i] === ")") ||
        (top === "[" && s[i] === "]") ||
        (top === "{" && s[i] === "}")
      ) {
        stack.pop();
      } else {
        return false;
      }
    }
  }
  // 4.字符串扫描完了,如果栈中为空说明都匹配了,都弹出去了,则返回 true,否则返回 false
  return stack.length === 0;
};
```

## 1.6. 前端与栈:JS 中的函数调用堆栈

> 略

## 1.7. 栈总结

- 重点 - 一定要牢记`栈`是`先进后出`的数据结构
- Javascript 中没有栈,但是可以使用 Array 来实现栈的所有功能
- 栈常用的操作:push,pop,stack[stack.length - ]

# 2. 刷题

栈学完了,后面就是刷`栈`相关的算法题!!!

[Leetcode 上栈的算法题](https://leetcode-cn.com/tag/stack/)
